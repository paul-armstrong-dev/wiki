----

## Hadoop vs Spark
#### Hadoop
**Hadoop is an open-source framework that allows to store and process big data, in a distributed environment across clusters of computers.** 
- Hadoop is designed to scale up from a single server to thousands of machines, where every machine is offering local computation and storage. 
- Hadoop is a registered trademark of the Apache software foundation. 
- It utilizes a simple programming model to perform the required operation among clusters. 
- All modules in Hadoop are designed with a fundamental assumption that hardware failures are common occurrences and should be dealt with by the framework.
- It runs the application using the MapReduce algorithm, where data is processed in parallel on different CPU nodes. 
    - In other words, the Hadoop framework is capable enough to develop applications, which are further capable of running on clusters of computers and they could perform a complete statistical analysis for a huge amount of data.
- The core of Hadoop consists of: 
    - **Storage**
        - Known as **Hadoop Distributed File System** 
    - **Processing** 
        - Known as the **MapReduce programming model**. 
- Hadoop basically split files into the large blocks and distribute them across the clusters, transfer package code into nodes to process data in parallel.
- This approach dataset to be processed faster and more efficiently. 
- Other Hadoop modules are: 
    - **Hadoop common**, which is a bunch of Java libraries and utilities returned by Hadoop modules. 
        - These libraries provide a file system and operating system level abstraction, also contain required Java files and scripts to start Hadoop. 
    - **Hadoop Yarn** is also a module, which is being used for job scheduling and cluster resource management.

---- 


#### Spark
**Spark is an open-source cluster computing designed for fast computation.** 
- It provides an interface for programming entire clusters with implicit data parallelism and fault tolerance. 
- The main feature of Spark is in-memory cluster computing that increases the speed of an application.
- Spark was built on the top of Hadoop MapReduce module and it extends the MapReduce model to efficiently use more type of computations which include Interactive Queries and Stream Processing. 
- Spark was introduced by the Apache software foundation, to speed up the Hadoop computational computing software process.
- Spark has its own cluster management and is not a modified version of Hadoop. 
- Spark utilizes Hadoop in two ways: 
    1. storage 
    2. processing. 
- Since cluster management is arriving from Spark itself, it uses Hadoop for storage purposes only.
- Spark is one of the Hadoop’s subprojects which was developed in 2009, and later it became open source under a BSD license. 
- It has lots of wonderful features, by modifying certain modules and incorporating new modules. 
- It helps run an application in a Hadoop cluster, multiple times faster in memory.
- This is made possible by reducing the number of read/write operations to disk. 
    - It stores the intermediate processing data in memory, saving read/write operations. 
- Spark also provides built-in APIs in Java, Python or Scala. 
    - Thus, one can write applications in multiple ways.
- Spark not only provides a Map and Reduce strategy but also support SQL queries, Streaming data, Machine learning and Graph Algorithms.

---- 

## Comparison 

#### Key differences between Hadoop vs Spark
- Both Hadoop vs Spark are popular choices in the market; 
- let us discuss some of the major Difference Between Hadoop and Spark:
    1. Hadoop is an open source framework which uses a MapReduce algorithm 
        - Spark is lightning fast cluster computing technology, which extends the MapReduce model to efficiently use with more type of computations.
    2. Hadoop’s MapReduce model reads and writes from a disk, thus slow down the processing speed 
        - Spark reduces the number of read/write cycles to disk and store intermediate data in-memory, hence faster-processing speed.
    3. Hadoop requires developers to hand code each and every operation 
        - Spark is easy to program with RDD – Resilient Distributed Dataset.
    4. Hadoop MapReduce model provides a batch engine, hence dependent on different engines for other requirements 
        - Spark performs batch, interactive, Machine Learning and Streaming all in the same cluster.
    5. Hadoop is designed to handle batch processing efficiently 
        - Spark is designed to handle real-time data efficiently.
    6. Hadoop is a high latency computing framework, which does not have an interactive mode 
        - Spark is a low latency computing and can process data interactively.
    7. With Hadoop MapReduce, a developer can only process data in batch mode only 
        - Spark can process real-time data through Spark Streaming.
    8. Hadoop is designed to handle faults and failures, it is naturally resilient toward faults, hence a highly fault-tolerant system 
        - with Spark, RDD allows recovery of partitions on failed nodes.
    9. Hadoop needs an external job scheduler for example – Oozie to schedule complex flows 
        - Spark has in-memory computation, so it has its own flow scheduler.
    10. Hadoop is a cheaper option available while comparing it in terms of cost 
        - Spark requires a lot of RAM to run in-memory, thus increasing the cluster and hence cost.



|    |Hadoop | Spark   |
|---|---|---|
| Category   |  Basic Data processing engine  | Data analytics engine   |
| Usage   | Batch processing with a huge volume of data   | Process real-time data, from real-time events like Twitter, Facebook   |
| Latency   | High latency computing   | Low latency computing   |
|  Data  |  Process data in batch mode  | Can process interactively   |
| Ease of use   | Hadoop’s MapReduce model is complex, need to handle low-level APIs   | Easier to use, abstraction enables a user to process data using high-level operators   |
| Scheduler   | External job scheduler is required   | In-memory computation, no external scheduler required   |
| Security   |Highly secure    |  Less secure as compare to Hadoop  |
| Cost   | Less costly since MapReduce model provide a cheaper strategy   |  Costlier than Hadoop since it has an in-memory solution  |


------- 

### Hadoop vs SQL

|Hadoop | SQL|
|---|---|
| It can be used for storing, processing, retrieving and pattern extraction from data across a wide range of formats.     |      It can be used for storage, processing, retrieval and pattern mining of data stored in a relational database format only     |      
| It works well for structured and unstructured data.     |      It works only for structured data only     |      
| It can many technology stacks on top of it each doing a specific task like HDFS, AVRO, Pig, HBase etc.     |      SQL is a query language with specific syntax and a scheme to get around with things     |      
| Data can be stored in the form of key-value pairs, tables, hash map etc.     |      Data is stored in the form of tables only     |      
| It supports NoSQL type data structures, columnar data structures etc. like MongoDB     |      It works on the property of ACID     |      
| It can be used to store and process log data, real-time data, images, videos, sensor data and other variety of data.     |      Data variety is severely restricted in SQL     |      
| Hadoop is used mainly in those applications where data volume is huge and systems like SQL cannot perform well.     |      SQL can store a moderate volume of data     |      
| INSERT, SELECT type statements are very fast in Hadoop compared to SQL     |      SQL syntax are much slower when executed on millions of rows at a time     |      
| Hadoop uses the concept of distributed computing, applies the principle of map-reduce and thus handle data available on multiple systems across multiple locations.     |      SQL data sources are usually available on-premise or on a cloud. Thus it cannot exploit the advantages of distributed computing     |      
| Hadoop based systems can be easily and cost-effectively scaled. Horizontal scaling is very cheap and as many computers can be connected to the network as desired thus it is scalable on demand.     |      Buying an additional SQL server costs a fortune. If a system runs out of storage, additional racks and servers need to be purchased and configured which is expensive and time-consuming     |      
| It is highly faulted tolerant.     |      It has good fault tolerance     |      
| It uses commodity hardware.     |      It uses propriety hardware     |      
| It is a free and open source.     |      Most of the SQL systems are licensed     |      
| Advanced machine learning and artificial intelligence techniques can be build using Hadoop.     |      Support for ML and AI is highly limited on SQL and only a few companies provide that     |      
| Using appropriate JDBC connectors, Hadoop can communicate with SQL systems and move data in between.     |      SQL systems can also read and write data to Hadoop infrastructure     |      
| Cloudera, Horton work, AWS are some of the providers of Hadoop systems.     |      Microsoft, Oracle, SAP etc. are some of the well-known industry leaders in SQL systems     |      
| Last but not the least, the learning curve of Hadoop for entry-level professionals, as well as a seasoned professional, is moderately hard.     |      Starting with SQL systems is much easier for even entry-level professionals     |


----      