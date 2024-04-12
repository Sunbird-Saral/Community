---
description: >-
  Saral allows quick and reliable capture of information from physical formats
  to structured, digital formats.
---

# Saral Production-Environment User Installation Guide

Using Saral results in extensive savings in terms of time and effort, when information from physical sources (such as paper) needs to be digitised and stored in a structured manner for analysis.

## Prerequisites

1\) Since, backend infra for Saral is hosted on AWS, user Must have a valid AWS account.

2\) Saral is a mobile application and its APK can be generated from source code. Process for the same can be found [here](https://saral.sunbird.org/use/generating-apk-from-source-code). Provision has been made such that adopters can create their own configurations for Saral application. Refer [here](https://saral.sunbird.org/use/update-base\_url-apkurl-in-apk) and [here](https://saral.sunbird.org/use/generate-aab-app-bundle-from-source-code) to know about detail guide for the same.&#x20;

User can publish their own configured saral app on Google play sore. Please refer [here](https://saral.sunbird.org/use/google-play-store-app-publish-recommendations) to know process to set it up.

Saral provides facility to pull varied analytical reports using Firebase Application. Please refer [here](https://saral.sunbird.org/use/firebase-setup-for-tflite-model-deployment) to know process to set Firebase account and configure it. Once Firebase account has been setup, refer [here](https://saral.sunbird.org/use/firebase-setup-for-saral-app-telemetry) to konw how to update it in source code. Please note, mobile APK needs to be rebuild for changes to get reflected.

3\) Saral app supports pre-configured template layouts. User is advised to take print outs of the same for their use. Current application version supports Assessment and layout for the same can be found attached below.&#x20;

{% file src="../../.gitbook/assets/Assesment sheet layout.pdf" %}
Saral Assessment-Sheet Layout
{% endfile %}

Latest published versions of all layouts will be available at below mentioned location.

{% embed url="https://github.com/Sunbird-Saral/Project-Saral/tree/v1-develop/docs/layout-design/Design" %}

Along with template files, ROI Json file are available at below location.

{% embed url="https://github.com/Sunbird-Saral/Project-Saral/tree/v1-develop/v1.0/backend/data/layout" %}

All layouts are configurable. Please refer [here](https://saral.sunbird.org/use/layout-configuration) to configure your own layout and create corresponding ROI file for it.

4\) Download and install MongoDB and Mongo Compass for your OS (Windows, mac, Linux) from below link&#x20;

{% embed url="https://www.mongodb.com/docs/compass/current/install/" %}
Download and Install Compass
{% endembed %}

```
# To Import the public key used by the package management system run 
sudo apt-get install gnupg curl

# To import the MongoDB public GPG key from https://www.mongodb.org/static/pgp/server-7.0.asc, run the following command
curl -fsSL https://www.mongodb.org/static/pgp/server-7.0.asc | \
   sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg \
   --dearmor
   
# To Create a list file for MongoDB run  
sudo touch /etc/apt/sources.list.d/mongodb-org-7.0.list

# To add Mongo Repo to package manager run 
echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list

# To Reload local package database run
sudo apt-get update

#To Install the MongoDB packages run
sudo apt-get install -y mongodb-org
```



5\) Postman Collections

{% file src="../../.gitbook/assets/saral-frontend.postman_collection.json" %}
Postman Collections
{% endfile %}

6\) Cloud Infra provisioning requirement and costing

Please refer [here](https://saral.sunbird.org/saral-easy-installer/reference-documents/saral-infra-requirements-and-associated-cost) for minimum infra required to be provisioned for Saral Dev environment and the monthly costing associated with it.

Please refer [here](https://saral.sunbird.org/saral-easy-installer/reference-documents/saral-infra-cost-benefit-analysis) to understand different combination of Infra that can be provisioned for Saral and its usage scenario details along with the cost associated with it. This will help user to choose which infra is suitable as per need.

Please note, there is need to whitelist server IP/domain for application to work. Please refer [here](https://docs.google.com/document/d/1pLTSwwak-u9CGl1IMyFbeFmgHH69kG\_e/edit#heading=h.3znysh7) to understand steps for the whitelisting

Once all above steps are completed, Saral will be ready to use.

Refer [here](https://saral.sunbird.org/saral-implementation-manual)[ ](https://saral.sunbird.org/step-by-step-guide-to-use-saral)to know more about implementation details of Saral.

Refer [here](https://saral.sunbird.org/step-by-step-guide-to-use-saral) to know about user User Experience of Saral.
