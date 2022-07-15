# Introduction
* Any set of processes that are connected sequentially are called pipelines.
* Output of one process is passed on as input to the next process in a chain.
* Data pipelines specific purpose is to move data from one place or form to another.
* It is any system that extracts, transforms and loads data.
* Software driven processes - commands, programs and threads.
* Bash 'pipe' is one example and can be used to connect such processes.

# Performance
* Data packets are simple units of data. These can range from just one record or to a collection of records in an event.
* These data packets are queued and passed through the pipeline.
* The length of the data pipeline is called pipline latency. In simple terms, length of the data pipeline indicates the time required for a single data packet to traverse entire pipeline.
* Hence, latency is total time taken by a single packet to traverse entire pipeline which equals the sum of individual latency during each processing stage.
* Througput delays equals the times between successive packet arrivals.
    * Another way to understand this is that it answers how much data can be fed through the pipe per unit of time.
    * Larger the data packets per time unit equals larger throughput.
* Latency and throughput are key design considerations for data pipelines.

# Key Data pipeline processes
* Stages
    * Data Extraction
    * Data ingestion into pipeline
    * Optional transformation stages within the pipeline
    * Final loading into destination
    * Scheduling or triggering
    * Monitoring workflow
    * Maintenance and optimization as required
* Considerations (after production)
    * Latency
    * Throughput
    * Warnings, errors and failures
    * Utilization rate
    * Logging and alerting system
* Load balanced data pipeline
    * The data packets for one stage would be available just in time the stage finished its job with earlier data packet.
    * This means that there will be no data blow bottlenecks as it is assumed that all the stages require same amount of time.
    * Thus, this ensured uniform packet throughput for each stage.
    * Such a pipeline is called load-balanced pipeline.
* One method to handle unbalanced loads is to use parallelism.
* Even though there would be a bit overhead of splitting and aggregating input and output respectively, the total latency will be reduced.
* Parallelism can be obtained by replicating data packets on multiple CPUs, cores or threads.
* Such pipelines that use parallelism is called dynamic or non-linear pipeline.
* For syncronization among such processes, one can use I/O buffers (holding area for data) to smooth out the flow of data.

# Applications
* Backing up files (simple as no transformation stage is required)
* Integrating disparate raw data sources into a data lake
* Moving transactional records to a data warehouse
* Streaming data from IoT devices to dashboards.
* Preparing raw data for ML development or production
* Messaging systems such as email and sms.

# Batch Data Pipelines
* Used when datasets needed to be extracted act as one big unit.
* Run periodically on schedule.
* Can also be initiated based on data size or other triggers.
* Useful when latest data is not needed and when accuracy is critical.

# Streaming Data Pipelines
* Ingest data packets in rapid succession.
* Real-time results/processing.
* Event streams can be loaded to storage and users can publish/subscribe to event streams.

# Micro-batch Data Pipeline
* Tiny micro-batches and faster processing achieve near real time processing.
* Smaller batches mean improve load balancing and lower latency.
* Used when short windows of data are required.

# Lambda Architecture
* A hybrid (batch and stream) data processing architecture.
* Historical data is liberated to batch layer and vice versa.
* Finally, they are integrated in the serving layer.
* Thus, data stream fills in "latency gap".
* Useful when accuracy and speed both are concerned.
* Only drawback is the logical complexity involved.

# Tools and Technologies
* Features observed in most
    * Automation: Fully automated pipelines from extraction to loading
    * Ease of use: Gives ETL rule recommendations.
    * Drag and Drop Interfaces: No code rules and data flows.
    * Transformation support: Assistance with complex calculations.
    Security and Compliance: Data encryption and compliance with HIPAA and GDPR
* Some tools
    * Pandas, Vaex, Dask and Apache Spark (similar functionalities) (OS)
    * Apache Airflow (OS)
    * Talend Open Studio (OS)
    * AWS Glue (Enterprise)
    * Panoply (Enterprise)
    * Alteryx (Enterprise)
    * IBM Infosphere Datastage (Enterprise)
    * IBM streams (Enterprise) (SDP)
    * Apache Storm, SQLStream, Apache Samza, Apache Spark, Azure stream analytics, Apache Kafka