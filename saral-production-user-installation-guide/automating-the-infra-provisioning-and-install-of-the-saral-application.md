# Automating the Infra provisioning and install of the Saral application

**Requirements**

Before you start, ensure you have the following:

* An AWS IAM account with administrator access.
* Ubuntu 20.04 LTS installed on your local machine.
* SSL certificate generated for your domain/subdomain

```
     To generate certificate from AWS
              1> Go to Certificate manager in AWS web console
              2> On top left hand side click on list certificates
              3> Once open on the top right side click on Request
              4> Click next
              5> Type the FQDN(fully qualified domain/subdomain name eg:   abcd.domain.com)
              6> Click request
              7> Click on refresh button
              8> You should see the newely requested certificate.
              9> Click on the certificate ID
              10> Under Domain you should see the generated CNAME records
              11> Add these CNAME records to your domain manager.
              12> Once CNAME records are entered in Domain manager it should take between 1-3 hours to generate the certificates
              13> Once generated the status should show in green issued
              14> Click on certificate ID once more
              15> Find and copy the Certificate ARN
```

* AWS CLI installed on your machine.
* To install follow the below steps

```
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/instal
```

#### &#x20;**Verify AWS CLI Installation**

1.  Run the following command to check if AWS CLI is installed properly.

    ```bash
    aws --version
    ```

    You should see the version of AWS CLI installed.
2.  **Configure AWS CLI**

    Use the AWS configure command to set up your credentials.

    ```bash
    aws configure
    ```

    Enter your AWS Access Key ID, Secret Access Key, region, and output format when prompted.
3. Download and extract from the following file

{% file src="../.gitbook/assets/Saral-Automation.zip" %}

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

To uninstall the `saral-backend` deployment using Helm, execute the following command

```
helm uninstall saral-backend
```

This command will deploy the application to your Kubernetes cluster using the values you have specified in the values.yml file

```
helm install saral-backend ./saral-backend-chart
```

Verify the deployment by checking the status of the pods.

```bash
kubectl get pods
```

You should see the pods associated with your deployment running successfully

