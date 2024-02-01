---
description: >-
  Saral allows quick and reliable capture of information from physical formats
  to structured, digital formats.
---

# Saral-DaaS-Sandbox-User-Installation-Guide

Using Saral results in extensive savings in terms of time and effort, when information from physical sources (such as paper) needs to be digitized and stored in a structured manner for analysis.

## Prerequisites

1\) Download App from Play Store (Saral-App). Alternatively User can download the App from the below mentioned link.

{% embed url="https://tarento-my.sharepoint.com/:u:/p/rashmi_ankalgi/Efu7Dq-3SadImhh3iUF49vgBXaZq39AoJoH4KiylEnRyLQ" %}
Saral Mobile app apk
{% endembed %}

2\) User Must have a valid AWS account.

3\) Template Layouts should be available with user. You can find the supported sample Template layouts here. User is advised to take print outs of the same.&#x20;

{% file src=".gitbook/assets/Attendance-sheetLayout.pdf" %}
Saral Attendance-Sheet Layout
{% endfile %}

{% file src=".gitbook/assets/Assesment sheet layout.pdf" %}
Saral Assessment-Sheet Layout
{% endfile %}

4\) Download and install Mongo Compass for your OS (Windows, mac, Linux) from below link&#x20;

{% embed url="https://www.mongodb.com/docs/compass/current/install/" %}
Download and Install Compass
{% endembed %}

5\) Install docker on Ubuntu Linux using below details

```
#!/bin/bash

# Update the package index
sudo apt update

# Install prerequisites for Docker
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common

# Add Docker GPG key
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# Add Docker repository
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Update the package index again (with Docker repository)
sudo apt update

# Install Docker
sudo apt install -y docker-ce docker-ce-cli containerd.io

# Add the current user to the docker group (to run Docker commands without sudo)
sudo usermod -aG docker $USER

# Install Docker Compose
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

# Print Docker and Docker Compose versions
docker --version
docker-compose --version
```

6\) Use below link from the public repository to download docker compose file.

Below is the sample file for the reference only. It is advisable to use latest available version from the public repository link mentioned above.

```
version: "2.4"

services:
  sandbox:
    image: jonathanrogers/saral-backend:1.6.2
    container_name: sandbox
    environment:
      - PROFILE=dev
      - PORT=3005
      - MONGODB_URL=mongodb://<your actual Mongo DB IP>:27017/saralv1newdb
      - JWT_SECRET=SARALDATA_NODE
      - MONGODB_POOL_SIZE=50
      - MIN_MONGODB_POOL_SIZE=30

    ports:
      - "3005:3005"
```

7\) Use NGINX to setup Domain Name and SSL Certificate. Refer [here](https://docs.google.com/document/d/1Rz2nhyc\_8oy56fwVHTO18ZbBT2Tss-ii8SbvqeNFiEY/edit?usp=sharing) for installation guide.

8\) Cloud Infra provisioning requirement and costing

Please refer here for minimum infra required to be provisioned for Saral sand box and the costing associated with it.

Once all above steps are completed, Saral will be ready to use.

Refer [here](https://app.gitbook.com/o/-Mi9QwJlsfb7xuxTBc0J/s/Le89Gzl6JNQ9inpB8sRg/\~/changes/174/step-by-step-guide-to-use-saral) to know how to use Saral.
