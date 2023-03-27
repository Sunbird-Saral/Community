# Firebase Analytics and Crashlytics

Firebase Analytics and Crashlytics can be enabled/disabled using `/schools/login` API by setting `isFBAnalyticsEnabled` flag to true or false. Refer below sample response from `/schools/login` API. This feature will will be available starting from Saral App release `v1.5.8`

```
{
    "name": "Dummy school 1",
    "schoolId": "u001",
    "password": "xxxxx",
    "state": "up",
    "autoSync": false,
    "autoSyncFrequency": 600000,
    "storeTrainingData": true,
    "tags": true,
    "supportEmail": "abc@gmail.com , xyz@gmail.com",
    "offlineMode": true,
    "isAppForceUpdateEnabled": true,
     "isFBAnalyticsEnabled": true
  }
```



Refer to firebase pricing @ [https://firebase.google.com/pricing](https://firebase.google.com/pricing)
