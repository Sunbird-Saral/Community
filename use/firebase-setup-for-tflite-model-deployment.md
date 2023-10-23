---
description: Firebase setup for TFLite model deployment
---

## Firstly We need an account of firebase to publish and download TFLite model
https://console.firebase.google.com/

### 1. Enter project name:
![](../.gitbook/assets/tflite_setup_step1.png)

### 2. Press on Continue button:
![](../.gitbook/assets/tflite_setup_step2.png)

### 3. Select Account to continue:
![](../.gitbook/assets/tflite_setup_step3.png)

### 4. Press on continue button:
![](../.gitbook/assets/tflite_setup_step4.png)

### 5. Click on Android:
![](../.gitbook/assets/tflite_setup_step5.png)

### 6. Add package name which will get from android/app/build.gradle file then once added package name click on Register button:
![](../.gitbook/assets/tflite_setup_step6.png)

### 7. Download Service json file:
![](../.gitbook/assets/tflite_setup_step7.png)

### 8. Do not add this dependency which is already added in project:
![](../.gitbook/assets/tflite_setup_step8.png)

### 9. Press continue button:
![](../.gitbook/assets/tflite_setup_step9.png)


## Firebase setup for Remote configuration to enable TFLite model
i) If remote config flag is set as true in firebase.\
ii) Then tflite model will be downloaded in mobile once it's timer completed.\
iii) Timer can be change in RemoteConfig.java file.\
iv) Timer will be count in second.

![](../.gitbook/assets/tflite_setup_config.png)

## There are some step for enable remote configuration which are listed below.
### 1. Press on Remote Config
![](../.gitbook/assets/tflite_setup_config1.png)

### 2. Press on Create Configuration
![](../.gitbook/assets/tflite_setup_config2.png)

### 3. Add field name with its data type and save it:
![](../.gitbook/assets/tflite_setup_config3.png)

### 4. Click on Publish Changes
![](../.gitbook/assets/tflite_setup_config4.png)
