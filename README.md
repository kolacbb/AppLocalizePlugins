# AppLocalize Android Plugin
AppLocalize focuses on providing services for individual developers to handle international translation and application localization
## Get Start

### Add AppLocalize to your Android project

#### **Step 1:** Create a AppLocalize project
Before you can add AppLocalize to your Android app, you need to create a AppLocalize project to connect to your Android app.

#### **Step 2:** Config AppLocalize with gradle file
1. In your root-level (project-level) Gradle file (<project>/build.gradle), add the AppLocalize services plugin as a buildscript dependency:
```gradle 
buildscript {

    repositories {
      // Make sure that you have the following two repositories
      google()  // Google's Maven repository
      mavenCentral()  // Maven Central repository
    }

    dependencies {
      ...

      // Add the dependency for the AppLocalize services Gradle plugin
      classpath 'com.google.gms:google-services:4.3.14'
    }
}

allprojects {
  ...

  repositories {
    // Make sure that you have the following two repositories
    google()  // Google's Maven repository
    mavenCentral()  // Maven Central repository
  }
}
```
2. In your module (app-level) Gradle file (usually <project>/<app-module>/build.gradle), add the AppLocalize services plugin:
``` gradle
plugins {
    id 'com.android.application'

    // Add the AppLocalize services Gradle plugin
    id 'top.applocalize.plugin'
    ...
}

appLocalizeStrings {
    key = "6779699421395000" // Replace with your AppLocalize Project key
    token = "ahi58ups96eb80xpclgragakq3vp000"  // Replace with your AppLocalize Project token
}
```

## How to use

### Prerequisties
* Make sure your project uses a version control tool (eg: Git or SVN). AppLocalize will modify the **strings.xml** file in the resource directory, and also create **gen_strings_localized.xml**. If unexpected problems occur during use, make sure you can return to roll back to previous version

* Pre-processing placeholder issues

### Sync strings with AppLocalize
The command will merge the strings.xml file into a multilingual key and upload it to the AppLocalize console, and update the newly created and updated multilingual key in AppLocalize to gen_strings_localized.xml
```gradle
//if your <app-module> named app
./gradlew app:syncStrings 
```






