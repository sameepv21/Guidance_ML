# Introduction
* Learn definitions about the following
    * ETL Processes
    * Data Extraction
    * Data Transformation
    * Data loading

# ETL Process
* ETL = Extract, Transform and Load
* It is automated data pipeline and engineering method where data is acquired from different sources, converted into formats that can be used by a number of applications and stored in a database for persistence and consistency.
* Extract - fetch data from one or more sources.
    * Data could be batched data or streaming data.
    * Techniques
        * OCR
        * ADC and CCD sampling
        * Mail, phone or in-person surveys and polls
        * Cookies and user logs
        * Web scraping
        * APIs
        * Database querying
        * Edge Computing - Eg. video cameras having inbuilt processing system to extract information
        * Biomedical devices
* Transform - Wrangles data into formats suitable for destination
    * Processing data to conform both target systems and use cases.
    * Cleaning, filtering, joining, mergine, feature engineering, formating and data typing (making data compatible with destination)
    * Techniques
        * Data typing (casting data into appropriate types like int, float etc.)
        * Data structuring (changin data formats. Eg JSON to XML or CSV to database tables)
        * Cleaning, Normalizing, Filtering, sorting, aggegating etc.
    * Schema Types
        * Schema-on-write
            * Conventional ETL approach
            * Data must conform to prior schema before storing to a destination
            * Consistent and efficient but has limited versatility
        * Schema-on-read
            * Schema is applied to the data after it is read from a data store.
            * Modern ELT approach
            * Increased versatility
            * Enhanced storage flexibility
* Loading - Store data into database, data warehouse or other storage.
    * Making data readily available for analytics, dashboards and machine learning techniques.
    * Techniques
        * Full loading
            * Load initial history to a database
            * Loading data in one large batch
            * Used when organizations want to start tracking transactions in a new data warehouse or copy from old to new system
        * Incremental loading
            * After full loading
            * Add new data or to update already loaded data
            * Ensures transaction history is trapped
            * Data is appended and not overwritten
            * Can use both batch or stream loading based on volume and velocity of the data.
        * Scheduled loading
            * Occurs on periodic basis
            * Tools used are windows task scheduler and cron for unix
        * On-demand loading
            * Load data as required
            * Can be triggered by data size or event detection or user requests.
        * Batch and stream data loading
            * Load data in batches after a significant amount of time like a day or a week is called batch loading
            * Stream data loading means it loads data continuously in real time
            * Micro-batch loading is a short time windows used to access older data
        * Push and pull
            * Uses client server model
            * Pull - requests for data originate from the client. Eg. RSS feeds and email
            * Push - server pushes data to clients. Eg. Push notifications, instant messaging etc.
        * Parallel and Serial
            * In parallel loading, data is loaded on multiple streams to boost data loading process
            * It also uses file partitioning in order to make the file availble for loading parallely

# Use cases
* Moving data from OLTP to OLAP
* Dashboards
* Engineering machine learning pipelines
* Sales and marketting jobs.

# ELT
* Only difference in order
* Many advantages as compared to conventional ETL
    * ETL is not scalable enough due to big data challenges and hence ELT comes to recue
    * ELT can be used for streaming analytics (Real-time processing)
    * It enables integration of highly distributed data sources.
    * It enables multiple data products from the same source.
    * Increases flexibility as instead of the pipeline being desgined for one application, data lake (staging area for ELT) can be used to server multiple applications, each requiring different transformations.
    * Solves scalibility problems and handles structured and unstructured data as well
* Boost of ELT over ETL is supported by cloud tech
* Cloud tech can store huge amounts of data. Moreover, it is very cost efficient as you pay only for those services that you are using.

# Extras
* ETL has an intermediate storage facilty called staging areas.
* 