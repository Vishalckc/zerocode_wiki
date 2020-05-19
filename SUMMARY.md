+ User's Guide
  + [Motivation](https://github.com/authorjapps/zerocode/wiki/About-Motivation.md)
  + [What is Zerocode](https://github.com/authorjapps/zerocode/wiki/What-is-Zerocode-testing)
  + [Hello World Examples](https://github.com/authorjapps/zerocode/wiki/Zerocode-Hello-World-Projects.md)
  + [An User journey(CRUD operation)- Simple n easy](https://github.com/authorjapps/zerocode/wiki/User-journey:-Create,-Update-and-GET-Employee-Details.md)
  + [JSON or YAML based test-scenarios](https://github.com/authorjapps/zerocode/wiki/User-journey:-Create,-Update-and-GET-Employee-Details#using-json.md)
  + [Dealing with YAML payload and arrays](https://github.com/authorjapps/zerocode/wiki/YAML-DSL-For-Test-Scenarios.md)
  + [Finished writing tests - Setting up CI Jenkins Build Pipe Line](https://github.com/authorjapps/zerocode/wiki/After-you-have-written-all-the-tests,-what's-next.md)
  

+ Matchers
  + [Strict Mode](https://github.com/authorjapps/zerocode/wiki/Strict-Mode-Payload-Comparison.md)
  + [Lenient Mode](#TODO.md)
  + [Available Matchers](https://github.com/authorjapps/zerocode/wiki#matchers.md)
  + [Validators vs Matchers](https://github.com/authorjapps/zerocode/wiki/Validators-and-Matchers.md)

+ Zerocode Tokens
  + [LOCALDATE.TODAY](https://github.com/authorjapps/zerocode/wiki/Token:-LocalDate-Today.md)
  + [LOCALDATETIME.NOW](https://github.com/authorjapps/zerocode/wiki/Token:-LocalDateTime-Now.md)
  + [RANDOM.NUMBER](https://github.com/authorjapps/zerocode/wiki/Token:-Random-Number.md)
  + [RANDOMSTRING.PREFIX](https://github.com/authorjapps/zerocode/wiki/Token:-Random-String.md)
  + [RANDOM.UUID](https://github.com/authorjapps/zerocode/wiki/Token:-Random-UUID.md)
  + [RECORD.DUMP](https://github.com/authorjapps/zerocode/wiki/Token:-Record-Dump.md)
  + [STATIC.ALPHABET](https://github.com/authorjapps/zerocode/wiki/Token:-Static-Alphabet.md)
  + [SYSTEM.ENV](https://github.com/authorjapps/zerocode/wiki/Token:-System-Environment.md)
  + [SYSTEM.PROPERTY](https://github.com/authorjapps/zerocode/wiki/Token:-System-Property.md)
  + [XML.FILE](https://github.com/authorjapps/zerocode/wiki/Token:-XML-File.md)

+ YAML DSL
  + [YAML Based Test Scenario Automation](https://github.com/authorjapps/zerocode/wiki/YAML-DSL-For-Test-Scenarios.md)
+ Http Testing
  + [External JSON file content](https://github.com/authorjapps/zerocode/wiki/External-JSON-file-as-reusable-content.md)
  + [Env Switching - CI,DIT,SIT etc](https://github.com/authorjapps/zerocode/wiki/Switching-Environment-to-CI-DIT-SIT-UAT-for-Test-Suite-or-Regression-Pack.md)
  + [Sending "Content-Type": "application/x-www-form-urlencoded"](https://github.com/authorjapps/zerocode/wiki/application-x-www-form-urlencoded-urlencoded-with-KeyValue-params.md)
  + [Http max implicit delay and connection timeout](https://github.com/authorjapps/zerocode/wiki/HTTP-max-timeout-or-implicit-wait.md)

+ Kafka Testing
  + [Introduction](https://github.com/authorjapps/zerocode/wiki/Kafka-Testing-Introduction.md)
  + [Produce raw message](https://github.com/authorjapps/zerocode/wiki/Produce-raw-message.md)
  + [Consume raw message](https://github.com/authorjapps/zerocode/wiki/Consume-RAW-message.md)
  + [Produce JSON message](https://github.com/authorjapps/zerocode/wiki/Produce-JSON-message.md)
  + [Consume JSON message](https://github.com/authorjapps/zerocode/wiki/Consume-JSON-message.md)
  + [Produce and consume XML message](https://github.com/authorjapps/zerocode/wiki/Producing-and-consuming-XML-message-to-and-from-a-Kafka-topic.md)
  + [Produce avro message]()
  + [Consume avro message]()
  + [KSQL in action]()
  + [Produce multiple records]()
  + [Produce from file]()
  + [Produce to a partition](#todo)
  + [Produce and consume records with headers](https://github.com/authorjapps/zerocode/wiki/Kafka-records-with-headers.md)
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
  + [Postgres db data validation](https://github.com/authorjapps/zerocode/wiki/Sample-DB-SQL-Executor.md)

+ Kotlin Testing
  + [Testing Kotlin Application](./Testing-Kotlin-Application-using-Zerocode.md)
  + [Kotlin Performance testing](https://github.com/authorjapps/zerocode/wiki/Kotlin-Performance-testing.md)

+ Performance Testing - Load and Stress
  + [Performance Testing - via awesome JUnit runners](https://github.com/authorjapps/zerocode/wiki/Load-or-Performance-Testing-(IDE-based).md)
  + [Load Vs Stress generation on target application](https://github.com/authorjapps/zerocode/wiki/Load-or-Performance-Testing-(IDE-based).md#load-vs-stress-horizontal-load-vs-vertical-load)
  + [Run a single test or a scenario in parallel](https://github.com/authorjapps/zerocode/wiki/Load-or-Performance-Testing-(IDE-based).md#how-to-run-tests-in-parallel-in-context-of-one-or-more-scenarios-)
  + [Run multiple test scenarios in parallel - Production load simulation](https://github.com/authorjapps/performance-tests#multi-scenario-parallel-load)
  + [Dynamically change the payload for every request](https://github.com/authorjapps/zerocode/wiki/Load-or-Performance-Testing-(IDE-based).md#how-to-dynamically-change-the-payload-for-every-request-during-the-load-)
  + [Analytics - Useful report(s) or statistics](https://github.com/authorjapps/zerocode/wiki/Load-or-Performance-Testing-(IDE-based).md#how-to-generate-useful-reports-or-statistics-to-explain-the-behaviour-of-the-system-under-test)

+ Parameterized Testing
  + [Value source - List of values](https://github.com/authorjapps/zerocode/wiki/Parameterized-Testing-From-List-of-Values).md
  + [CSV source - List of comma separated values](https://github.com/authorjapps/zerocode/wiki/Parameterized-Testing-From-CSV-rows).md

+ Docker
  + [Running Postgres DB in a container](https://github.com/authorjapps/zerocode-docker-factory/wiki/Docker-container-for-a-Postgres-DB).md
  + [Picking host, port, user, password details](https://github.com/authorjapps/zerocode/wiki/Sample-DB-SQL-Executor#config-properties).md
  + [Running DB executor and asserting SQL result sets](https://github.com/authorjapps/zerocode/wiki/Sample-DB-SQL-Executor).md

+ More+
  + [Reusing step via step file(s)](https://github.com/authorjapps/zerocode/wiki/Reusing-Single-and-Multiple-Step-Files).md

+ Extensions
  + [In-Memory Spring-Boot Integration testing](https://github.com/authorjapps/spring-boot-integration-test).md
  + [Load testing a Cassandra Application(Spring)](https://github.com/authorjapps/zerocode-spring-junit).md
  + [Gradle - Charts and Reports](https://github.com/authorjapps/zerocode/wiki/Gradle-build-for-JUnit-Smart-Chart-and-CSV-Reports).md
  + [Kotlin Integration Testing - Simlified via Zerocode](https://dzone.com/articles/kotlin-spring-bootspring-data-h2-db-rest-api).md 

+ JUnit5 Jupiter Test
  + [JUnit5 Parallel Load Extension](https://github.com/authorjapps/zerocode/wiki/JUnit5-Jupiter-Parallel-Load-Extension).md

+ Questions And Answers(FAQ)
  + [What is Zerocode testing?](https://github.com/authorjapps/zerocode/wiki/What-is-Zerocode-testing).md
  + [SSL http https connections supported?](https://github.com/authorjapps/zerocode/wiki/QnA:-Does-it-support-https-connections%3F).md
  + [How to assert array size Greater-Than Lesser-Than etc?](https://github.com/authorjapps/zerocode/wiki/QnA:-How-to-assert-an-array-in-the-response-with-SIZE-Greater-Than-or-Lesser-Than-etc%3F).md
  + [How to invoke POST api?](https://github.com/authorjapps/zerocode/wiki/QnA:-How-to-invoke-POST-apis-%3F).md
  + [How to assert custom headers of the response?](https://github.com/authorjapps/zerocode/wiki/QnA:-How-to-assert-custom-headers-of-the-response%3F).md
  + [How to pass custom security token into the request header?](https://github.com/authorjapps/zerocode/wiki/How-to-pass-custom-security-token-into-the-request-header-which-is-new-for-every-request%3F).md
  + [When to use JUnit Suite runner and when Zerocode Package runner?](https://github.com/authorjapps/zerocode/wiki/Suite-Runner-Vs-Package-runner).md
  + [How to execute DB SQL and assert?](https://github.com/authorjapps/zerocode/wiki/Sample-DB-SQL-Executor).md
  + [How to handle Http response other than utf-8 e.g. utf-16 or utf-32 ?](https://github.com/authorjapps/zerocode/wiki/Charset-UTF-8-or-UTF-16-or-UTF-32-etc-in-the-http-response).md
  + [Random Number Generator Placeholders Usages and Limits](https://github.com/authorjapps/zerocode/wiki/Placeholders-Usage-and-Limits).md
  + [Automation tests for Zerocode lib itself](https://github.com/authorjapps/zerocode/wiki/Automation-tests-for-Zerocode-lib-itself).md
  + [Picking a leaf value from the array matching JSON Path](https://github.com/authorjapps/zerocode/wiki/When-JSON-Path-Matching-returns-value-or-values-as-an-array).md
  + [Array assertions made easy, incl. size and element finder](https://github.com/authorjapps/zerocode/wiki/Array-assertions-made-easy--e.g.-SIZE,-element-finder).md

### Blogs
+ [Read Our Blogs](https://github.com/authorjapps/zerocode/wiki/Read-Our-Blogs).md
  + [Top 16 Open Source API Testing Tools For REST & SOAP Services](https://www.joecolantonio.com/12-open-source-api-testing-tools-rest-soap-services/).md - joecolantonio (Lists popular tools - Globally) 
  + [OAuth2 Test Automation](https://dzone.com/articles/oauth2-authentication-in-zerocode).md - DZone 2min Read
  + [Zero defect APIs - Build Pipe Line](https://medium.com/@bethecodewithyou/develop-zerodefect-apis-with-zerocode-cadd9dc2a430).md - Medium 10 min Read
  + [Develop ZeroDefect API's with ZeroCode!](https://extremeportal.blogspot.com/2018/10/zerodefect-rest-apis-with-zerocode.html).md - Extreme Portal ( A **must read** for all developers and test engineers) 10min Read
  + [Performance testing using JUnit and maven](https://www.codeproject.com/Articles/1251046/How-to-do-performance-testing-using-JUnit-and-Mave).md - Codeproject 10 min Read
  + [REST API or SOAP End Point Testing](https://www.codeproject.com/Articles/1242569/REST-API-or-SOAP-End-Point-Testing-with-ZeroCode-J).md - Codeproject 10min Read
  + [DZone- MuleSoft API Testing With Zerocode Test Framework](https://dzone.com/articles/zerocode-test-framework-for-restsoap-api-tddbdd-ap).md - DZone 5min Read
  + [Testing need not be harder or slower, it should be easier and faster](https://dzone.com/articles/rest-api-testing-using-the-zerocode-json-based-bdd).md - DZone 5 min Read
  + [Kotlin Integration Testing simplified via Zerocode](https://extremeportal.blogspot.com/2018/11/kotlin-dev-spring-boot-rest-api-with.html).md - Extreme portal 10 min Read
  + [and More...](https://github.com/authorjapps/zerocode/wiki/Read-Our-Blogs).md
