# Lyftrondata Pipeline Framework

The Lyftrondata pipeline broadly consists of the Source, the Lyftrondata platform, and the Destination. To understand more about the Sources and Destinations that Lyftrondata supports, refer to the relevant sections on Sources and Destinations. The key components that form the Lyftrondata platform are the Connectors, the Lyftrondata Event Stream, and the Consumers.

\
**Connectors in Lyftrondata:**

**Connectors** are the systems that interact with your Source Type. The Source Type is the application or database where your data lies. For example, if your data exists in a MySQL database, then your Source Type is MySQL. The Connectors typically use the SDKs provided by the Source or are developed in-house by Lyftrondata. Some Connectors may be a combination of the Source SDKs and in-house components.

**Functionality of Connectors:**

* **Identification:** The Connector of each Source Type identifies the objects to be ingested.
* **Polling:** It polls the Source to capture data changes and identifies when to read data from the Source.

#### Data Processing Components

The data ingested by the Connectors is acted upon by the following components:

1. **JSON Converters:** The ingested data is parsed according to the JSON parsing strategy selected during the Destination configuration in Lyftrondata.
2. **Translators:** The parsed data is translated into the Lyftrondata standardized format, known as a Lyftrondata Record or Event. The Event contains information about the Source schema, the data values, and metadata columns that Lyftrondata creates and uses for deduplicating the data before loading. This metadata includes details such as timestamps and unique identifiers.
3. **Schema Learning Engine:** This component creates the schema to be mapped in the Destination. It learns the schema from the ingested data and the metadata information provided by the Source.
4. **Lyftrondata Ingestion Controller:** The controller monitors and manages aspects such as API rate limits, the offset for the next data read in the case of incremental data, and other controls necessary for efficient data ingestion.

\
**Pipeline tasks**

In Lyftrondata, all activities performed by the Connectors to ingest data from a Source are achieved through background tasks. Tasks are individual units of work within a pipeline. These tasks are created, scheduled, processed, and monitored periodically by Lyftrondata’s distributed task manager. The task manager is composed of the following components:

1. **Coordinator Process:**
   * **Responsibility:** This process is responsible for auto-scaling the system.
   * **Functionality:** It monitors the tasks queue and takes necessary actions, such as adding more workers when the number of tasks waiting to be processed exceeds a threshold value.
2. **Set of Workers:**
   * **Grouping:** The worker processes are grouped into pools.
   * **Task Execution:** Each available worker picks up a task from the queue and processes it.
3. **Overseer Process:**
   * **Task Creation:** This process creates the necessary tasks and queues them.
   * **Monitoring:** It also monitors the health of the worker pool, ensuring that workers are functioning correctly and efficiently.



\


\


\
