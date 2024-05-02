---
description: This page contains the requirement for running Lyftrondata Application.
---

# Requirements

## Requirements and compatibility <a href="#requirements-and-compatibility" id="requirements-and-compatibility"></a>

**Memory Requirements:**\
Memory requirements depend on the product target use. For most deployments, 12 GB RAM is sufficient. For small deployments, 8 GB RAM is the minimum requirement until specific deployments are tested and verified.

### Hardware recommendations <a href="#hardware-recommendations" id="hardware-recommendations"></a>

Lyftrondata can scale from a basic installation on a laptop used by a single person all the way up to a highly available deployment used by thousands of people. The following recommendations should apply to most Lyftrondata deployments, but your requirements may vary depending on the usage of your team.&#x20;

A single machine, with 4-core processor, 16 GB of RAM, and 50GB storage. Scaling the server up can enable it to handle a larger number of users and workload.

For evaluation or personal use, you can use a basic configuration with as little as 8 GB of RAM, but this would not be recommended for a testing or production server used by more than one person.

## System Setup and Software Installation

### Install Docker and Docker Compose

* Install `Docker Engine` and the `Docker Compose plugin` on your workstation (see Linux  [instructions](https://docs.docker.com/engine/install/)).
* If you are unable to install using the above instructions you can follow the below steps.&#x20;

**For Red Hat Enterprise  Linux.**

```bash
sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
sudo systemctl start docker
sudo systemctl enable docker
```

**For Ubuntu.**

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

Run Docker command without sudo, execute the below command and reset your terminal.

```bash
sudo usermod -a -G docker $USER
```

### Git installation

**For Red Hat Enterprise Linux.**

```bash
sudo yum install git -y
```

**For Ubuntu.**

```bash
sudo apt install git -y
```

Git is use to install our require script which will setup the application.

### Create Bucket and Require User

For AWS IAM user and s3 bucket, kindly follow the [document](../configure-lyftrondata/aws-s3-iam-user.md).

For Wasabi follow the [document](../configure-lyftrondata/wasabi.md).

### Natural Languages <a href="#natural-languages" id="natural-languages"></a>

You can install Lyftrondata on supported operating systems in various languages. However, Lyftrondata user interface is available only in US English.

#### Browsers <a href="#browsers" id="browsers"></a>

You can use these browsers with Lyftrondata to access it with the web client.

| Browser           | Supported Version         | Known issues                                                                                       |
| ----------------- | ------------------------- | -------------------------------------------------------------------------------------------------- |
| Chrome            | most recent (recommended) |                                                                                                    |
| Firefox           | most recent               |                                                                                                    |
| Edge              | most recent               |                                                                                                    |
| Internet Explorer | 11 and later              | May not render Apache Spark application portal properly. For example, query plans will not show up |

Edge, Firefox, and Chrome automatically update themselves, so Lyftrondata supports the most recent version.

## Third-Party Software <a href="#third-party-software" id="third-party-software"></a>

Lyftrondata software may be provided with certain third-party software, including but not limited to open-source software, which is licensed under its applicable third-party software license agreement. For license information about third-party software distributed with Lyftrondata software, refer to your Lyftrondata license agreement.



