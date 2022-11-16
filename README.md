# restAPI
This repository demonstrate API test framework based on Cucumber BDD API framework using Maven with Rest Assured Java. Application considered for demonstration is : https://www.woolworths.com.au/apis/ui/v2/Search/count?searchTerm=deli
Installation (pre-requisites)
JDK 1.9+ (make sure Java class path is set)
Maven (make sure .m2 class path is set)
Eclipse
Maven
Cucumber
Maven dependencies
Maven surfire
Cucumber-java
Cucumber-junit
Cucumber reporting
Rest assured
slf4j
log4j
Framework set up
Fork / Clone repository from here or download zip and set it up in your local workspace.

In Eclipse-> import-> existing maven project
Run time JRE is set to Java 9+
Setting-up test runner class as per test requirement
Existing test runner setup will run all the feature files under src/test/java/features/ tagged as @RestAPI
To run specific feature file set features path to src/test/java/features/RestAPIGet.feature
Run test-runner class using mvn command from command line
Navigate to the project directory. Run command line from the directory. Typemvn clean test command to run test-runner file. With this command it will start executing feature files specified under test runner file

To run test-runner file, use command 'mvn clean test'
Run test-runner class directly from Eclipse
Open project workspace in Eclipse
Right-click on root Project, select Run As->Maven Test

Right-click on TestRunner.java, select Run As->JUnit Test `
Reporter
Once tests are executed, on the console or command propmt user gets link to view the report generated by cucumber. Paste the url on the browser

The example below is a report generated after executing smoke tests https://reports.cucumber.io/reports/dfca9502-44c9-4799-bb07-5df19de81593

Develop automation scripts using BDD approach -Cucumber- Rest Assured Java
There are one StepDefinition file which is packaged under src/test/java/stepDefinitions/RestAPIGetSteps

Tests are written in the Cucumber framework using the Gherkin Syntax.

@GetAPI
Scenario Outline: GET all posts from API

Given I do a GET call to "<url>"
Then response is "<statusCode>"

        Examples:
        |url|statusCode|
        |https://www.woolworths.com.au/apis/ui/v2/Search/count?searchTerm=deli|200|

Project Structure of a Cucumber BDD API framework using Maven with Rest Assured Java
Maven for cucumber provides two folder to logically place the file

a. src/main/java - As this is small project, have left this empty. Usually user can store re-usable methods, pojo classes.

b. src/test/java

cucumber.Options package: Contains test runner java class
feature package: Contains feature files divided by modules
stepDefinitions package: Contains stepDefinitions
utilities package: Contains various classes used in test classes
AssertionConstants class: All constant are stored in this class instead of passing hardcoded values
JsonUtils class: Method to extract values from API response
RequestFilter class: Methods to filter request specification
RestAssuredUtils class: Methods to perform API requests
log4j.properties file: Properties of logging is defined. All classes are logged with INFO and ERROR level.
logs folder: logs.log file is created once the test execution is complete

Licensing
This project is licensed under the terms of the MIT license.
