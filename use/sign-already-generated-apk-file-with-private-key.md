# Sign already generated APK file with private Key

Execute below command from terminal:

**`$ANDROID_HOME`**`/build-tools/{build-tool-version}/apksigner sign --ks <keystore.jks> --out <saral-release-signed.apk> <saral-app-unsigned-aligned.apk>`

OR

**`%ANDROID_HOME%`**`/build-tools/{build-tool-version}/apksigner sign --ks <keystore.jks> --out <saral-release-signed.apk> <saral-app-unsigned-aligned.apk>`

Example:

**`%ANDROID_HOME%`**`/build-tools/30.0.2/apksigner sign --ks my-release-key.jks --out saral-release-signed.apk saral-app-unsigned-aligned.apk`
