# React Native

## Table of Contents
1. Placeholder
2. [Troubleshooting](#troubleshooting)
    * [Build Errors](#build-errors)
        * [Target Support Files Pods error](#target-support-files-pods-error)


## Expo CLI

Open a different IOS simulator 
```
$ shift + i
```

## Troubleshooting

### Build Errors
#### Target Support Files Pods error
#### Symptom
Cloned a react native project and opened a <project name>.xcworkspace file in the /ios directory <br/>
to build and run the application on a local ios device. Build fails on Xcode with the following error.

<img width="684" alt="Build Error on Xcode" src="https://user-images.githubusercontent.com/24871462/126023314-5a3adf5d-6b26-480b-a993-12d5ccb06290.png">

#### Solution
This error happenes due the wrong cocoapods in the project.
Therefore, remove cocoapods from the project
```bash
$ pod deintegrate
$ sudo gem install cocoapods -clean
$ pod clean
```
Open the xcode project by clicking <filename>.xcodeproj and remove Pods directory from the project.

<img width="273" alt="Remove Pods directory" src="https://user-images.githubusercontent.com/24871462/126023540-b63b7688-ab68-43a4-acbc-96ad2c838022.png">
   
```bash
$ pod setup
$ pod install
```
