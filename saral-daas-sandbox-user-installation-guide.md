---
description: >-
  Saral allows quick and reliable capture of information from physical formats
  to structured, digital formats.
---

# Saral Dev-Environment User Installation Guide

Using Saral results in extensive savings in terms of time and effort, when information from physical sources (such as paper) needs to be digitised and stored in a structured manner for analysis.

## Prerequisites

1\) Since, backend infra for Saral is hosted on AWS, user Must have a valid AWS account.

2\) Saral is a mobile application and its APK can be generated from source code. Process for the same can be found [here](https://saral.sunbird.org/use/generating-apk-from-source-code). Provision has been made such that adopters can create their own configurations for Saral application. Refer [here](https://saral.sunbird.org/use/update-base\_url-apkurl-in-apk) and [here](https://saral.sunbird.org/use/generate-aab-app-bundle-from-source-code) to know about detail guide for the same.&#x20;

3\) Saral app supports pre-configured template layouts. User is advised to take print outs of the same for their use. Current application version supports Assessment and layout for the same can be found attached below.&#x20;

{% file src=".gitbook/assets/Assesment sheet layout.pdf" %}
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

5\) Saral user docker for containerisation and hence, to Install docker on Ubuntu Linux use below details

```
# To Update the package index run
sudo apt update

# To Install prerequisites for Docker run
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common

# To Add Docker GPG key run
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# To Add Docker repository run
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# To Update the package index again (with Docker repository) run
sudo apt update

# To Install Docker run
sudo apt install -y docker-ce docker-ce-cli containerd.io

# To Add the current user to the docker group (to run Docker commands without sudo) run
sudo usermod -aG docker $USER

# To Install Docker Compose run
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

# To Print Docker and Docker Compose versions run
docker --version
docker-compose --version
```

6\) Create a docker-compose.yml file and paste below code snippet in it. Please make sure to replace your MongoDB instance IP in the below code snippet.

```
version: '2.4'
services:
  sandbox:
    image: jonathanrogers/saral-backend:1.6.2
    container_name: sandbox
    environment:
      - PROFILE=dev
      - PORT=3005
      - MONGODB_URL=mongodb://<Insert your actual Mongo DB IP here>:27017/saralv1newdb
      - JWT_SECRET=SARALDATA_NODE
      - MONGODB_POOL_SIZE=50
      - MIN_MONGODB_POOL_SIZE=30

    ports:
      - "3005:3005"
```

To execute docker compose file, please execute below mention command in your VM terminal

[**`sudo docker compose up -d`**](#user-content-fn-1)[^1]

7\) Use NGINX to setup Domain Name and SSL Certificate. Refer [here](https://docs.google.com/document/d/1Rz2nhyc\_8oy56fwVHTO18ZbBT2Tss-ii8SbvqeNFiEY/edit?usp=sharing) for installation guide.

8\) Cloud Infra provisioning requirement and costing

Please refer [here](https://docs.google.com/spreadsheets/d/1IrQqBEMG\_phASHvORvkQ8qRl30hndvj4yBsDCl6eoho/edit?usp=sharing) for minimum infra required to be provisioned for Saral sand box and the monthly costing associated with it.

Please note, there is need to whitelist server IP/domain for application to work. Please refer [here](https://docs.google.com/document/d/1pLTSwwak-u9CGl1IMyFbeFmgHH69kG\_e/edit#heading=h.3znysh7) to understand steps for the whitelisting

Once all above steps are completed, Saral will be ready to use.

Refer [here](https://saral.sunbird.org/saral-implementation-manual)[ ](https://saral.sunbird.org/step-by-step-guide-to-use-saral)to know more about implementation details of Saral.

Refer [here](https://saral.sunbird.org/step-by-step-guide-to-use-saral) to know about user User Experience of Saral.

[^1]: 
