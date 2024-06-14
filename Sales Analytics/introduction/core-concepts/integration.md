# Integration

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

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption><p>Integration Type</p></figcaption></figure>

| Key                  | Value            | Description                                                   |
| -------------------- | ---------------- | ------------------------------------------------------------- |
| **Integration Type** | Full Load        | Transfers the entire dataset from the source to the target.   |
| **Integration Type** | Incremental Load | Transfers only the data that has changed since the last load. |

<figure><img src="../../.gitbook/assets/image (2) (1).png" alt=""><figcaption><p>Warehouse</p></figcaption></figure>

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

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption><p>Whitelist</p></figcaption></figure>

{% hint style="info" %}
**Source**:\
Lyftrondata integrates with over 300 data sources. You simply need to select the source from which to load your data into the target.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption><p>Lyftrondata Connectors</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption><p>Freshsales Connection Name</p></figcaption></figure>

<table><thead><tr><th>Key</th><th>Description</th><th data-hidden></th></tr></thead><tbody><tr><td>Connection Name</td><td>You need to write a meaningful connection name.</td><td></td></tr><tr><td>Description</td><td>Short description of the connection name.</td><td></td></tr><tr><td>Tag</td><td>Tags for a connection are keywords or labels assigned to a data connection to categorize and organize it.</td><td></td></tr></tbody></table>

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption><p>Configuration</p></figcaption></figure>



{% hint style="info" %}
You need to complete the prerequisites for the API in order to obtain the credentials. Some APIs require payment, while others are free to use. I have used Freshsales API as an example.
{% endhint %}

<table><thead><tr><th>Key</th><th>Value</th><th data-hidden></th></tr></thead><tbody><tr><td>Personal Token</td><td>Your Freshsales API Personal Token.</td><td></td></tr><tr><td>Base URL</td><td>Your Freshsales API BASE URL.</td><td></td></tr><tr><td>Hostname</td><td>Your Freshsales Hostname.</td><td></td></tr></tbody></table>



<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>
