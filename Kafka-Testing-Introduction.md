# 1.  Introduction
In this Wiki page, we will see various concepts of Kafka distributed streams and how to test an Application built using Kafka and REST APIs. 

For more details about Kafka streams and how to develop a streaming application, please visit [Developing Streaming Applications](https://www.confluent.io/blog/stream-processing-part-1-tutorial-developing-streaming-applications).

# 2.  Kafka Testing Concepts
Kafka is a distributed messaging system. When we deal with a Kafka application, we need to know where the `topic` resides and what types of messages aka `records` are written aka `produced` to the topic, then what happens when the messages are `consumed` by the listeners.

Once we know these three things, we should be able to test a Kafka application easily.

# 2.1.  What is a Kafka topic
Kafka topics are divided into a number of partitions. Partitions allow you to parallelize a topic by splitting the data in a particular topic across multiple brokers — each partition can be placed on a separate machine to allow for multiple consumers to read from a topic in parallel.

# 2.2.  What is produce and consume
`Produce` is simply writing one or more records to a topic.

`Consume` is simply reading one or more records from one or more topic(s).

# 2.3.  Writing tests only to produce
When you write or produce to a topic you can verify the acknowledgment from a Kafka broker which is in the form of `recordMetadata`.

e.g.
```java

Response from broker after a successful "produce".

{
    "recordMetadata": {
        "offset": 0,
        "timestamp": 1547760760264,
        "serializedKeySize": 13,
        "serializedValueSize": 34,
        "topicPartition": {
            "hash": 749715182,
            "partition": 0,
            "topic": "demo-topic"
        }
    }
}
```

# 2.4.  Writing tests only to consume
When you read or consume from a topic you can verify the record(s) from the topics.
Here you can validate/assert some of the metadata too, but most of the times you might only need to deal with the records only(not the metadata).

e.g.
```java

Response from broker after a successful "consume".
{
    "records": [
        {
            "topic": "demo-topic",
            "key": "1547792460796",
            "value": "Hello World"
        }
    ]
}
```
The full record with meta data information looks like below, which too you can validate/assert in case you have a test-requirement to do so.
```java
{
    "records": [
        {
            "topic": "demo-topic",
            "partition": 0,
            "offset": 3,
            "timestamp": 1547792461364,
            "timestampType": "CREATE_TIME",
            "serializedKeySize": 13,
            "serializedValueSize": 11,
            "headers": {
                "headers": [],
                "isReadOnly": false
            },
            "key": "1547792460796",
            "value": "Hello World",
            "leaderEpoch": {
                "value": 0
            }
        }
    ]
}
```
# 2.5.  Writing tests for both produce and consume
In the same test, you can hook the two steps like below <br/>
+ Step-1) Produce to a topic e.g. `demo-topic` and validate `recordMetadata`
  + e.g. Produce a record with "key":"1234", "value":"Hello World"

+ Step-2) Consume from the same topic i.e. `demo-topic` and validate `records`
  + Assert that the same record was in the consumed records with "key": "1234", "value": "Hello World", because we might have consumed more that one record if they were produced to the same topic. 


# 3.  Writing your first produce test
To write the tests for any of 'Produce' or 'Consume' tests, we need to know the following details
+ The topic name which is our "end point" aka "url"
```

"url": "kafka-topic: demo-topic"

```

+ The operation i.e. `'produce' or 'consume'` 
```

"operation": "produce"

```
_Also you can use the `'load' or 'unload'` aka `'send' or 'receive'` which means the same._

+ While sending a message to the topic, we need to send as below
```java

"request": {
    "records": [
        {
            "key": "KEY-1234",
            "value": "Hello World"
        }
    ]
}

```

Please visit these pages for examples and explanations.
+ [Produce a RAW message]()
+ [Produce a JSON message]()

# 3.1.  Writing our first "consume" test
We need to know,
+ The topic name which is our "end point" aka "url"
```

"url": "kafka-topic: demo-topic"

```

+ The operation i.e. 'consume'` 
```

"operation": "consume"

```
_Also you can use the `'unload'` aka `'receive'` which exactly means the same._

+ While consuming message(s) from the topic, we need to send as below
```java

"request": { },

```
That's do nothing, but simply consume.

Or we can configure our test to do certain stuff while consuming or after consuming the records.
```
"request": {
    "consumerLocalConfigs": {
        "commitSync": true,
        "showRecordsConsumed": true,
        "maxNoOfRetryPollsOrTimeouts": 3
    }
}

```

>         "commitSync": true,

Here, we are telling the test to do a `commitSync` after consuming the message, that means, it won't read the message again when you `poll` next time. It will only read the new messages if any arrives on the topic.

>        "showRecordsConsumed": true,  // Default is true
Here, we are telling the test to show the consumed records in the response. If you set `"showRecordsConsumed": false`, then it will only show the size, not the actual records.

>        "maxNoOfRetryPollsOrTimeouts": 3
Here, we are telling the test to show poll 3 times maximum, then stop polling. If we have more records, we can set to a larger value. The default value is `100` mili sec.

>        "pollingTime": 500   // Default is 100 mili sec if you skip this flag.
Here, we are telling the test to poll for 500 mili sec each time it polls.

- Visit this page [All configurable keys - ConsumerLocalConfigs]() for the source code.
- Visit the [HelloWorld example]() to try it at home.

### :::Note:::
These config values can be set in the properties file global to all the tests, which means it will apply to all the tests in our test suite or the test pack. Also, we can override any of the configs for a particular test or tests inside the suite. **Hence it gives us very flexibility for covering all kind of test scenarios.**

Please visit these pages for examples and explanations.
+ [Consume a RAW message]()
+ [Consume a JSON message]()


# 4.  Validating Kafka response after producing
We can simply tell the test to check that it has been produced successfully as below
```JSON
"assertions": {
    "status": "Ok"
}
```

Or we can ask the test to assert that we have received `not null` "recordMetadata" from the Kafka brokers
```json
"assertions": {
    "status": "Ok",
    "recordMetadata": "$NOT.NULL"
}
```

Or we can go further and ask the test to assert the "recordMetadata" field-by-field to verify it has written to correct `partition` of the correct `topic` and much more as below. 
```json
"assertions": {
    "status": "Ok",
    "recordMetadata": {
        "offset": 0,
        "serializedKeySize": 13,
        "serializedValueSize": 34,
        "topicPartition": {
            "hash": 749715182,
            "partition": 0,
            "topic": "demo-topic"
        }
    }
}
```
Yes, just stick the JSON block as it is. Isn't it awesome and clean? Hasn't it take away a lot of hassles from us of doing vicious deserialization of the `acknowledgment` or the asserting field-by-field, making the test almost not-readable?

Or if you are not really bothered about some fields, you can simply put as `$NOT.NULL` against them as below or completely skip them from the "assertions block".

### :::Note:::
Field order doesn't really matter here as long as the structure is maintained. 👍 

```json
{
    "status": "Ok",
    "recordMetadata": {
        "topicPartition": {
            "partition": 0,
            "topic": "demo-2"
        },
        "offset": "$NOT.NULL",
        "timestamp": "$NOT.NULL",
        "serializedKeySize": "$NOT.NULL",
        "serializedValueSize": "$NOT.NULL"
    }
}
```

# 5.  Validating Kafka response after consuming
We can simply tell the test to check that we have received a number of records we intended to consume.
```java
"assertions": {
    "size" : 1
}
```

Or we can ask the test to assert a record as not null or field-by-filed of key/values of that record. 
```java
"assertions": {
    "size": 1
    "records": [
        {
            "key": "1547792460796",
            "value": "Hello World"
        }
    ]
}
```

Or we can ask the test to assert the records along with some metadata e.g. topic and partition info too. 

```java
"assertions": {
    "records": [
        {
            "key": "1547792460796",
            "value": "Hello World",
            "topic": "demo-ksql",
            "partition": 0,
            "offset": 3,
            "timestamp": 1547792461364
        }
    ],
    "size": 1
}
```

### :::Note:::
Field order doesn't really matter here as long as the structure is maintained. 👍 

# 6.  Combining Kafka testing with REST API testing
Most of the time we have situations to deal with Kafka and REST API testing. With `Zerocode` it's just zero effort when comes to this kind of situation or any API testing situation. You need to know four things only to write the tests 
```
1) The "url"
2) The "operation"
3) The "request"
4) The "assertions" i.e. the expected response
```

Let's see how we can fit REST API validation along with Kafka produce/consume validation at the same time.

In the first place, this is not a big deal. Nothing really changes from a test perspective other than the "url".

That means the "url" is a REST end point as below:

>            "url": "/api/v1/persons"

Then, the Zerocode framework picks the REST endpoint details from the "host.properties" and create the full URL and invokes the REST API and asserts the response. The effective URL will be as below behind the scene 

>            "url": "http://localhost:8082/api/v1/persons"

```properties
"host.properties"

kafka.bootstrap.servers=localhost:9092
kafka.producer.properties=kafka_servers/kafka_producer_avro.properties
kafka.consumer.properties=kafka_servers/kafka_consumer_avro.properties

# REST End point server FQDN 
web.application.endpoint.host=http://localhost
web.application.endpoint.port=8082
web.application.endpoint.context=

# URL of any other REST/Http server
kafka-ksql-server-fqdn=http://localhost:8088

```

If we are inside a micro-services deployment world, simply put more "url"s of your `Kubernetes` pods you need to deal with e.g. 

>            "url": "${http-server-fqdn}/api/v1/persons"

The "http-server-fqdn" above is another config key-value which can be simply put into the host properties file where we keep Kafka `kafka.bootstrap.servers` details.

Now, in a BDD scenario like below, the tests steps would involve calls to  Kafka topics and validate the REST api response over an Http call(s).
```
AC1:
Given I send an "Address" record with id "id-lon-123" to the "address-topic",
When the(my) record gets processed by the Kafka application,
Then the message will be "PUT" to the "address REST api" and updated in the DB

AC2:
Given I query(GET) the "Address" REST API by using "/api/v1/addresses/id-lon-123" ,
When I receive the updated "Address" record,
Then I will receive the updated address and validate the fields. 

```

We have at least two steps(can be more steps the cover Happy and Sad paths) to perform here to test the scenario end-to-end. 

To keep it simple, lets first go with the simple two steps, later we can explore that it's so easy to hook more additional steps.

Step-1 (AC1)
***
```json
{
    "name": "produce_to_kafka",
    "url": "kafka-topic:people-address",
    "operation": "produce",
    "request": {
        "recordType" : "JSON",
        "records": [
            {
                "key": "id-lon-123",
                "value": {
                    "id": "id-lon-123",
                    "postCode": "UK-BA9"
                }
            }
        ]
    },
    "assertions": {
        "status": "Ok",
        "recordMetadata" : "$NOT.NULL"
    }
}
```

Step-2 (AC2)
***
```json
{
    "name": "verify_updated_address",
    "url": "/api/v1/addresses/id-lon-123",
    "operation": "GET",
    "request": {
        "headers": {
            "X-GOVT-API-KEY": "top-key-only-known-to-secu-cleared" // Skip this if Auth key not needed
        }
    },
    "assertions": {
        "status": 200,
        "value": {
            "id": "id-lon-123",
            "postCode": "UK-BA9"
        }
    }
}
```

When we combine the steps it looks like below. Here we can avoid hardcoding the value and reuse the "postcode" from the "request" payload.

>    $.produce_to_kafka.request.records[0].value.postcode

This will resolve to "UK-BA9" in the runtime.

Step1 + Step2
***

```java

test_kafka_and_rest.json
------------------------

{
    "scenarioName": "Kafka and REST api validation example",
    "steps": [
        {
            "name": "produce_to_kafka",
            "url": "kafka-topic:people-address",
            "operation": "produce",
            "request": {
                "recordType" : "JSON",
                "records": [
                    {
                        "key": "id-lon-123",
                        "value": {
                            "id": "id-lon-123",
                            "postCode": "UK-BA9"
                        }
                    }
                ]
            },
            "assertions": {
                "status": "Ok",
                "recordMetadata" : "$NOT.NULL"
            }
        },
        {
            "name": "verify_updated_address",
            "url": "/api/v1/addresses/${$.produce_to_kafka.request.records[0].value.id}",
            "operation": "GET",
            "request": {
                "headers": {
                    "X-GOVT-API-KEY": "top-key-only-known-to-secu-cleared"
                }
            },
            "assertions": {
                "status": 200,
                "value": {
                    "id": "${$.produce_to_kafka.request.records[0].value.id}",
                    "postCode": "${$.produce_to_kafka.request.records[0].value.postcode}"
                }
            }
        }
    ]
}

```


# 7.  Producing RAW messages vs JSON messages
When we have situation or requirements to produce simple texts which are not JSON records, then the framework takes care of it by default. Or for the test readability(you can even skip this field), you can mention it as below.
>          "recordType" : "RAW",

When we have situation or requirements to produce JSON records, then we need to tell the test to do so as below.

>          "recordType" : "JSON"

The host properties are defined as below
```properties

"host.properties"
-----------------

kafka.bootstrap.servers=localhost:9092
kafka.producer.properties=kafka_servers/kafka_producer_avro.properties
kafka.consumer.properties=kafka_servers/kafka_consumer_avro.properties

# REST End point server FQDN 
web.application.endpoint.host=http://localhost
web.application.endpoint.port=8082
web.application.endpoint.context=

```

You simply run the test(s) via a JUnit runner `ZeroCodeUnitRunner.class` as below
```java
@TargetEnv("kafka_servers/host.properties")
@RunWith(ZeroCodeUnitRunner.class)
public class KafkaRestTest {

    @Test
    @JsonTestCase("kafka/produce/test_kafka_and_rest.json")
    public void testKafkaAndRestApi() throws Exception {
    }

}
```

See more RAW and JSON examples in the sidebar of the Wiki. :raised_hands:


# 8.  Why do I need `zerocode-tdd` lib
Zerocode is a light-weight, simple and extensible open-source framework for writing test intentions in a simple JSON format that facilitates both declarative configuration and automation. The framework manages the request payload handling and response assertions at the same time.

Zerocode has taken a different approach to solve the fuss involved in the Kafka and REST API testing.

It has got the best of best ideas and practices from the community and the adoption is rapids growing among the developer/tester community. Even many times the manual test engineers come out and help in automation due to the simplicity of writing tests.

# 9. Conclusion
In this tutorial, we looked at some of the Kafka concepts and how to test Kafka applications using the Zerocode Testing Framework.

The complete source code and all example code snippets for this Wiki page can be found below.
+ [Produce Tests](https://github.com/authorjapps/zerocode/tree/master/kafka-testing/src/test/resources/kafka/produce)
+ [Produce Tests](https://github.com/authorjapps/zerocode/tree/master/kafka-testing/src/test/resources/kafka/consume)
+ [KSQL Tests](https://github.com/authorjapps/zerocode/tree/master/kafka-testing/src/test/resources/kafka/consume/ksql)
+ [Produce Records Directly From File](https://github.com/authorjapps/zerocode/tree/master/kafka-testing/src/test/resources/kafka/produce/file_produce)
+ [Consume Records And Dump To File](https://github.com/authorjapps/zerocode/tree/master/kafka-testing/src/test/resources/kafka/consume/file_dump)

# Happy API Testing! 🐼 