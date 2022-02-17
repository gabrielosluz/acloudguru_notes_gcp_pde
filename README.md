# GCP Professional Data Engineer

Repository to store study notes for the GCP Professional Data Engineer certification.

Source: [A Cloud Guru](https://acloudguru.com/course/google-certified-professional-data-engineer)

## Storage in GCP

#### **Data Processing fundamentals**

- DW: Structured and/or Processed. Ready to use.
- Data Lake: Raw and/or Unstructured. Ready to analyse. Flexible.
- OLTP: transactional. Modify.
- OLAP: analytical. Query.
- Batch: time window to load data.
- Streaming: continuous collection of data. Can you micro-batches.
- Data Pipeline:
  - Ingestion: batch or streaming. 
  - Storage.
  - Processing: ETL/ELT. Formatting, labeling, filtering, validating etc. 
  - Visualization. Decision making. 

#### **Storage and Databases**

- Choosing data options:
![alt text](./img/img1.png)

- **Cloud Storage**:
  - Unstructured object storage.
  - Regional, dual-region or multi-regio.
  - Standard, nearline and coldline.
  - Storage event triggers.
  - Buckets exist within projets.
  - Objects are immutable.
  - Overwrite are atiomic.
  - Access: Console, HTTP API, SDK, gsutil cli.
  - Integrity checking. 
  - Parallel uploads of composite objects.
  - Requestor pays.
  - Charges: Operation, Network, Data retrieval.
  - Lifecycle management.
  - IAM for bukl access to buckets.
  - ACLs for granular access.
  - Signed URLs.
  - Signed policy documents to set what kinds of files can be uploaded.

![alt text](./img/img2.png)


- **Cloud BigTable**:
  - Petabyte-scale NoSQL Database.
  - High-throughput and scalability.
  - Wide column key/value data.
  - Time-series, transacional, IoT data. 

- **Big Query**:
  - Petabyte-scala data warehouse.
  - Fast SQL queries on large datasets.

- **Cloud Spanner**:
  - Global SQL based relational database.
  - Strong consistency.
  - Horizontal scalability and high availability. 
  - Financiual transactions.

- **Cloud SQL**:
  - Managed MySQL, SQL Server and PostgreSQL instances. 
  - Built-in backups, replicas and failover. 
  - Vertically scalable. 
  - Not fully managed. 
  - Automate instance and database creation, replciation, backups, patches and updates.
  - Scalability and availability: vertically scale to 64 cores and 416GB RAM. Live migration and HA configs.
  - Unsupported features:
    - User defined functions.
    - InnoDB memcached plugin.
    - Federated engine.
    - SUPER privilege. 
  - Importing MySQL Data:
    - InnoDB mysqldump export/import.
    - CSV import.
    - External replica promotion.

- **Cloud Firestore**:
  - Fully-managed NoSQL document database.
  - Large collections of small JSON documents. 
  - Realtime database with mobile SDKS.

- **Memorystore**:
  - Cache.
  - Managed Redis instances.
  - In-memory DB, cache or message broker.
  - Built-in high availability.
  - Vertically scalable. 

- Managing Data:
  - Sources ans sinks.
  - Structured or unstructured.
  - Batch or streaming.
  - Data modeling:
    - Conceptual.
    - Logical. 
    - Physical. 
  - Relational: good relational schema design. 
    - Normalization and reducing waste. 
    - Accuracy and integrity.
    - Primary Keys and tables.

- **Service Account**:
  - Human: auth with their own credentials.
  - Automate tasks: service accounts. 
  - Identity can be assumed by an app/workload.
  - Scopes: set of users. 
  
- **Data Transfer Services**:
  - Cloud Storage Transfer Service.
    - Scheduled and periodic.
    - Filters based on names and dates.
    - Delete obj in source and destination.
    - Full access: storagetransfer.admin
    - Submit transfer: storagetransfer.user
    - List jobs and operations: storagetransfer.viewer. 

  - BigQuery Data Transfer Service:
    - Automates data transfer to BQ.
    - Data loaded on a regular basis.
    - Backfills can recover from gaps and outages. 

  - Transfer Appliance:
    - Physical rackable storage device. 
    - Ship the full device back to Google. 



