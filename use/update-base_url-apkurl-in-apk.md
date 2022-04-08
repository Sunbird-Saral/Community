# Update BASE\_URL,apkURL in APK

From unix/mac terminal open apk attached with release in `vi` editor and update `BASE_URL` using below steps.

1\) Download APK file from release notes Assets section into \<target\_folder>.                                   For example for `v1.5.0` release download apk from  [https://github.com/Sunbird-Saral/Project-Saral/releases/download/v1.5.0/saral-app-unsigned-v1.5.0.apk](https://github.com/Sunbird-Saral/Project-Saral/releases/download/v1.5.0/saral-app-unsigned-v1.5.0.apk)

2\) Open Terminal or shell in \<target\_folder> and use below `vi` command to open apk in `vi` editor.

&#x20;`vi saral-app-unsigned-v1.5.x.apk`&#x20;

3\) Press `Esc` key and type `/index.android.bundle` and presss `Enter` key to locate `assets/index.android.bundle` file and press `Enter` key. This will open up the file for editing.

4\) Search for `TO_BE_REPLACED` string and replace it with target BASE\_URL. For example \`[https://saral-statename.anuvaad.org](https://saral-statename.anuvaad.org)\`

5\) Press `Esc` key and enter `:wq` to save and go to file list the `vi` editor. Press `Esc` key and enter `:q` to quit the `vi` editor.

6\) APK file should be updated with target BASE\_URL with above steps.

7\) Search for `apkURL` and change the value to actual Playstore URL based on the implementation.
