# Notes on TDD with Android Studio

See the pre-requisites in https://www.jetbrains.com/help/idea/2016.1/tutorial-test-driven-development.html

Also refer to the following tutorial http://www.vogella.com/tutorials/AndroidTesting/article.html

## Android project organization for tests

The preferred way of organizing tests is based on a convention. In your application project, you should use the following base folder structure for your code organization, this is also the structure the project wizard creates.

`app/src/main/java` for your source code of your main application build  
`app/src/test/java` for any unit test which can run on the JVM  
`app/src/androidTest/java` for any test which should run on an Android device  

## Basic JUnit 4 TDD

### Imports

```
import static org.junit.Assert.*;

import org.junit.After;
import org.junit.Before;
import org.junit.Test;
```

### JUnit Testing

#### Create a Test

1. Right click on the package you want to create the test in and select `New | Java Class`.
2. To creat a new test case, with the cursor placed somewhere inside the class’s curly braces, press `Alt+Insert`, and select `JUnit 4`.
3. Using TDD, write the test body, _but_ follow these rules to keep the compiler happy:
  1. Use `Alt+Enter` to add the target __class__ that will be tested 
  2. Use `Alt+Enter` to add the target __method__ that will be tested
  3. Use IntelliJ _refactoring tools_ `Ctrl-Shift-Alt-T` as required

#### Run the Test

1. When following a TDD approach, typically you go through a cycle of Red-Green-Refactor. You’ll run a test, see it fail (go red), implement the simplest code to make the test pass (go green), and then refactor the code so your test stays green and your code is sufficiently clean.
2. From inside the test, press `Ctrl+Shift+F10` to run this individual test.
3. The results will be shown in the __Run__ dialog. The test name will have an icon next to it - either red for an exception, or yellow for an assertion that fails. For either type of failure, a message stating what went wrong is also shown.

#### Implementing the Code

1. The next step is to make the tests pass, which means implementing the simplest thing that works.
2. You can navigate to the code being tested using the usual methods - clicking through on the method name, pressing `Ctrl+Alt+B` while the cursor is on the method name, or pressing `Ctrl+Shift+T` to switch between the test and the production code.
3. Re-run the test, using `Shift+F10` to re-run the last test.

#### Run the Test Suite

1. Re-run the last test only using `Shift+F10`.
2. Using `Ctrl-Shift+F10` re-run _all_ the last tests in that suite.
3. Select the JUnit test package, to run all the test suites.

## Resources

Use the following strtucture to access XML resources from JUnit:

`src\test\java\<package-name>\<fileTest.java>`
`src\test\resources\xml\<file.xml>`

Read the file as below:

```
private static final String SMALL_STRAVA_DATA_FILE = "xml/ride1.xml";

@Test
public void testXmlHandler() throws Exception {
    InputStream inputStream =
        this.getClass().getClassLoader().getResourceAsStream(SMALL_STRAVA_DATA_FILE);
```
        
