---
description: App force update feature
---

# App Force Update



> App force updates when a new version of the app is available in the play store. This feature is available from release `v1.5.7` and above.

1. `isAppForceUpdateEnabled` flag set to true in the `POST /schools/login` API response will enable this feature.
2. If the play store has a new version of the app , then in app there would an alert which shows user an alert message to force update the app.
3. If there is any error occurred while populating alert message of app force update, support logs which will capture failure logs.
4. Multiple users on the same device , data will be retained after the update. If there is no data struture change between versions of the app , data stored in the device before update can be pushed to backend after app upgrade.

```javascript

{
    "name": "Dummy school 1",
    "schoolId": "u001",
    "password": "tarento@123",
    "state": "up",
    "autoSync": false,
    "autoSyncFrequency": 600000,
    "storeTrainingData": true,
    "tags": true,
    "supportEmail": "abc@gmail.com , xyz@gmail.com",
    "offlineMode": true,
    "isAppForceUpdateEnabled": true

  }
```



![appForceUpdate](https://user-images.githubusercontent.com/86999055/203745089-11a24f18-69f6-4f22-805a-35439de93ed0.jpg)
