---
description: >-
  Saral allows quick and reliable capture of information from physical formats
  to structured, digital formats using mobile devices.
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# User Experience Guide for Saral Non-Prod-Environment

1\) Saral is a mobile application and can be download from Play Store (Saral-App). Alternatively User can download the App from the below mentioned link.

{% embed url="https://drive.google.com/file/d/1vQVH5QRvkUqzeClcmb1d-Fw2iOf0kn36/view?usp=sharing" %}

2\) Saral uses pre-defined template Layouts for scanning. Such templates should be available with user. User can find the supported sample mark-sheet/assessment template layouts attached below. User is advised to take print outs of the same. Avoid using photocopies as unclear photocopies are prone to error while scanning.



{% file src="../.gitbook/assets/Assesment sheet layout.pdf" %}
Saral Assessment-Sheet Layout
{% endfile %}

{% file src="../.gitbook/assets/Attendance-sheetLayout.pdf" %}
Saral Attendance-Sheet Layout
{% endfile %}

Alternatively, latest published versions of all layouts will be available at below mentioned location.

{% embed url="https://github.com/Sunbird-Saral/Project-Saral/tree/v1-develop/docs/layout-design/Design" %}

Also layout specification and configuration as well as design guidelines for ROI can be found [here](https://saral.sunbird.org/learn/specifications/layout-specification) and [here](https://saral.sunbird.org/use/layout-configuration) and [here](https://saral.sunbird.org/use/layout-design-guidelines).

3\) Once user is ready with above mobile application and properly filled print outs, user is ready to convert their physical data into structured digital data.

Saral has capability to support multiple OCR and OMR based forms digitisation. Below is the workflow guide for Assessments. Similar guide for Admission forms can be found [here](https://saral.sunbird.org/learn/features/capture-admissions-record).

* Open Saral App on your mobile device and login to Saral Mobile App with the below Credentials

&#x20;       Username: u002

&#x20;       Password: tarento@123

* Select option Assessments
* On the next page, select the following and click on Submit
  * Class - 2
  * Section - D
  * Subject - Hindi
  * Paper Set - B
* User will see list of students and an option to make attendance for each student. Mark attendance and click on Next to see Summary page before actual scan starts.
* Start scanning all your assessment sheets.
* You can verify your scan sheets and edit them if required before submitting all your data.
* Click on Submit to complete the process.

4\) Once data is submitted, it is digitised into structured format and saved into back-end database. User can view structured digital data by connecting to database using below mentioned details.

* Download and install MongoDB Compass using details mentioned [here](https://www.mongodb.com/docs/compass/current/install/).&#x20;
* Connect to MongoDB database using URL  ¨mongodb://3.110.36.135:27017¨
* Once connected, user can view digitised data

User can refer [here](https://saral.sunbird.org/learn/videos/feature-explanation) to know more about Saral features

User can refer here for Saral app [usage guidelines](https://saral.sunbird.org/use/saral-app-usage-guidelines).





