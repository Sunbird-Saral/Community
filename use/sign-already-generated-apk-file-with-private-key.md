---
description: Sign existing APK file with keystore
---

# Sign already generated APK file with private Key

Refer [workspace-setup-playbook.md](workspace-setup-playbook.md "mention")to setup Android on the developer machine.

Execute below command from a terminal:

**`$ANDROID_HOME`**`/build-tools/{build-tool-version}/apksigner sign --ks <keystore.jks> --out <saral-release-signed.apk> <saral-app-unsigned-aligned.apk>`

OR

**`%ANDROID_HOME%`**`/build-tools/{build-tool-version}/apksigner sign --ks <keystore.jks> --out <saral-release-signed.apk> <saral-app-unsigned-aligned.apk>`

Example:

**`$ANDROID_HOME`**`/build-tools/30.0.2/apksigner sign --ks my-release-key.jks --out saral-release-signed.apk saral-app-unsigned-aligned.apk`

Please enter keystore password when prompted. This will generate signed apk with the name provided in  `--out`  parameter.
