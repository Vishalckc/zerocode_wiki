+ User's Guide
  + [Motivation](./About-Motivation.md)
  + [What is Zerocode](./What-is-Zerocode-testing)
  + [Hello World Examples](./Zerocode-Hello-World-Projects.md)
  + [An User journey(CRUD operation)- Simple n easy](./User-journey:-Create,-Update-and-GET-Employee-Details.md)
  + [JSON or YAML based test-scenarios](./User-journey:-Create,-Update-and-GET-Employee-Details#using-json.md)
  + [Dealing with YAML payload and arrays](./YAML-DSL-For-Test-Scenarios.md)
  + [Finished writing tests - Setting up CI Jenkins Build Pipe Line](./After-you-have-written-all-the-tests,-what's-next.md)
  

+ Matchers
  + [Strict Mode](./Strict-Mode-Payload-Comparison.md)
  + [Lenient Mode](#TODO.md)
  + [Available Matchers](./matchers.md)
  + [Validators vs Matchers](./Validators-and-Matchers.md)

+ Zerocode Tokens
  + [LOCALDATE.TODAY](./Token:-LocalDate-Today.md)
  + [LOCALDATETIME.NOW](./Token:-LocalDateTime-Now.md)
  + [RANDOM.NUMBER](./Token:-Random-Number.md)
  + [RANDOMSTRING.PREFIX](./Token:-Random-String.md)
  + [RANDOM.UUID](./Token:-Random-UUID.md)
  + [RECORD.DUMP](./Token:-Record-Dump.md)
  + [STATIC.ALPHABET](./Token:-Static-Alphabet.md)
  + [SYSTEM.ENV](./Token:-System-Environment.md)
  + [SYSTEM.PROPERTY](./Token:-System-Property.md)
  + [XML.FILE](./Token:-XML-File.md)

+ YAML DSL
  + [YAML Based Test Scenario Automation](./YAML-DSL-For-Test-Scenarios.md)
+ Http Testing
  + [External JSON file content](./External-JSON-file-as-reusable-content.md)
  + [Env Switching - CI,DIT,SIT etc](./Switching-Environment-to-CI-DIT-SIT-UAT-for-Test-Suite-or-Regression-Pack.md)
  + [Sending "Content-Type": "application/x-www-form-urlencoded"](./application-x-www-form-urlencoded-urlencoded-with-KeyValue-params.md)
  + [Http max implicit delay and connection timeout](./HTTP-max-timeout-or-implicit-wait.md)

+ Kafka Testing
  + [Introduction](./Kafka-Testing-Introduction.md)
  + [Produce raw message](./Produce-raw-message.md)
  + [Consume raw message](./Consume-RAW-message.md)
  + [Produce JSON message](./Produce-JSON-message.md)
  + [Consume JSON message](./Consume-JSON-message.md)
  + [Produce and consume XML message](./Producing-and-consuming-XML-message-to-and-from-a-Kafka-topic.md)
  + [Produce avro message]()
  + [Consume avro message]()
  + [KSQL in action]()
  + [Produce multiple records]()
  + [Produce from file]()
  + [Produce to a partition](#todo)
  + [Produce and consume records with headers](./Kafka-records-with-headers.md)
  + [Produce n assert partition ack]()
  + [Comsume and dump to file]()
  + [commitSync vs commitAsync]()
  + [Overriding config inside a test]()
  + [Chosing String or Int or Avro Serializer]()
  + [Chosing String or Int or Avro Deserializer]()
  + [Attaching  timestamp during load]()
  + [Default timestamp provided by Kafka]()
  + [Consume and assert avro schema metadata]()
  + [Error handling - produce via avro schema ]()

+ DB Testing
  + [Postgres db data validation](./Sample-DB-SQL-Executor.md)

+ Kotlin Testing
  + [Testing Kotlin Application](./Testing-Kotlin-Application-using-Zerocode.md)
  + [Kotlin Performance testing](./Kotlin-Performance-testing.md)

+ Performance Testing - Load and Stress
  + [Performance Testing - via awesome JUnit runners](./Load-or-Performance-Testing-(IDE-based.md))
  + [Load Vs Stress generation on target application](./Load-or-Performance-Testing-(IDE-based.md)#load-vs-stress-horizontal-load-vs-vertical-load)
  + [Run a single test or a scenario in parallel](./Load-or-Performance-Testing-(IDE-based.md)#how-to-run-tests-in-parallel-in-context-of-one-or-more-scenarios-)
  + [Run multiple test scenarios in parallel - Production load simulation](https://github.com/authorjapps/performance-tests#multi-scenario-parallel-load)
  + [Dynamically change the payload for every request](./Load-or-Performance-Testing-(IDE-based.md)#how-to-dynamically-change-the-payload-for-every-request-during-the-load-)
  + [Analytics - Useful report(s) or statistics](./Load-or-Performance-Testing-(IDE-based.md)#how-to-generate-useful-reports-or-statistics-to-explain-the-behaviour-of-the-system-under-test)

+ Parameterized Testing
  + [Value source - List of values](./Parameterized-Testing-From-List-of-Values.md)
  + [CSV source - List of comma separated values](./Parameterized-Testing-From-CSV-rows.md)

+ Docker
  + [Running Postgres DB in a container](./Docker-container-for-a-Postgres-DB.md)
  + [Picking host, port, user, password details](./Sample-DB-SQL-Executor#config-properties.md)
  + [Running DB executor and asserting SQL result sets](./Sample-DB-SQL-Executor.md)

+ More+
  + [Reusing step via step file(s)](./Reusing-Single-and-Multiple-Step-Files.md)

+ Extensions
  + [In-Memory Spring-Boot Integration testing](https://github.com/authorjapps/spring-boot-integration-test.md)
  + [Load testing a Cassandra Application(Spring)](./zerocode-spring-junit.md)
  + [Gradle - Charts and Reports](./Gradle-build-for-JUnit-Smart-Chart-and-CSV-Reports.md)
  + [Kotlin Integration Testing - Simlified via Zerocode](https://dzone.com/articles/kotlin-spring-bootspring-data-h2-db-rest-api) 

+ JUnit5 Jupiter Test
  + [JUnit5 Parallel Load Extension](./JUnit5-Jupiter-Parallel-Load-Extension.md)

+ Questions And Answers(FAQ)
  + [What is Zerocode testing?](./What-is-Zerocode-testing.md)
  + [SSL http https connections supported?](./QnA:-Does-it-support-https-connections%3F.md)
  + [How to assert array size Greater-Than Lesser-Than etc?](./QnA:-How-to-assert-an-array-in-the-response-with-SIZE-Greater-Than-or-Lesser-Than-etc%3F.md)
  + [How to invoke POST api?](./QnA:-How-to-invoke-POST-apis-%3F.md)
  + [How to assert custom headers of the response?](./QnA:-How-to-assert-custom-headers-of-the-response%3F.md)
  + [How to pass custom security token into the request header?](./How-to-pass-custom-security-token-into-the-request-header-which-is-new-for-every-request%3F.md)
  + [When to use JUnit Suite runner and when Zerocode Package runner?](./Suite-Runner-Vs-Package-runner.md)
  + [How to execute DB SQL and assert?](./Sample-DB-SQL-Executor.md)
  + [How to handle Http response other than utf-8 e.g. utf-16 or utf-32 ?](./Charset-UTF-8-or-UTF-16-or-UTF-32-etc-in-the-http-response.md)
  + [Random Number Generator Placeholders Usages and Limits](./Placeholders-Usage-and-Limits.md)
  + [Automation tests for Zerocode lib itself](./Automation-tests-for-Zerocode-lib-itself.md)
  + [Picking a leaf value from the array matching JSON Path](./When-JSON-Path-Matching-returns-value-or-values-as-an-array.md)
  + [Array assertions made easy, incl. size and element finder](./Array-assertions-made-easy--e.g.-SIZE,-element-finder.md)

### Blogs
+ [Read Our Blogs](./Read-Our-Blogs.md)
  + [Top 16 Open Source API Testing Tools For REST & SOAP Services](https://www.joecolantonio.com/12-open-source-api-testing-tools-rest-soap-services/) - joecolantonio (Lists popular tools - Globally) 
  + [OAuth2 Test Automation](https://dzone.com/articles/oauth2-authentication-in-zerocode) - DZone 2min Read
  + [Zero defect APIs - Build Pipe Line](https://medium.com/@bethecodewithyou/develop-zerodefect-apis-with-zerocode-cadd9dc2a430) - Medium 10 min Read
  + [Develop ZeroDefect API's with ZeroCode!](https://extremeportal.blogspot.com/2018/10/zerodefect-rest-apis-with-zerocode.html) - Extreme Portal ( A **must read** for all developers and test engineers) 10min Read
  + [Performance testing using JUnit and maven](https://www.codeproject.com/Articles/1251046/How-to-do-performance-testing-using-JUnit-and-Mave) - Codeproject 10 min Read
  + [REST API or SOAP End Point Testing](https://www.codeproject.com/Articles/1242569/REST-API-or-SOAP-End-Point-Testing-with-ZeroCode-J) - Codeproject 10min Read
  + [DZone- MuleSoft API Testing With Zerocode Test Framework](https://dzone.com/articles/zerocode-test-framework-for-restsoap-api-tddbdd-ap) - DZone 5min Read
  + [Testing need not be harder or slower, it should be easier and faster](https://dzone.com/articles/rest-api-testing-using-the-zerocode-json-based-bdd) - DZone 5 min Read
  + [Kotlin Integration Testing simplified via Zerocode](https://extremeportal.blogspot.com/2018/11/kotlin-dev-spring-boot-rest-api-with.html) - Extreme portal 10 min Read
  + [and More...](./Read-Our-Blogs.md)
