---
description: Saral App Debug Tips
---

# Saral App Debug Tips

## SaralSdk log tracing from Android studio

In Android studio,open Logcat view at the bottom while running android application. Use "SrlSdk" as a filter in Logcat view to monitor Saral SDK logs. This is easy way to monitor whats happening within [SaralSDK](../source-code/saral-sdk-source-code-repository.md) code.

## Debug React Native Layer

1. Install `react-native-cli` using the below command.

`npm install --global react-native-cli`

&#x20;2\. Run the below command from the frontend folder

`react-native run-android`

3\. Run the below command to trace logs.

`react-native log-android`

## Android logs

> Install [https://developer.android.com/studio/command-line/adb](https://developer.android.com/studio/command-line/adb)

> use the below log command to monitor android logs.

`adb logcat`
