# Offline mode

This feature will be avilable from Saral releases v1.5.6 and above.

> When we login into the app backend should have an offlineMode flag true, offline mode will be enabled. Also as this feature caches api response as needed , this will occupy additional mobile local storage. Please ensure sufficient storage is available on the device.&#x20;

```
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
"offlineMode": true
```

},

> When the internet is available, the user has to navigate to all the screens with specific selections for the first time. During subsequent app usage, the internet is not required to navigate and scan using the app.

> When the internet is not available on the device, the user can navigate to screens and selections tried by the user when the internet is available.

> In offline mode we can scan the layout but we cannot save it . It will be stored in local storage and when net is available then we can hit save all scan Api

> user will be able to log in through Login Api Cache by entering schoolD and password if any school hasn't cache then it would not logged in and will throw an error "You don't have cache".

> in offline mode if user click on log-out it will just navigate to log-in page. if user close the app and bring back the app that will be logged in the same school. logout we don't erase any data.we have given an interface to switch multiple school without loosing marks data and api cache.

> **we have remove user cache**: it will erase the logged in school's api cache except the marks.

![IMG\_20221017\_130043](https://user-images.githubusercontent.com/91952702/196121468-eeb521c7-1f64-4b3d-8227-8d61f31824ab.jpg)

***

> **remove all user cache**: it will erase the all schools api cache except the marks.

![IMG\_20221017\_130104](https://user-images.githubusercontent.com/91952702/196121542-8a1de48a-37d0-42cf-b705-e404978f62c6.jpg)

***

> in multiple user case if u logout current logged in school while you have network only logged in school's data will be stored in db and rest of data will be there in local and you can go one by one school and save it

> autosync process will be disabled when offline mode is active.

> user will be able to log in through Login Api Cache by entering schoolD and password if any school hasn't cache then it would not logged in and will throw an error "You don't have cache".
