---
description: Saral App Debug Tips
---

# Saral App Debug Tips

## SaralSdk log tracing from Android studio

In Android studio,open Logcat view at the bottom while running android application. Use "SrlSdk" as a filter in Logcat view to monitor Saral SDK logs. This is easy way to monitor whats happening within [SaralSDK](../engage/saral-sdk-source-code-repository.md) code.

## Debug React Native Layer

1. Install `react-native-cli` using the below command.

`npm install --global react-native-cli`

2\. Run the below command from the frontend folder

`react-native run-android`

3\. Run the below command to trace logs.

`react-native log-android`

## Android logs

> Install [https://developer.android.com/studio/command-line/adb](https://developer.android.com/studio/command-line/adb)

> use the below log command to monitor android logs.

`adb log-cat`

## SaralSdk log tracing from Android studio

In Android studio,open Logcat view at the bottom while running android application. Use "SrlSdk" as a filter in Logcat view to monitoring Saral SDK logs. This is easy way to monitor whats happening with in SaralSDK code.

## Navigate to the Android device path to check files stored.

`adb shell cd <Path>`

> Example: `storage/emulated/0/Android/data/com.saralapp/files/Download`

``

## Capture scanned images from Android phone

* > Set debug option to true to store the image in android mobile. Modify below java file under /saralsdk and change below highlighted flags to true.

SaralSDKOpenCVScannerActivity.java

> > ```
> >    mTableCornerDetection           = new TableCornerCirclesDetection(true);
> >    mDetectShaded                   = new DetectShaded(true);
> > ```

* > With the above changes, run the scan on the mobile.
* > Use the below command to grab the android level logs and search for 'SrlSDK::CVOps: Saving file:' and 'SrlSDK::DetectShaded: Saving file:'. This will give you path to where the saved images are stored in your android phone.

`adb logcat`

* > Use the below command to pull the images finally. `adb pull <image path in android phone found in above logs>` example: `adb pull /storage/emulated/0/Android/data/com.saralapp/files/Download/table_4Fg.jpg`
