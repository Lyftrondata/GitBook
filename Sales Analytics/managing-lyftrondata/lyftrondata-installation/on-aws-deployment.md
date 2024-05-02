---
description: >-
  This page guides you through deploying Lyftrondata  on an Amazon EC2 instance
  by setting up the deployment environment, installing and starting Lyftrondata,
---

# On AWS Deployment



{% hint style="info" %}
**INFO**

The instructions have been tested on Amazon Linux Red Hat - 8  and Ubuntu 22.04 LTS.
{% endhint %}



### Requirements[​](https://docs.airbyte.com/deploying-airbyte/on-aws-ec2#requirements) <a href="#requirements" id="requirements"></a>

* To test Lyftrondata, we recommend a `t2.medium` instance
* To deploy Lyftrondata in a production environment, we recommend a `t2.xlarge` instance
* Before starting the installation process make sure you have implement the application [requirements](requirements.md).
* [Create and download an SSH key to connect to the instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/create-key-pairs.html)

### **Setup & Installation Lyftrondata**

* Setup the application on EC2 follow these [steps](deployment-info.md).
