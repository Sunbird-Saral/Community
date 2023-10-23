---
description: Firebase setup for Saral App Telemetry
---

# Setup react native side

some libraries have to be installed to add firebase Google Analytics and firebase Google Crashlytics in react native

```
npm i @react-native-firebase/app
npm i @react-native-firebase/analytics
npm i @react-native-firebase/crashlytics
```
## Add In your module (app-level) Gradle file under dependencies

```
implementation "com.google.firebase:firebase-iid:21.1.0"
implementation "com.google.firebase:firebase-bom:31.2.2"
implementation 'com.google.firebase:firebase-analytics'
implementation ('com.google.firebase:firebase-iid:21.1.0'){
transitive = true}
```
## On the top of (app-level) Gradle file add this line

```
apply plugin: 'com.google.gms.google-services'
apply plugin: 'com.google.firebase.analytics'
apply plugin: 'com.google.firebase.crashlytics'
```
## Add In your root-level (project-level) Gradle file under dependencies

```
classpath("com.google.gms:google-services:4.3.3")
classpath "com.google.firebase:firebase-iid:19.0.0"
classpath 'com.google.firebase:firebase-crashlytics-gradle:2.7.1'
```
## Add In your frontend/SaralApp/android/app/src/main/AndroidManifest.xml

```
< meta-data android:name="firebase_analytics_collection_enabled" android:value="true" />

< meta-data android:name="firebase_crashlytics_collection_enabled" android:value="true" />
```
## To link the app to firebase, go to the firebae console and make project
[firebase console](https://firebase.google.com/)

## To link the app after the project is created 
Add google-service.json under android/app

# Firebase Analytics Run time configuration
for enable or disable at run time environment firebase_analytics_collection_enabled in App.js file frontend/SaralApp/App.js

You need to add flag **isFBAnalyticsEnabled** in login api
> > /schools/login

response from api
> > "school": { "storeTrainingData": true, "name": "Dummy school 4", "schoolId": "u002", "state": "up", "district": "district1", "autoSync": true, "autoSyncFrequency": 900000, "tags": true, "autoSyncBatchSize": 10, "offlineMode": true, "isAppForceUpdateEnabled": false, "isFBAnalyticsEnabled": true, "userId": "u002" }

Add in code useEffect(async()=>{ let hasFBAnalytics = await getLoginData();
```
const hasFBAnalyticsValue = hasFBAnalytics.school && hasFBAnalytics.school.enableFBAnalytics
if(hasFBAnalyticsValue != null){
if (__DEV__) {
  analytics().setAnalyticsCollectionEnabled(hasFBAnalyticsValue);
  crashlytics().setCrashlyticsCollectionEnabled(hasFBAnalyticsValue);}  else{
  analytics().setAnalyticsCollectionEnabled(hasFBAnalyticsValue);
  crashlytics().setCrashlyticsCollectionEnabled(hasFBAnalyticsValue);}}},[])
```
**DEV** variable. By default if you run your app with **npx react-native run-android**, it will run in Debug mode and **DEV** will be true. In release mode, **DEV** will be false.
here **hasFBAnalyticsValue** is the flag which will come from backend as boolean.
**If mobile is not connected with internet then data will not pushed to the firebase**

After adding all dependencie rebuild the app using **npx react-native run-android**

# Firebase Pricing plans
Get started at no cost,then pay as you go.
Firebase service will be free of cost for some time but after some time events triggered it will be chargeable
here is the link for know all plans [pricing plans](https://firebase.google.com/pricing#blaze-calculator)


