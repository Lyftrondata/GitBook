---
description: This page define the Lyftrondata Architecture flow.
---

# Lyftrondata Architecture

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption><p>Lyftrondata Architecture Flow</p></figcaption></figure>

<table><thead><tr><th width="239">Component</th><th>Description</th></tr></thead><tbody><tr><td>Lyftrondata Fabric (Application Server)</td><td>Lyftrondata Application server where the user manage the pipeline and configuration.</td></tr><tr><td>DB Server <br>(Project Metadata DB)</td><td>Store the actual data related to application.</td></tr><tr><td>DB Server<br>(Admin Metadata DB)</td><td>Store the metadata of the application.</td></tr><tr><td>Lyftrondata Fabric Highly Scalable<br>(Job Server Pods)</td><td>Job server pods (multiple warehouses) where lyftrondata application deploy and run the jobs for the pipelines.</td></tr><tr><td>Warehouse Logs Server<br>(S3/Wasabi/Blob/Google Storage)</td><td>A centralized system for managing and storing warehouse logs, integrated with cloud storage solutions (S3, Wasabi, Blob, Google Storage) for scalable and cost-effective storage.</td></tr><tr><td>DB Server<br>(Warehouse Metadata DB)</td><td>Store and manage the data related to the jobs runs on multiple warehouses.</td></tr><tr><td>Notification Services<br>(Email/Slack)</td><td>Facilitates sharing of job-related information through email and Slack notifications.</td></tr></tbody></table>

{% hint style="info" %}
Info: For lyftrondata installation on the environment follow the [document](../../managing-lyftrondata/lyftrondata-installation/)
{% endhint %}
