---
description: This page contains the info related to lyftrondata installation Deployment.
---

# Deployment Info

{% hint style="info" %}
**INFO**

These instructions have been tested on Linux RHEL - 8 and Ubuntu 22.04 LTS.
{% endhint %}

## **Setup & Installation Lyftrondata**

1. ### Requirements

* Before starting the installation process make sure you have implement the application [requirements](requirements.md).

2. ### Create User, directories and folders

* After the requirement implementation, create a user in linux which going to manage the application if needed.&#x20;
* If needed a new linux user, create a user or you can skip the user creation. After user creation or not, just download the `directory.sh` script, give permission to execute it and execute.

```bash
chmod +x directory.sh
./directory.sh
```

* This script will create require directories for the application and download the require script from Lyftrondata Repo.
* Copy the wheels folder which is provided by team to `/opt/lyftrondata/lyftrondatainstaller.`
* Add your new user or current login user to the docker group so you can run the docker commands without sudo.&#x20;

```bash
sudo usermod -a -G docker $USER
```

4.  ### Setup the Database & Restore Dump Backup&#x20;

    Here are the steps to restore a database dump using DBeaver and update the database credentials in the `.env_API` and `.env_DB` files:

    1.  **Connect to PostgreSQL Database in DBeaver:**

        * Open DBeaver and connect to the PostgreSQL database via master database using the provided credentials (`db_host`, `db_name`, `db_user`, `db_password`).

        ```
        DB Host - AWS Application Public IP
        Database Name - Postgres
        username - postgres
        Password- *********
        ```
    2. Once connected, expand the database in the DBeaver explorer to view the list of databases.

    <figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>



    To create new databases `lyft_sync` and `lyft_master` in DBeaver, follow these steps:

    1. Right-click on the database connection.
    2. Select "Create" and then "Database".
    3. Enter `lyft_sync` as the name and click "OK".
    4. Repeat steps for `lyft_master`.
    5. Verify creation in the DBeaver explorer panel.
    6. here are the steps to create a user with password and grant permissions using DBeaver:
       * **Open SQL Editor:** After successfully connecting to the database, right-click on the master database in the database navigator panel and select "SQL Editor" and then "New SQL Editor".
       *   **Write SQL Commands:** In the SQL Editor window, write the SQL commands to create the user and grant permissions. Based on your provided commands, the SQL script should look like this:

           ```
           sql
           ```
       * ```sql
         CREATE USER Enter UserName WITH PASSWORD 'Enter Password';

         GRANT ALL PRIVILEGES ON DATABASE "Enter DatabaseName" TO Enter UserName;
         GRANT ALL ON ALL TABLES IN SCHEMA public TO UserName;

         GRANT pg_read_all_data TO UserName;
         GRANT pg_write_all_data TO UserName;
         ```
       * **Execute SQL Script:** Once you have written the SQL script, click on the "Execute SQL Script" button (usually looks like a green arrow) in the toolbar of the SQL Editor window.
       * **Verify Execution:** After executing the script, you should see the output in the bottom panel indicating successful execution. You can also verify the changes by querying the system tables or using DBeaver's interface to view users and their permissions.
    7.  **Restore Database Dump:**

        * Right-click on the database name (`lyft_sync` or `lyft_master`) where you want to restore the dump.

        <figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

        * Go to "Tools" and select "Restore".
        * In the Restore dialog, choose "Local client" as the restore method.
        * Select PostgreSQL version 14 from the dropdown menu.
        * Choose "tar" as the format of the dump file.
        * Click on the "Attach file" button and select the database dump file provided to you.
        * Click "Next" to proceed.

        <figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

        <figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>
    8. **Start Restore Process:**
       * Review the restore settings and make sure they are correct.
       * Click on the "Start" button to begin the restore process.
       * Wait for the restore process to complete. You may see progress indicators during this process.
    9. **Update Database Credentials in .env Files:**
       * Open the `.env_API` and `.env_DB` files in a text editor.
       * Update the database credentials (`db_host`, `db_name`, `db_user`, `db_password`) with the correct values.
       * Save the changes to the `.env_API` and `.env_DB` files.
    10. **Verify Connection and Functionality:**
        * Reconnect to the PostgreSQL database in DBeaver using the updated credentials.
        * Verify that you can access the databases (`lyft_sync` and `lyft_master`) and that the data has been successfully restored.
        * Test the functionality of the applications connected to the databases to ensure they are working as expected.

    By following these steps, you can successfully restore the database dump using DBeaver and update the database credentials in the `.env_API` and `.env_DB` files for your applications. Remember to double-check the credentials and test the connections to ensure everything is configured correctly.
5. ### Setup the Application

* Go to the directory which is `/opt/lyftrondata/lyftrondatainstaller` , run the envwizard.sh script. This script will ask about the details related to your UI, API and database info and the S3 access key and secret key.

```bash
sh envwizard.sh
```

* When the `envwizard.sh` is executed, you need to enter the details related db and aws and lyftrondata app.

```
// Details related to master api
Enter your master database name: YOUR-MASTER-DB-NAME
Enter your master database username: YOUR-DB-USERNAME
Enter your master database password: YOUR-DB-PASSWORD
Enter your master database host: YOUR-DB-VM-PUBLIC-IP or YOUR-DB-HOST
Enter your master database port: YOUR-DB-PORT
Enter your AWS access key ID: YOUR-AWS-ACCESS-KEY
Enter your AWS secret access key: YOUR-AWS-SECRET-KEY
Enter your bucket name: DEFAULT-BUKCET-NAME
Enter your bucket base URL: 

// Details related to App
Enter your APP API Base URL: http://YOUR-VM-PUBLIC-IP
Enter your APP Stripe URL: http://YOUR-VM-PUBLIC-IP

// Details related to Api
Enter your api database name: YOUR-API-DB-NAME
Enter your api database username: YOUR-DB-USERNAME
Enter your api database password: YOUR-DB-PASSWORD
Enter your api database host: YOUR-DB-VM-PUBLIC-IP or YOUR-DB-HOST
Enter your api database port: YOUR-DB-PORT
Enter your AWS access key ID: YOUR-AWS-ACCESS-KEY
Enter your AWS secret access key: YOUR-AWS-SECRET-KEY
Enter your Default bucket name: DEFAULT-BUKCET-NAME
Enter your bucket base URL: 
Enter your bucket base URL with region: 
Enter your bucket logo name: LOGO-BUKCET-NAME
Enter your bucket connector name: CONNECTOR-BUKCET-NAME
Enter your Lyftrondata Master URL: http://YOUR-VM-PUBLIC-IP
Enter your Lyftrondata URL for api log: http://YOUR-VM-PUBLIC-IP
Enter your Lyftrondata AIRFLOW URL: http://YOUR-VM-PUBLIC-IP

```

* Now go to `/opt/lyftrondata/lyftrondatainstaller` , give execution permission to the script and run the lyftrondataapp.sh script.

```bash
chmod +x lyftrondataapp.sh
./lyftrondataapp.sh
```

* During the execution it will ask for docker hub password. Enter the password which is shared by Lyftrondata Team.

```bash
Enter Lyftrondata Docker Hub password:
```

* After all docker images pulled, you need to wait a bit to let the application UI, API and Airflow be ready.
* After the successfully installation and configuration, In your browser, visit http://localhost:3000

{% hint style="info" %}
Note: Make sure you server is listening on these [ports](../configure-lyftrondata/settings-and-security.md).
{% endhint %}

* You will need to sign in the application using the email id `admin@lyftrondata.com` and password `Lyftron123!` . Once you sign in, you are good to go.
* For the custom wheels installation which are provided by the lyftrondata team, copy those wheels folder to `/opt/lyftrondata/lyftrondatainstaller` and go to `/opt/lyftrondata/lyftrondatainstaller` directory and run the script `./wheelsinstaller.sh` . This will install the require wheels which was provided you by the lyftrondata team.

```bash
chmod +x wheelsinstaller.sh
./wheelsinstaller.sh
```

<figure><img src="../../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

**After Login follow the steps How to create warehouse**

1. Log in to the admin console using your credentials.
2. Navigate to the "Account Management" section.
3.  In the "Account Management" section, find and select "Compute."

    <figure><img src="../../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>
4. Click on the "Warehouse" tab.
5.  Look for the "Add Warehouse" button and click on it.

    <figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>
6. In the form that appears, enter the following details:
   * Name: Enter the name of the warehouse.
   * Version: Specify the version of the warehouse.
   * Compute Rate: Enter the compute rate for the warehouse.
   * Tags: Add any relevant tags for the warehouse.
   * Tenant: Select the appropriate tenant for the warehouse.
   * Computes: Choose the computes to be associated with the warehouse.
   * Description: Provide a brief description of the warehouse.
7. After filling in all the necessary details, click on the "Submit" button to add the warehouse.

