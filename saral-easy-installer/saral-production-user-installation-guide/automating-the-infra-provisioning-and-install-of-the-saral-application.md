# Automating the Infra provisioning and install of the Saral application



1. Download and extract from the following file

{% file src="../../.gitbook/assets/Saral-Automation.zip" %}

Open the extracted folder in terminal and type the following commands



<pre><code><strong>cd Saral-Automation
</strong>ls
</code></pre>

you should see a file with the name "install-saral.sh" run the following commands to make the file executable

```
chmod +x install-saral.sh
```

To execute the file type the following command

```
./install-saral.sh
```

You will be prompted to enter the AWS Document DB **Username** and **Password**

enter the details and also save those with you

Once the entire process is run  on the same terminal window you should see outputs of the Document db host-name copy and keep it

you should have the entire Saral Infra setup on you AWS account  Infra structure Includes the following components

```
1> EKS cluster with fargate Nodes
2> VPC
3> Subnets (2-Private and 2-Public subnet for EKS cluster 2-Private subnets for Document DB
3> Application load balancer
4> NAT gateway
5> Elastic IP
6> AWS document DB
6> Saral backend application installed on the cluster
```

Once the entire Infrastructure is setup

We need to update the application with the document db hostname, username, password and the ssl certificate arn.&#x20;

4. Go to the following folder  "Saral-Automation/Saral-EKS/helm/saral-backend-chart/"
5. Fill the value.yml file with the following details &#x20;

```
a.  under docdb->connections-> fill  documentdb username, documentdb password, documentdb hostname
b.  under whitelist->domain-> fill in your domain/subdomain 
c.  under ingress->certificateARN-> fill the certificate arn that you will get from AWS certificate manager
```

* Once you have updated the values in the `value.yml` file, use the following command to deploy the chart.

Open the helm folder in a terminal window and run the following&#x20;

Below command will deploy the application to your Kubernetes cluster using the values you have specified in the values.yml file

```
helm install saral-backend ./saral-backend-chart
```

Verify the deployment by checking the status of the pods.

```bash
kubectl get pods
```

You should see the pods associated with your deployment running successfully

To uninstall the `saral-backend` deployment using Helm, execute the following command

```
helm uninstall saral-backend
```

