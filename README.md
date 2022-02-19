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
  - There is no AWS service do compare. Cloud Spanner is a leader. 
  - Horizontally scalable and High available.
  - Regional or multi-regional.
  - Parent-child relationships.
  - Interleaved table.


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
  - Dynamic schema.
  - Simple queries.
  - Scales horizontally.
  - Serverless NoSQL document store.
  - Document = json data.
  - Data types: string, integer, boolean, float, null, bytes, date and time, geographical point, array and map. Reference.

- **Memorystore**:
  - Cache.
  - Managed Redis instances.
  - In-memory DB, cache or message broker.
  - Built-in high availability.
  - Vertically scalable. 
  - Compare to amazon elastic cache.
  - Fully managed Redis instance.
  - Basic and standard tier.
  - Use cases: session cache.

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

- **Choosing Storage Options**:

![alt text](./img/img3.png)

![alt text](./img/img4.png)

- **Exam Tips**:
  - Choose de rith product. Memorise the flow chart.
  - Consider the business requirement. Do not just pick the best tech solution. Provably there will be multiple answers that will fulfill the tech requirements but only one will fulfill the non-tech requirement.
  - Get to know the ecosystem (hadoop).
  - Do not over look security. Learn about the different  IAM roles for each service, and in particular how you would use them to separate users who can write data from those who just need to read data. 


## Big Data Ecosystem.

- MapReduce:
  - Programming model. Map and reduce functions.
  - Distributed implementation.
  - Created at Google. 

- Hadoop and HDFS:
  - Open source implementation of mapreduce. 
  - Hadoop Common, Hadoop HDFS, Hadoop Yarn, Hadoop MapReduce. 

- Apache Pig:
  - Platform for analysing large datasets.
  - Pig Latin defines analytics jobs.
  - An abstraction for mapreduce.
  - ETL. 

- Apache Spark:
  - Limitations of mapreduce:
    - Linear dataflow. Slow.
  - Spark:
    - General purpose cluster-computing framework.
    - RDDs. 
    - Spark Core: SparkSQL, Spark Streaming, Spark MLLib, Spark Graph X.
    - Java, Scala, Python, R.
    - Cluster Manager, Storage System.

![alt text](./img/img5.png)

- Apache kafka:
  - Publish/subscribe to streams of records. 
  - Message bus, but for data. 
  - High throughput and low latency. 
  - Four main APIs: Producer, Consumer, Streams and Connector.

![alt text](./img/img6.png)

![alt text](./img/img7.png)

## Real Time Messaging with Pub/Sub

- Messagaging Middleware: decouple applications. 
  - Without it, the system do not have resiliency. 

- PUB/SUB:
  - Global messaging and event ingestion.
  - Serverless and fully-managed. 
  - Multiple publisher/subscriber patterns.
  - Ate least once delivery.
  - Real time or batch.
  - Integrate with dataflow, cloud functions, cloud run etc.
  - Use cases:
    - Distributing workloads.
    - Asynchronous workflows.
    - Device data streaming.
    - Distributing event notifications.

- PUB/SUB Basics.
  - One to one, many to many, one to many etc. 
  - Message 10 MB or less.
  - Pull is the default delivery method. 
  - Messages must be acknowledge.
  - Push will send messages to an endpoint.
  - Must be HTTPS with valid SSL cert. 
  - A push Subscription endpoint must accept an HTTPS POST with a valid SSL certificate. It must also be configured to use an authentication header.
  - gcloud pubsub topics list.
  - Pub/Sub is designed for:
    - To enable asynchronous workflows.
    - To decouple services and distribute workloads.
    - To receive, buffer and distribute events.
    - To receive, buffer and distribute data.

- Advanced features:
  - Each message is delivered at least once for every subscription.
  - Undelivered messages are deleted after the message retention period duration (by default 7 days).
  - Minimum retation periodo: 10 minutes.
  - Messages published before a subscription is created will not be delivered to that subscription.
  - Subscription expire after 31 days of inactivity (by default).
  - New subscription with the same name have no relationship to the previous subscription.
  - Acknowledge messages are no longer available to subscribles.
  - Every message must be processed by a subscription.
  - Order: messages may not be received in order. Can use timestamps to reorder the messages at the application.
  - Messages are stored in the nearest region by default. 
  - Most granular level for which you can configure access control for Pub/Sub: Across individual topics and subscription.

![alt text](./img/img8.png)

![alt text](./img/img9.png)

- **Exam Tips**:
  - Decouple data:
    - Try to spot where Pub/Sub would be good fit to decouple components that would normally send data directly to each other. Pub/Sub can be a shock absorber, receiving data globally and allowing it to be consumed by other components at their own pace. 
  - Decouple services.
    - Try to spot where Pub/Sub can add event logic to a stack. Pub/Sub can pass events from one system to another, ir order to create asynchronous workflows.
  - Limitations:
    - Pub/Sub has unrivalled capacity and latency globally but it has certain limitations. Message data must be 10 MB or less in size, and you need to be mindful of the expiry time of undelivered messages and unused subscriptions.
  - Kafka:
    - If Kafka comes up in the exam, PUB/SUB may be a great cloud service to replace it with, especially if a case studay calls for managed cloud service to be embraced. But kafka has a much broader feature set, so make sure Pub/Sub still meets the necessary technical requirements. 
  - Cloud IoT:
    - Cloud IoT Core manages secure device registration and connection, but all messages are handled by Cloud Pub/Sub.
  - Cloud Taks *search.
  - Browse reference architectures.
    - Pub/Sub is normally the glue that holds together a data pipeline or other asynchronous workflow in a stack. Look at the smart analytical reference architectures to see how Pub/Sub works with other GCP products and services. 


## Pipelines with Dataflow

- ETL tool.
- Fully managed, serverless.
- Uses open source Apache Bean SDK.
- Support expressive SQL, Java and Python APIs.
- Real time and batch processing.
- Stackdriver integration.

![alt text](./img/img10.png)

- Driver programm defines the pipeline and are submitted tio the runner. 

![alt text](./img/img11.png)

- Pipeline lifecycle:
  - Design.Create.Test.
  - Considerations for design:
    - Location of data.
    - Input data structure and format.
    - Transformation objectives.
    - Output data structure and lcoation.
    - Basic or Branching pipelines. 
    -  Driver Program (design time):
      - Create pipeline object.
      - Create a PCollection using or create transform.
      - Apply multiple transforms as required.
      - Write out final PCollectin.

- Dataflow Pipelines Concepts:
  - ParDo: 
    - Parallel Do

![alt text](./img/img12.png)

  - Aggregation:

![alt text](./img/img13.png)

  - Characteristics of PCollection:
    - Data types.
    - Access.
    - Immutability.
    - Boundedness.
    - Timestamp.

  - Tranforms:
    - PardO.
    - GroupByKey.
    - CoGroupByKey.
    - Combine.
    - Flattern.
    - Partition.

- Advanced Datafllow concepts. 
  
![alt text](./img/img14.png)

  - Trigger types:
    - Event time.
    - Processing time.
    - Data-driven.
    - Composite. 

- Dataflow security and access.
  - Dataflow run: locally, cloud dataflow managed service. 
  - Cloud dataflow service account: 
    - Automatically created.
    - Manipules job resources.
    - Service agent role.
    - Read/write access to project resources.
    - Name:
      - service<project-number>@dataflow-service-producer-prod.iam.gserviceaccount.com.
  - Controller service account:
    - Used by workers (created by the jobs).
    - Compute Engine Instances.
    - Metadata operations. 
    - User-managed controller service account.
    - <project-number>-compute@developer.gserviceaccount.com.

- Using dataflow.
  - Regional endpoint:
    - Default: us-central-1.
    - Manages metadata about cloud data flow jobs.
    - Controls Cloud Dataflow workers.
    - Automatically selects best zone. 
    - Customer-managed encryption keys.
    - Flexible Resource Scheduling (FlexRS).
      - Advanced scheduling.
      - Cloud Dataflow Shuffle Service.
      - Preemtible VMs.
    - Migrating MapReduce jobs to Cloud Dataflow.
    - Cloud Dataflow with Pub/sub Seek.
    - Dataflow SQL:
      - Develop and run Cloud Dataflow jobs from BQ web UI.
      - Dataflow SQL (ZetaSQL variant) integrates with Apache Beam SQL.
      - Apache Beam SQL:
        - Query bounded and unbounded PCollections.
        - Query is converted to a SQL transform.
      - Cloud Dataflow SQL:
        - Utilise existing SQL skills.
        - Join streams with BQ tables.
        - Query streams or static datasets.
        - Write output BQ for analysis.

![alt text](./img/img15.png)

- **Exam Tips**:
  - Apache Beam and Dataflow are preferred solution for streaming data. Dataproc and Spark may be suitable for batch workloads.
  - Pipelines represents the complete set of stages required to read data, performe any transmormations and write data. 
  - A PCollection represents a multi-element dataset that is processed by the pipeline.
  - Understand some of the functions of the SDK:
    - ParDo is the core parallel processing function of Apache Beam, mhich can transform elements of an input PCollection into an output PCollection.
    - DoFn is a template you use to create user-defined functions (UDF) that are referenced by a ParDo.
  - Sources are where data is read from and Sinks where data gets wirtten. 
  - Windows and Watermarks;
    - Windowing allows streaming data to be grouped into finite collections according to time or session-based windows. This is very usefull when you need to impose ordering or constraints on Pub/Sub. 
    - A watermark indicates when Dataflow expects all data in a window to have arrived. Data that arrives with timestamp that's inside window but past the watermark is considered late data. 
  - Dataflow vs Cloud Composer:
    - Dataflow is normally the preferred option for data ingestion pipelines. Cloud Composer may sometimes be used for ad-hob orchestration, or to manual control of Dataflow pipelines themselves. 

- Quiz:
  - What is the purpose of a trigger in Cloud Dataflow?
    - Triggers determine when to emit output data, and behave differently for bounded and unbounded data. Triggers determine when to emit aggregated results as data arrives. For bounded data, results are emitted after all of the input has been processed. For unbounded data, results are emitted when the watermark passes the end of the window, indicating that the system believes all input data for that window has been processed.
  - What is a sensible way to test a Cloud Dataflow pipeline before deploying it to production?
    - Remove DataflowRunner from PipelineOptions, to allow the pipeline to run locally.
  - Which transformation can be used to process collections of key/value pairs, in a similar fashion to the shuffle phase of a map/shuffle/reduce-style algorithm?
    - GroupByKey is a Beam transform for processing collections of key/value pairs. It’s a parallel reduction operation, analogous to the Shuffle phase of a Map/Shuffle/Reduce-style algorithm. CoGroupByKey performs a relational join of two or more key/value PCollections that have the same key type. Combine simply combines elements, and Partition splits elements into smaller collections.
  - What is a pipeline in the context of Cloud Dataflow?
    - A pipeline represents the entire series of steps involved in ingesting data, transforming that data and writing output.
  - What method could you use to help compute averages when dealing with unbounded/streaming data?
    - A sliding time window represents time intervals in the data stream; however, sliding time windows can overlap. This kind of windowing is useful for taking running averages of data. For example, using sliding time windows you could compute a running average of the past 60 seconds’ worth of data, updated every 30 seconds.
  - What would be the most secure way to grant access from Dataflow in Project A to a Cloud Storage bucket in Project B?
    - Create a custom service account to use as the Dataflow controller service account in Project A. Grant storage viewer access for the bucket in Project B to the custom service account in Project A. By default, compute workers use your project’s Compute Engine service account as the controller service account. For more fine-grained access and control, you can use a custom service account from your job's project as the user-managed controller service account, then grant the necessary permissions to that service account from the other project.
  - Which operation can be used to invoke a user-specified function of each element of an input PCollection?
    - ParDo is a Beam transform for generic parallel processing. The ParDo processing paradigm is similar to the 'Map' phase of a Map/Shuffle/Reduce-style algorithm: a ParDo transform considers each element in the input PCollection, performs some processing function (your user code) on that element, and emits zero, one, or multiple elements to an output PCollection.
    