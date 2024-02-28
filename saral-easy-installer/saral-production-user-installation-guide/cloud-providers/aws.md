# AWS

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
3. Once above completed pls refere to [here](../automating-the-infra-provisioning-and-install-of-the-saral-application.md)
