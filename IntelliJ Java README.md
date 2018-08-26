# IntelliJ Setup

## Missing src folder
For the Mac the solution is to go manually into: Intellij IDEA -> Preferences -> Build, Execution, Deployment -> Build Tools -> Gradle -> check the "Create directories for empty content roots automatically".

## Gradle

To run `gradlew` from terminal, first execute

`gradle wrapper`

then

`./gradlew`

