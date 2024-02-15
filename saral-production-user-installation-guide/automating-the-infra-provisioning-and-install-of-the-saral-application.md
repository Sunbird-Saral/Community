# Automating the Infra provisioning and install of the Saral application

**Requirements**

Before you start, ensure you have the following:

* An AWS IAM account with administrator access.
* Ubuntu 20.04 LTS installed on your local machine.
* AWS CLI installed on your machine.
* TO install follow the below steps

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

