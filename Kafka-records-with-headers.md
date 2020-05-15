Introduction
===
todo - write a business usecase of sending a records with headers(one or two precise lines only)

Records With Headers (Produce)
===
Below are the examples of sample records with headers:

## JSON Record
```JSON
{
                        "key": 101,
                        "value": {
                            "name": "Foo",
                            "addressLine1": "99 Bar Street"
                        },
                        "headers": {
                            "my-company-header1": "my-value1",
                            "correlationId": "e.g.d85e88d2-9393-40a8-9c56-ec29004c45c9"
                        }
}
```

## RAW Record

```JSON
{
                        "key": 101,
                        "value": "Something",
                        "headers": {
                            "myKey": "MyValue",
                            "correlationId": "e.g.d85e88d2-9899-40a8-9c56-ec29004c45c9"
                        }
}
```

Test Scenario
===
Provide sample test scenarios for 

## JSON
todo

## RAW
todo


Records With Headers (Consume)
===
to do - mimic the above `produce` pattern for this section. Add sub sections etc


Conclusion
===
Please visit [HelloWorld Kafka Streaming]() repo for working examples to clone and try at home

