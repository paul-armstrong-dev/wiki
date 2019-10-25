Difference Between Apache Pig and Apache Hive
The Apache Pig story begins in the year 2006 when the researcher as Yahoo was struggling with MapReduce Java codes. It was difficult to reuse and maintain code for compilation.  At the same time, they observed that MapReduce users were not comfortable with declarative languages such as SQL. They started to work on new language that was supposed to fit in a sweet spot between the declarative style of SQL, low-level and procedural style of MapReduce. This resulted in the birth of Pig and the first release of Pig came in September 2008 and by end of 2009 about half of the jobs at Yahoo were Pig jobs.

The Apache Hive story begins in the year 2007 when non-Java Programmer have to struggle while using Hadoop MapReduce. IT professional from database background were facing challenges to work on Hadoop Cluster. Initially, researchers, working at Facebook came up with Hive language. This language was very similar to SQL language. So language was called Hive Query Language (HQL) and later it becomes project of open source Apache Community. After becoming project of Apache Community there was a major development in Apache Hive. Facebook was the first company to come up with Apache Hive.

Let me explain about Apache Pig vs Apache Hive in more details.

 
Introducing Apache Pig vs Apache Hive
Apache Pig is a platform for analyzing large data sets that consists of a high-level language for expressing data analysis programs, coupled with infrastructure for evaluating these programs. Apache is open source project of Apache Community. Apache Pig provides a simple language called Pig Latin, for queries and data manipulation.

Pig is being utilized by companies like Yahoo, Google and Microsoft for collecting huge amounts of data sets in the form of click streams, search logs and web crawls.

Apache Pig provides nested data types like Maps, Tuples, and Bags
Apache Pig Follows multi-query approach to avoid multiple scans of the datasets.
Programmers familiar with scripting language prefer Apache Pig
Pig is easy if you are well aware of SQL
No need to create schema to work on Apache Pig
Pig also provides support to major data operations like Ordering, Filters, and Joins
Apache Pig framework translates Pig Latin into sequences of MapReduce programs
 

Apache Hive data warehouse software facilitates reading, writing, and managing large datasets residing in distributed storage using SQL. Apache Hive is an Apache open-source project built on top of Hadoop for querying, summarizing and analyzing large data sets using a SQL-like interface. Apache hive provides the SQL-like language called HiveQL, which transparently convert queries to MapReduce for execution on large datasets stored in Hadoop Distributed File System (HDFS).

Apache Hive is a Data warehouse Infrastructure.
Apache Hive is an ETL tool (Extraction-Transformation-Loading)
Apache hive is similar to SQL
Apache Hive enables customized mappers and reducers
Apache Hive increases the schema design flexibility using data serialization and deserialization
Apache hive is an analytical tool

Key differences between Apache Pig vs Apache Hive:
Apache Pig is more faster comparing Apache Hive
Apache Pig and Apache Hive both runs on top of Hadoop MapReduce
Apache Pig is best for Structured and Semi-structured while Apache Hive is best for structured data
Apache Pig is a procedural language while Apache Hive is a declarative language
Apache Pig supports cogroup feature for outer joins while Apache Hive does not support
Apache Pig does not have a pre-defined database to store table/ schema while Apache Hive has pre-defined tables/schema and stores its information in a database.
Apache Pig is also suited for complex and nested data structure while Apache Hive is less suited for complex data
Researchers and programmers use Apache pig while Data Analysts use Apache Hive
When to use Apache Pig:
When you are a programmer and know scripting language
When you don’t want to create schema while loading
ETL requirements
When you are working on client side of the Hadoop cluster
When you are working on Avro Hadoop file format
When to use Apache Hive:
Data warehousing requirements
Analytical Queries of historical data
Data Analysis who are familiar with SQL
While working on structured data
By Data Analysts
To visualize and create reports
 
Apache Pig vs Apache Hive Comparison Table
I am discussing major artifacts and distinguishing between Apache Pig and Apache Hive.


| 	| Apache Pig | 	Apache Hive |
|---|------------|--------------| 
| Data Processing     |      Apache Pig is High-level data flow language     |      Apache Hive is used for batch processing i.e. Online Analytical Processing (OLAP)     |      
| Processing Speed     |      Apache Pig has higher latency because of executing MapReduce job in background     |      Apache Hive also has higher latency because of executing MapReduce job in background      |      
| Compatibility with Hadoop     |      Apache Pig runs on top of MapReduce     |      Apache Hive also runs on top of MapReduce     |      
| Definition     |      Apache Pig is open source, high-level data flow system that renders you a simple language platform properly known as Pig Latin that can be used for manipulating data and queries.     |      Apache Hive is open source and  similar to SQL used for Analytical Queries     |      
| Language Used     |      Apache Pig uses procedural data flow language called Pig Latin     |      Apache Hive uses a declarative language called HiveQL                                         |      
| Schema     |      Apache Pig doesn’t have a concept of schema. You can store data in an alias.     |      Apache hive supports Schema for inserting data in tables     |      
| Web Interface     |      Apache Pig does not support web Interface     |      Apache Hive supports web interface     |      
| Operations     |      Apache Pig is used for Structured and Semi-Structured data     |      Apache Hive is used for structured data.     |      
| User Specification     |      Apache Pig is used by Researchers and Programmers     |      Apache Hive is used by Data Analyst     |      
| Operates On     |      Apache Pig operates on Client side of cluster     |      Apache hive Operates on Server side of Cluster     |      
| Partition Methods     |      There is no concept of Partition in Apache Pig     |      Apache Hive supports Sharding features     |      
| File Format     |      Apache Pig Supports Avro file format     |      Apache hive directly does not support Avro format but can support using “org.apache.hadoop.hive.serde2.avro”      |      
| JDBC / ODBC     |      Apache Pig does not support     |      Apache hive supports but limited     |      
| Debugging     |      It is easy to debug Pig scripts     |      We can debug, but it is bit complex | 