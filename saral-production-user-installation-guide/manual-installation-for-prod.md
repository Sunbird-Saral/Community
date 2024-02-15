---
description: Prerequisites
---

# Manual Installation for Prod

1>  AWS IAM account with administrator access

2> Ubuntu 20.04LTS on Local Machine

3> Download the following zip file and extract to folder



{% file src="../.gitbook/assets/Saral Manual install.zip" %}

Open the file named "Saral-Prod-manual-install-steps.txt".&#x20;

Open the location of the above folder in terminal and execute the commands to provision the EKS Infra required to install Saral

In the same  terminal  run the following commands to install the Saral application on the EKS cluster

`kubectl apply -f saral_backend_EKS.yml`

Run the following command to activate the load balancer and ingress object

`kubectl apply -f ing.yml`

