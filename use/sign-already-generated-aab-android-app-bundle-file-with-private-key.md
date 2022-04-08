# Sign already generated AAB(Android App Bundle) file with private key

Make sure JAVA is configured on your machine and `jarsigner` command is available.

Use below command to sign the AAB file. This command will prompt you for keystore passphrase or password.

`jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore [path to keystore] -signedjar [name for the output signed file].aab [path to unsigned aab] [keystore alias]`

**Example:**

`jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore hwrecog-upload-key.keystore -signedjar app-release-signed.aab app-release.aab hwrecog-key-alias`
