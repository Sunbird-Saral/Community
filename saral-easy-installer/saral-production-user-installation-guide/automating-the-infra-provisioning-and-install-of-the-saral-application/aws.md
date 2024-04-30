# Prerequisites

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
3. **Install terraform**

Ensure that your system is up to date and you have installed the `gnupg`, `software-properties-common`, and `curl` packages installed. You will use these packages to verify HashiCorp's GPG signature and install HashiCorp's Debian package repository.

```shell-session
 sudo apt-get update && sudo apt-get install -y gnupg software-properties-common
```

Install the HashiCorp [GPG key](https://apt.releases.hashicorp.com/gpg)

```shell-session
 wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg > /dev/null
```

Verify the key's fingerprint.

```shell-session
 gpg --no-default-keyring \
--keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg \
--fingerprint
```

The `gpg` command will report the key fingerprint:

```plaintext
/usr/share/keyrings/hashicorp-archive-keyring.gpg
-------------------------------------------------
pub   rsa4096 XXXX-XX-XX [SC]
AAAA AAAA AAAA AAAA
uid           [ unknown] HashiCorp Security (HashiCorp Package Signing) <security+packaging@hashicorp.com>
sub   rsa4096 XXXX-XX-XX [E]
```

Tip

Refer to the [Official Packaging Guide](https://www.hashicorp.com/official-packaging-guide) for the latest public signing key. You can also verify the key on [Security at HashiCorp](https://www.hashicorp.com/security) under **Linux Package Checksum Verification**.

Add the official HashiCorp repository to your system. The `lsb_release -cs` command finds the distribution release codename for your current system, such as `buster`, `groovy`, or `sid`.

```shell-session
```

```shell-session
 echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list
```

Download the package information from HashiCorp.

```shell-session
 sudo apt update
```

Install Terraform from the new repository.

```shell-session
 sudo apt-get install terraform
```

### Verify the installation <a href="#verify-the-installation" id="verify-the-installation"></a>

Verify that the installation worked by opening a new terminal session and listing Terraform's available subcommands.

```shell-session
 terraform -help
Usage: terraform [-version] [-help] <command> [args]

The available commands for execution are listed below.
The most common, useful commands are shown first, followed by
less common or more advanced commands. If you're just getting
started with Terraform, stick with the common commands. For the
other commands, please read the help and docs before usage.
```

Add any subcommand to `terraform -help` to learn more about what it does and available options.

```shell-session
 terraform -help plan
```

```
Ensure that your system is up to date and you have installed the gnupg, software-properties-common, and curl packages installed. You will use these packages to verify HashiCorp's GPG signature and install HashiCorp's Debian package repository.

1> sudo apt-get update && sudo apt-get install -y gnupg software-properties-common
2> wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg > /dev/null
3> gpg --no-default-keyring \
--keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg \
--fingerprint
5> gpg
output " /usr/share/keyrings/hashicorp-archive-keyring.gpg
-------------------------------------------------
pub   rsa4096 XXXX-XX-XX [SC]
AAAA AAAA AAAA AAAA
uid           [ unknown] HashiCorp Security (HashiCorp Package Signing) <security+packaging@hashicorp.com>
sub   rsa4096 XXXX-XX-XX [E]
```
