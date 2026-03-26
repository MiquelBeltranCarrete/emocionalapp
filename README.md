# Emotional App

## Description
Emotional App is an Android application designed to help users manage their emotions and improve mental health. It provides various tools and resources aimed at fostering emotional wellness.

## Requirements
- Android Studio (latest version)
- JDK 8 or later
- Gradle (included with Android Studio)
- Access to the internet for downloading dependencies

## Installation Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/MiquelBeltranCarrete/emocionalapp.git
   cd emocionalapp
   ```
2. Open the project in Android Studio.
3. Sync the project with Gradle files to download required dependencies.

## Build Instructions
### Building the APK
1. In Android Studio, select `Build` from the menu.
2. Then choose `Build Bundle(s) / APK(s)` > `Build APK(s)`.
3. Once the build is complete, you can find the APK in the `output` folder.

### Building the App Bundle
1. Go to `Build` in the menu.
2. Select `Build Bundle(s) / APK(s)` > `Build Bundle(s)`.
3. The App Bundle will be generated and can be found in the `output` folder.

## Signing Configuration
To publish your app on the Google Play Store, you'll need to sign your app using a release key:
1. Generate a signing key using the following command:
   ```bash
   keytool -genkey -v -keystore your-release-key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias your-key-alias
   ```
2. In `build.gradle (Module: app)`, configure the signing:
   ```groovy
   android {
       signingConfigs {
           release {
               keyAlias 'your-key-alias'
               keyPassword 'your-key-password'
               storeFile file('path/to/your-release-key.jks')
               storePassword 'your-store-password'
           }
       }
       buildTypes {
           release {
               signingConfig signingConfigs.release
           }
       }
   }
   ```

## Project Structure
- **app/**: Contains the main source code and resources of the application.
- **build.gradle (Project)**: Project-level Gradle file.
- **build.gradle (Module: app)**: Module-level Gradle file containing application-specific dependencies and configurations.
- **gradle/**: Contains Gradle wrapper files.
- **settings.gradle**: Contains the settings for the project configuration.

For more details, refer to the Android developer documentation and guidelines for publishing on the Google Play Store.