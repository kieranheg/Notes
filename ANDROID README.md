# Android Setup and Development Notes for Ubuntu

## Setup

1. Install Android Studio as described here: https://developer.android.com/studio/install.html
2. Increase the IDE memory to 2048MB by following these instructions: http://tools.android.com/tech-docs/configuration
3. Fix the Gradle build problem 

```Exception in thread "png-cruncher_8" java.lang.RuntimeException: Timed out while waiting for slave aapt process, try setting environment variable SLAVE_AAPT_TIMEOUT to a value bigger than 5 seconds
    at com.android.builder.png.AaptProcess.waitForReady(AaptProcess.java:104)
    at com.android.builder.png.QueuedCruncher$1.creation(QueuedCruncher.java:107)
    at com.android.builder.tasks.WorkQueue.run(WorkQueue.java:206)
    at java.lang.Thread.run(Thread.java:745)```

by running

```sudo apt-get install lib32z1```

4. In your app's top-level build.gradle file, you need to specify these libraries as dependencies:

```dependencies {
    // Required -- JUnit 4 framework
    testCompile 'junit:junit:4.12'
    // Optional -- Mockito framework
    testCompile 'org.mockito:mockito-core:1.10.19'
}```
