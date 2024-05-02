---
description: >-
  This page guides you through cloning deploying Lyftrondata  on an Amazon EC2
  instance by setting up the deployment environment, installing and starting
  Lyftrondata,
---

# On AWS Deployment Using AMI

{% hint style="info" %}
**INFO**

The instructions have been tested on RHEL 8 and Ubuntu 22.04.
{% endhint %}

### Requirements[​](https://docs.airbyte.com/deploying-airbyte/on-aws-ec2#requirements) <a href="#requirements" id="requirements"></a>

* To test Lyftrondata, we recommend a `t3a.medium` instance
* To deploy Lyftrondata in a production environment, we recommend a `t3a.xlarge` instance
* [Create and download an SSH key to connect to the instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/create-key-pairs.html)

### **Setup & Installation Lyftrondata**

1. Before going further, make sure for AWS you have created S3 buckets and IAM user by following [link](../configure-lyftrondata/aws-s3-iam-user.md) **OR** if you have wasabi, you have created wasabi buckets by following [link](../configure-lyftrondata/wasabi.md).

### **Setup EC2 using AMI and Configure Security Group:**

1. **Navigate to EC2 Dashboard**: Click on "Services" and select "EC2" from the list of available services.
2. **Launch Instance**: In the EC2 dashboard, click on "Launch Instance" to start the instance creation process.
3. **Choose AMI**: Select the "My AMIs" tab and choose the cloned AMI from the list.
4. **Select Instance Type**: Choose "t2.xlarge" as the instance type and proceed to configure other details.
5. **Configure Instance Details**: Specify necessary details like subnet, IAM role, and other configurations. Ensure the correct networking settings.
6. **Add Tags**: Optionally, add tags to the instance for better organization.
7. **Configure Security Group**: Create a new security group or select an existing one. Ensure that all ports are open to allow inbound and outbound traffic mention on documents. follow this steps [AWS-Security Group](../configure-lyftrondata/settings-and-security.md)
8. **Review and Launch**: Review the instance details and click on "Launch".
9. **Create New Key Pair**: Choose to create a new key pair. Download the private key file and keep it secure.
10. **Launch Instance**: After downloading the key pair, launch the instance.

Once launched, you can connect to the EC2 instance using the downloaded key pair and start using it as needed.



### Configuration Env file

To configure the environment files for the specified applications (`LyftrondataDB`, `LyftrondatasyncAPI`, `LyftrondatasyncReduxUI`), follow these step-by-step instructions:

1. **Locate Environment Configuration Files**:
   * Navigate to the root directory of each application where the environment configuration files are located.
2. **Open Environment Configuration Files**:
   * Open the environment configuration file for each application (e.g., `.env` or `.env.example`).
3. **Replace VM IP and Port**:
   * Find the variables related to the database host and port (e.g., `DB_HOST` and `DB_PORT`).
   * Replace the placeholder values with your VM's IP address and the corresponding port number.
4.  **Update URLs**:

    * Locate the variables representing URLs (e.g., `master_url`, `log_host_ip`, `airflow_dag_url`, `airflow_trigger_url`).
    * Update these URLs with your VM's IP address and port numbers where applicable.

    ```json
    DB_NAME=lyft_sync 
    DB_USER=lyft_sync
    DB_PASSWORD=***********************
    DB_HOST=VM Pivate ip       
    DB_PORT=5432
    master_url=http://VM IP:8001
    log_host_ip=http://VM IP:8000
    airflow_dag_url=http://Airflow-ip:5009
    airflow_trigger_url=http://Airflow-ip:8080
    ```




5. **Change AWS Access Key and Secret Key**:
   * Find the variables for AWS access key ID and secret access key (e.g., `aws_access_key_id` and `aws_secret_access_key`).
   * Replace the empty values with your IAM user's AWS access key ID and secret access key.
   * `aws_access_key_id=`**`******`**&#x20;
   * `aws_secret_access_key=`**`********`**
6.  **Modify Bucket Names and URLs**:

    * Update the variables representing bucket names (e.g., `bucket_name`, lyftlogos\_bucket\_name, etc.) with the desired bucket names.
    * Adjust the URLs if necessary.

    **UI ENV**

    ```json
    FAST_REFRESH='false'
    REACT_APP_MAP_KEY=
    ESLINT_NO_DEV_ERRORS='true'
    #DISABLE_ESLINT_PLUGIN=true
    REACT_APP_MS_KEY=
    REACT_APP_GOOGLE_KEY=
    REACT_APP_OCTA_ID=
    REACT_APP_OCTA_SECRET=
    REACT_APP_OCTA_DOMAIN=
    REACT_APP_API_BASE_URL='http://VM Public IP:8000'
    REACT_APP_STRIPE_URL='http://VM Public IP:8000'
    REACT_APP_AIRFLOW_BASE_URL=
    AIRFLOW_AUTH_KEY='Basic bHlmdHJvbmRhdGE6QmxhemVAMTIzIQ=='

    ```

    **API ENV**

    <pre class="language-json"><code class="lang-json">bucket_name=your-company-lyftdefault
    base_url=https://s3.amazonaws.com 
    url=https://s3.amazonaws.com/
    region_name=us-east-1 
    lyftinvoices_bucket_name=your-company-default 
    lyftlogos_bucket_name=<a data-footnote-ref href="#user-content-fn-1">your-company-logos</a> 
    lyftconnectors_bucket_name=your-company-connectors 
    base_url_with_region=https://s3-us-east-1.amazonaws.com 
    is_encoded=False
    </code></pre>

    **DB ENV**

    ```json
    aws_access_key_id=
    aws_secret_access_key=
    bucket_name=your-company-default
    wasabi_base_url=http://s3.amazonaws.com/
    STRIPE_SECRET_KEY=        
    ```
7. **Save Changes**:
   * Save the changes made to each environment configuration file.
8. **Restart Applications** (if necessary):
   * If the applications are already running, you may need to restart them for the changes to take effect.
9. **Verify Configuration**:
   * Test the applications to ensure that they are using the updated configuration values correctly.

### Execute Script to start the application:

Here's a simple bash script that navigates to each directory and runs the specified `nohup` command:

```bash
#!/bin/bash

# Navigate to LyftrondatasyncAPI directory and run the command
cd /home/lyftrondata/LyftrondatasyncAPI
nohup /home/lyftrondata/LyftrondatasyncAPI/venv/bin/python3.9 manage.py runserver 0.0.0.0:8000 > /home/lyftrondata/LyftrondatasyncAPI/APIServer.log 2>&1 &

# Navigate to LyftrondataDB directory and run the command
cd /home/lyftrondata/LyftrondataDB
nohup /home/lyftrondata/LyftrondataDB/venv/bin/python3.9 manage.py runserver 0.0.0.0:8001 > /home/lyftrondata/LyftrondatasyncAPI/DBServer.log 2>&1 &

# Navigate to LyftrondatasyncReduxUI directory and run the command
cd /home/lyftrondata/LyftrondatasyncReduxUI
nohup yarn start > UIServer.log 2>&1 &
```

Save this script to a file, for example, `run_servers.sh`, and make it executable using the following command:

```bash
sudo chmod +x run_servers.sh
```

Then you can run the script by executing `./run_servers.sh` in your terminal. This will navigate to each directory and run the specified commands using `nohup`.

[^1]: 
