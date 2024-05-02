---
description: >-
  This page guides you through deploying Lyftrondata on a Microsoft Azure VM by
  setting up the deployment environment, installing and starting Lyftrondata,
---

# On Azure Deployment

{% hint style="info" %}
INFO

The instructions have been tested on a standard DS1 v2 (2 vcpu, 8 GiB memory) Microsoft Azure VM with Linux Red Hat - 8  and Ubuntu 22.04 LTS.
{% endhint %}

### Requirements[​](https://docs.airbyte.com/deploying-airbyte/on-aws-ec2#requirements) <a href="#requirements" id="requirements"></a>

* To test Lyftrondata, we recommend a `t2.medium` instance
* To deploy Lyftrondata in a production environment, we recommend a `t2.xlarge` instance
* Before starting the installation process make sure you have implement the application [requirements](requirements.md).
* [Create and download an SSH key to connect to the instance](https://learn.microsoft.com/en-us/azure/virtual-machines/ssh-keys-portal)

### **Setup & Installation Lyftrondata**

* Setup the application on Azure follow these [steps](deployment-info.md).
