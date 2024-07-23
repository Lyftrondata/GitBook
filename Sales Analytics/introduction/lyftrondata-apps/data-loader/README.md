# Data Loader

Data loading integration refers to the process of extracting data from various sources, transforming it as needed, and loading it into a destination system, such as a data warehouse or data lake. This process is often referred to as ETL (Extract, Transform, Load) or ELT (Extract, Load, Transform) depending on when the data transformation occurs.

**Integration is Divided into 5 Simple Steps:**

{% hint style="success" %}
1. Prep
2. Select Source
3. Select Target
4. Configuration
5. Confirm
{% endhint %}

Choose Integration Type:

<figure><img src="../../../.gitbook/assets/image (7).png" alt=""><figcaption><p>Integration Type</p></figcaption></figure>

| Key                  | Value            | Description                                                   |
| -------------------- | ---------------- | ------------------------------------------------------------- |
| **Integration Type** | Full Load        | Transfers the entire dataset from the source to the target.   |
| **Integration Type** | Incremental Load | Transfers only the data that has changed since the last load. |

<figure><img src="../../../.gitbook/assets/image (2) (1).png" alt=""><figcaption><p>Warehouse</p></figcaption></figure>

**Warehouse:**

Warehouse (also known as a virtual warehouse) is a key component that plays a central role in processing Integrations. It is a cluster of computing resources (e.g., CPU, memory) that users can provision to perform data processing tasks.

**Components of Warehouse:**

| Key        | Value             |
| ---------- | ----------------- |
| Name       | Warehouse Name    |
| CPU        | No of CPU's       |
| Memory     | Amount of memory  |
| IP address | Public IP Address |

**Whitelist Warehouse IP**:

{% hint style="danger" %}
To ensure proper functionality, please whitelist the IP address in your environment. This will allow necessary access and prevent any connectivity issues.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (6).png" alt=""><figcaption><p>Whitelist</p></figcaption></figure>

{% hint style="info" %}
**Select Source**:\
Lyftrondata integrates with over 300 data sources. You simply need to select the source from which to load your data into the target.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption><p>Lyftrondata Connectors</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption><p>Freshsales Connection Name</p></figcaption></figure>

<table><thead><tr><th>Key</th><th>Description</th><th data-hidden></th></tr></thead><tbody><tr><td>Connection Name</td><td>You need to write a meaningful connection name.</td><td></td></tr><tr><td>Description</td><td>Short description of the connection name.</td><td></td></tr><tr><td>Tag</td><td>Tags for a connection are keywords or labels assigned to a data connection to categorize and organize it.</td><td></td></tr></tbody></table>

<figure><img src="../../../.gitbook/assets/image (5).png" alt=""><figcaption><p>Configuration</p></figcaption></figure>



{% hint style="info" %}
You need to complete the prerequisites for the API in order to obtain the credentials. Some APIs require payment, while others are free to use. I have used Freshsales API as an example.
{% endhint %}

<table><thead><tr><th>Key</th><th>Value</th><th data-hidden></th></tr></thead><tbody><tr><td>Personal Token</td><td>Your Freshsales API Personal Token.</td><td></td></tr><tr><td>Base URL</td><td>Your Freshsales API BASE URL.</td><td></td></tr><tr><td>Hostname</td><td>Your Freshsales Hostname.</td><td></td></tr></tbody></table>

{% hint style="info" %}
**Select Target:**\
Lyftrondata's target refers to the destination where data is transferred, transformed, or loaded during data integration processes. It could include databases, data warehouses, data lakes, cloud storage services, or other platforms where the processed data is ultimately stored or used for further analysis and reporting.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (22).png" alt=""><figcaption><p>Target Connectors</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (24).png" alt=""><figcaption><p>Target Connection Name</p></figcaption></figure>

<table><thead><tr><th width="196">Key</th><th>Description</th><th data-hidden></th></tr></thead><tbody><tr><td>Connection Name</td><td>You need to write a meaningful connection name.</td><td></td></tr><tr><td>Description</td><td>Short description of the connection name.</td><td></td></tr><tr><td>Tag</td><td>Tags for a connection are keywords or labels assigned to a data connection to categorize and organize it.</td><td></td></tr></tbody></table>

<figure><img src="../../../.gitbook/assets/image (23).png" alt=""><figcaption><p>Configuration Screen Target</p></figcaption></figure>

#### Basic <a href="#basic" id="basic"></a>

<table><thead><tr><th>Key</th><th width="291">Value</th><th>Field</th></tr></thead><tbody><tr><td>URL</td><td>Your snowflake account URL.</td><td>Required</td></tr><tr><td>Username</td><td>Enter your snowflake Username.</td><td>Required</td></tr><tr><td>Password</td><td>Enter your snowflake Password.</td><td>Required</td></tr><tr><td>Schema</td><td>Enter your snowflake Schema.</td><td>Required</td></tr><tr><td>Role</td><td>Enter your snowflake Role.</td><td>Required</td></tr><tr><td>Warehouse</td><td>Enter your snowflake Warehouse.</td><td>Required</td></tr><tr><td>Database</td><td>Enter your snowflake Database.</td><td>Required</td></tr></tbody></table>

Target Snowflake Connection Video:

{% embed url="https://www.loom.com/share/8338706973e94db2a3878ed6c342b908" %}
Snowflake
{% endembed %}

{% hint style="info" %}
After setting up the target, the integration configuration process begins, defining data flow through mappings, transformations, and schedules for efficient, accurate processing. Batches manage data transfer size and frequency to optimize performance, while logging tracks each step for troubleshooting and monitoring. Webhooks trigger actions on event-based notifications, enhancing automation in real-time data workflows.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption><p>Integration</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (26).png" alt=""><figcaption><p>Process Configuration</p></figcaption></figure>

<table><thead><tr><th width="273">Config Parameters</th><th>Description</th><th data-hidden></th></tr></thead><tbody><tr><td>Batch Size</td><td>Batch size is the number of data records processed together in a single operation, optimizing performance and resource use.</td><td></td></tr><tr><td>Select Memory Size</td><td>Refers to choosing the amount of memory allocated for a specific task.</td><td></td></tr><tr><td>Regex</td><td>A sequence of characters that defines a search pattern for matching, replacing, and extracting text.</td><td></td></tr><tr><td>Die on Error</td><td>Immediately stop a program or process when an error occurs, preventing any further execution.</td><td></td></tr><tr><td>Process Method</td><td>Process method parquet or Avro" refers to the choice between using the Parquet or Avro file formats during data processing.</td><td></td></tr><tr><td>Pipeline Parallelism</td><td>Pipeline parallelism means how many pipelines can run in parallel.</td><td></td></tr><tr><td>Enable Multithreading</td><td>Execute multiple threads concurrently, improving performance by utilizing multiple CPU cores effectively</td><td></td></tr><tr><td>Pipeline Per Dag Limit</td><td>Pipeline per DAG means how many pipelines/tables you can select in a single integration.</td><td></td></tr></tbody></table>



{% hint style="info" %}
You need to select the target schema in the load configuration.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (27).png" alt=""><figcaption><p>Load Configuration Schema</p></figcaption></figure>



{% hint style="info" %}
You can schedule the integration based on your specific time.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (28).png" alt=""><figcaption><p>Schedule Integration</p></figcaption></figure>



{% hint style="info" %}
If you want to receive notifications through email or a Slack channel, you can configure that. You will get notifications for any event, whether it passes or fails.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (29).png" alt=""><figcaption><p>Notification</p></figcaption></figure>



{% hint style="info" %}
You have the option to select your preferred logging service for tracking and monitoring your data integration processes. Choose between Lyftrondata or CloudWatch to ensure you receive timely and detailed logs of all activities.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (30).png" alt=""><figcaption><p>Logging</p></figcaption></figure>

{% hint style="info" %}
You can also set up Web Hook Calls to receive real-time notifications and updates. This allows you to instantly react to events and integrate with other systems seamlessly.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (31).png" alt=""><figcaption><p>Webhooks Call</p></figcaption></figure>

**Data Loading Integration:**

{% embed url="https://www.loom.com/share/addb780e54f3430aa2c84a2caed67b76?sid=d0397880-1843-400e-bb99-35d7ee3339e6" %}
