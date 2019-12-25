The Problem
===
Automated testing of REST APIs or SOAP APIs in a [declarative fashion](https://ieeexplore.ieee.org/document/5070714) is still difficult in Java compared to OSS frameworks provided by other programming languages like [Python](https://github.com/svanoort/pyresttest#sample-test), JavaScript. These languages provide YAML or JSON or Fluent API interfaces or [DSLs](https://en.wikipedia.org/wiki/Domain-specific_language) for easily writing test scenarios.

Zerocode brings similar simplicity to Java to validate a REST APIs/SOAP APIs in a declarative and configurable way.

Challenges
===
Zerocode intends to solve many other testing challenges such as:
- Running tests in parallel
- Generating load/stress on the target server
- Writing tests using YAML, JSON or Java/Kotlin Fluent APIs
- Switching environments are configurable programmatically
- Running tests in a containerized way such as Docker
- Firing tests against multiple hosts in Microservices deployments


Motivation
===
The motivation for the inception of `Zerocode` has roots in the country's one of the largest `Digital Transformation Project` which posed tough challenges to testing approach due to 

* A large number of microservices being used to achieve various `workflows` based on REST APIs/JSON Payload
* A large number of `data pipelines` to ingest various legacy system's data into the project’s `Big Data` store.
* REST APIs to be tested in `isolation` as well as `integrated`
* Tests to be run in `parallel` to reduce feeedback time during the Build Pipeline
* Small SIT and Large SIT should have their respective regression packs
* Performance testing to be done by developers themselves
* Data streams APIs should be validated easily


Over several brainstorming sessions, automation testers and developers came to a common conclusion to write tests
* Using enable Fluent APIs/DSLs
* That will allow anyone to change and maintain the tests easily
* Avoid writing boilerplate or glue code 
* Large numbers of tests can be well organized for env specific regression packs
* Configurable for multiple environments (LAPTOP, DEV/DIT/CI, SIT, UAT, PRE-PROD etc)

The outcome of the sessions was to consider a `steps based` scenario build-up approach with JUnit, like Cucumber/JBehave where the underlying test and test data is picked from a referenced `JSON file` instead of a `feature` file. 

JSON is well recognized widely supported by `all IDEs` and hence could prove to be a good approach.

In fact, many folks were already practicing this kind of approach in a similar manner in their respective Govt, Media, Banking and Retail projects, but was never unified so that the approach could be reused to benefit more and more testers and developers across the program/industries.

After the implementation of the agreed approach we found that we were successfully able to achieve the following:

* Multiple `Jenkins Pipeline` integrations was seamless
* Tests were simple, `human readable JSON/Java Fluent` files
* Plugging in Custom HTTP Client was quick and easy
* `Test reports` were apt and to the point, easily searchable
* Parallel running was declarative and easily configuration

The above approach helped the program in a big way. 

Then in the recent years `Zerocode` has unified the approaches with additions of much more testing features to make it easy and efficient for the testing community.
