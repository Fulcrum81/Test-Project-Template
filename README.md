# Test-Project-Template

Default template (based on maven archetype) for generation an initial structure of test project. 

###The project uses:
* Language: Java (1.8)
* WebDriver: 2.47.1
* Build Manager: Maven
* Testing Framework: TestNG
* Test-runner: maven-surfire-plugin.
* Reporter: ReportNG (+default TestNG).
* Logger: Log4j2.

###Base moments which have been resolved with the project:
* Template project can be generated based on maven archetype
* All variables can be passed to command line (include testng properties such as: threadCount and parallel by options)
* Multi-threading. Tests can be executed in paralell (by default it uses paralel.by=classes and thread.count=2)
* Remote/Local. Tests can be started locally or on Grid.
* Different applications can be automated from the template (the project contains single 'app' project)
* Different browsers are supported. (just change variable value in test.properties files or override it via console)
* Console logs were optimized. Now it uses Log4j2. And logs contain only actual info (in comparison with default TestNG logs)
* Template contains some tests.

###How to start
1.execute the following command (just change -DgroupId and -DartifactId):

single row:
```bash
mvn archetype:generate -DarchetypeGroupId=com.mycompany.dy -DarchetypeArtifactId=test-project -DarchetypeVersion=1.0-SNAPSHOT -DgroupId=com.your.company -DartifactId=your-artifact -DarchetypeRepository=http://52.20.121.28:10101/artifactory/snapshots
```
with word wrapping:
```bash
mvn archetype:generate -DarchetypeGroupId=com.mycompany.dy \
-DarchetypeArtifactId=test-project \
-DarchetypeVersion=1.0-SNAPSHOT \
-DgroupId=com.your.company \
-DartifactId=your-artifact \
-DarchetypeRepository=http://52.20.121.28:10101/artifactory/snapshots
```
2.Open generated folder in your SDK.

###How to execute tests
The project contains 2 suites (3 tests) and testng.xml: sampleTests.xml was added to project. So you can execute these 3 tests via the following command:
```bash
mvn clean install -Dtestset=sample.xml
```
just make sure that chromeDriver has been added to your Environement Variables (chrome is default browser for the template). Otherwise please start these tests in Firefox:
```bash
mvn clean install -Ddriver.browser.name=firefox -Dtestset=sample.xml
```
