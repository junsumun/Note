# React Native

## Table of Contents
1. [Basic Setup](#basic-setup)
   * [Creating a new project](#creating-a-new-project) 
   * [Use .env file in React Native](#use-env-file-in-react-native)
2. [Troubleshooting](#troubleshooting)
    * [Build Errors](#build-errors)
        * [Target Support Files Pods error](#target-support-files-pods-error)
        * [react-native-dotenv Configuration error](#react-native-dotenv-configuration-error)

## Expo CLI

Open a different IOS simulator 
```
$ shift + i
```
## Basic Setup
### Creating a new Project
```bash
npx react-native init <project name>
```

### Use \.env file in React Native
Using a .env file allows a project to exclude configuration information from the codebase. 

1. Create **.env** file in the root directory of a project
2. Save the configuration information inside the .env file
    ```bash
    # .env
    # firebase config example
    API_KEY=xxxx
    AUTH_DOMAIN=xxxx
    PROJECT_ID=xxxx
    STORAGE_BUCKET=xxxx
    MESSAGING_SENDER_ID=xxxx
    APP_ID=xxxx
    MEASUREMENT_ID=xxxx
    ```
3. Install **react-native-dotenv** pacakge
    ```
    $ npm install react-native-dotenv
    ```
4. Create **.babelrc** file in the root directory of a project
5. Include the react-native-dotenv package as a babel plugin
   ```json
   {
     "plugins": [
       ["module:react-native-dotenv"]
     ]
   }
   ```
6. Import the information in the .env file
    ```javascript
    import {
      API_KEY,
      AUTH_DOMAIN,
      PROJECT_ID,
      STORAGE_BUCKET,
      MESSAGING_SENDER_ID,
      APP_ID,
      MEASUREMENT_ID,
    } from '@env'
    ```
## Troubleshooting

### Build Errors

**Title:**
#### Target Support Files Pods error

**Symptom:**

Cloned a react native project and opened a <project name>.xcworkspace file in the /ios directory to build and run the application on a local ios device. Build fails on Xcode with the following error </br>

<img width="684" alt="Build Error on Xcode" src="https://user-images.githubusercontent.com/24871462/126023314-5a3adf5d-6b26-480b-a993-12d5ccb06290.png">

**Solution:**

This error happenes due the wrong cocoapods in the project.
Therefore, remove cocoapods from the project
```bash
$ pod deintegrate
$ sudo gem install cocoapods -clean
$ pod clean
```
Open the xcode project by clicking <filename>.xcodeproj and remove Pods directory from the project. </br>

<img width="273" alt="Remove Pods directory" src="https://user-images.githubusercontent.com/24871462/126023540-b63b7688-ab68-43a4-acbc-96ad2c838022.png">
   
```bash
$ pod setup
$ pod install
```

</br>

**Title:**
#### react-native-dotenv Configuration error

**Symptom:**

Added react-native-dotenv module to a project.

<img width="393" alt="react-native-dotenv module config error" src="https://user-images.githubusercontent.com/24871462/126273873-6ec90116-04f7-4143-abd1-45e514e0749a.png">

**Solution:**

react-native-dotenv packaged has changed a way to setup from v0.x to v2.x </br>
Therefore, follow the [Migration Guide](https://github.com/goatandsheep/react-native-dotenv/wiki/Migration-Guide).
