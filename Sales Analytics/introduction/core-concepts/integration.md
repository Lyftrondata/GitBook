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

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>Integration Type</p></figcaption></figure>

| Key                  | Value            | Description                                                   |
| -------------------- | ---------------- | ------------------------------------------------------------- |
| **Integration Type** | Full Load        | Transfers the entire dataset from the source to the target.   |
| **Integration Type** | Incremental Load | Transfers only the data that has changed since the last load. |

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption><p>Warehouse</p></figcaption></figure>

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

To ensure proper functionality, please whitelist the IP address in your environment. This will allow necessary access and prevent any connectivity issues.\


<figure><img src="../../.gitbook/assets/image (21).png" alt=""><figcaption><p>Whitelist</p></figcaption></figure>
