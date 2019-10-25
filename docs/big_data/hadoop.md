## Hadoop Framework :
##### 1. Common Utilities:
- Also called the Hadoop common. 
- These are nothing but the JAVA libraries, files, scripts, and utilities that are actually required by the other Hadoop components to perform.

##### 2. HDFS: Hadoop Distributed File System
- **Solves the problem of storing big data.** 
- Why Hadoop has chosen to incorporate a Distributed file system?
- Let’s understand this with an example: 
    - We need to read  1TB of data and we have one machine with 4 I/O channels each channel having 100MB/s, it took 45 minutes to read the entire data. 
    - Now the same amount of data is read by 10 machines each with 4 I/O channels each channel having 100MB/s. 
    - Guess the amount of time it took to read the data? 4.3 minutes. 

- The two main components of HDFS are: 
    1. **NAME NODE.**
        - Name node is the master, 
        - We may have a secondary name node as well in case the primary name node stops working the secondary name node will act as a backup. 
        - The name node basically maintains and manages the data nodes by storing metadata.
    2. **DATA NODE.**
        -  The data node is the slave which is basically the low-cost commodity hardware. 
        - We can have multiple data nodes. 
        - The data node stores the actual data. 
        - This data node supports the replication factor, suppose if one data node goes down then the data can be accessed by the other replicated data node, therefore, the accessibility of data is improved and loss of data is prevented.

##### 3. Map Reduce:
- **Solves the problem of processing big data.** 
- Let’s understand the concept of map reduces by solving this real-world problem.
    - ABC company wants to calculate its total sales, city wise. 
    - Now here the hash table concept won’t work because the data is in terabytes, so we will use the Map-Reduce concept.
        - There are two phases: 
            1. MAP
                - First, we will split the data into smaller chunks called the mappers on the basis of the key/value pair. 
                - So here the key will be the city name and the value will be total sales. 
                - Each mapper will get each month’s data which gives a city name and corresponding sales.
            2. REDUCE
                - It will get these piles of data and each reducer will be responsible for North/West/East/South cities. 
                - So the work of the reducer will be collecting these small chunks and convert into larger amounts (by adding them up) for a particular city. 

##### 4. YARN Framework: 
- **It is the middle layer between HDFS and Map Reduce which is responsible for managing cluster resources.**
- Yet another resource negotiator.
- The initial version of Hadoop had just two components: Map Reduce and HDFS. 
    - Later it was realized that Map Reduce couldn’t solve a lot of big data problems. 
    - The idea was to take the resource management and job scheduling responsibilities away from the old map-reduce engine and give it to a new component. 
    - This is how YARN came into the picture. 
- It is having two key roles to perform: 
    1. **Job Scheduling**
        - When a large amount of data is giving for processing, it needs to be distributed and broken down into different tasks/jobs.
        - Now the JS decides which job needs to be given the top priority, the time interval between two jobs, dependency among the jobs, checks that there is no overlapping between the jobs running. 
    2. **Resource management**
        - For processing the data and for storing the data we need resources right? 
        - So the resource manager provides, manages and maintains the resources to store and process the data.

