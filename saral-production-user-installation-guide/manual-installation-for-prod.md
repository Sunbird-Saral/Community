---
description: Prerequisites
---

# Manual Installation for Prod

1>  AWS IAM account with administrator access

2> Ubuntu 20.04LTS on Local Machine

3> Download the following zip file and extract to folder



{% file src="../.gitbook/assets/Saral Manual install.zip" %}

Open the location of the above folder in terminal&#x20;

&#x20;And in the open terminal window execute the commands one by one in the "Saral-Prod-manual-install-steps.txt" file  to provision the EKS Infra required to install Saral

In the same  terminal  run the following commands to install the Saral application on the EKS cluster

`kubectl apply -f saral_backend_EKS.yml`



Go to the Certificate manager in the AWS console&#x20;

And generate a SSL certificate for the domain/subdomain  to be used with the saral app

Once the certificate is generated and the status shows as issued copy the arn of the certificate and find the file "ing.yml" in the folder and update and save the value for the certificate arn in it. &#x20;

Run the following command to activate the load balancer and the ingress object

`kubectl apply -f ing.yml`

Once the above commands are run wait 10-15 minutes for the Load balancer and ingress object to be provisioned

then run&#x20;

`kubectl get ing`&#x20;

From the output of the above command find the value under the address column and copy it,  use it to map to domain/subdomain  using the CNAME option in your DNS manger.
