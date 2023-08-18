# Getting Started

The below steps will get you going with Saral using an existing layout

### Install backend
1. Install the Saral backend on a server. [This page](https://github.com/Sunbird-Saral/Project-Saral/blob/main/v1.0/backend/README.md) has the instructions to build and deploy the docker images
2. Once the backend is up verify that you're able to view the swagger docs at $BASE_URL/api-docs/saral/frontend/
3. Create the Users, Schools, Sections, Classes and an Exam
4. Postman collections are available here - https://github.com/Sunbird-Saral/Project-Saral/tree/main/v1.0/backend/test

### Create APK
Once the backend is up, create a APK file that can be installed in android phones. Instructions to create a build are available on the these links [Build APK](https://saral.sunbird.org/use/generating-apk-from-source-code), [Update base URL](https://saral.sunbird.org/use/update-base_url-apkurl-in-apk)


### Create and print your SARAL Layout
Some sample layouts are on this page towards the end - https://saral.sunbird.org/use/layout-design-guidelines 
Pick a layout and print it out

### Create ROIs for your layout
1. Use Microsoft VoTT to tag the ROIs in the printed layout
2. Use the Jupyter notebook along with the data from VoTT and generate the ROI json
3. Upload the ROI json to the exam using the API

This page has detailed instructions for this step - https://saral.sunbird.org/use/layout-configuration

### Scan layout using the Saral App
1. Create a few prints of the layout and mark the student IDs and answers on them
2. Login to the app using one of the users
3. Choose the exam and students
4. Start scanning

### View data captured via scan
For completed scans, the data wil be stored in MongoDB. The scan data can be accessed via the `getSavedScan` API or by directly accessing the database.
