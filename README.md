# SPARK
# Hadoop Introduction:
Hadoop is an open-source framework used to store and process large-scale data (Big Data) across a cluster of computers using distributed computing.
# Key Purpose of Hadoop
# Hadoop solves three big problems of Big Data:
1 Volume – Huge amount of data (TB, PB)
2 Velocity – High-speed data generation
3 Variety – Different types of data (structured, semi-structured, unstructured)
# Hadoop Core Components
# 1 HDFS (Hadoop Distributed File System) – Storage
Stores big files by splitting them into blocks.
Distributes blocks across many machines in a cluster.
Maintains replication for fault tolerance.
# 2 YARN (Yet Another Resource Negotiator) – Resource Management
Allocates CPU, memory, and resources to different jobs.
Schedules and manages tasks.
# 3 MapReduce – Data Processing Model
Processes data in parallel across cluster nodes.
Two phases:
1 Map → Splits work
2 Reduce → Combines output

# 1 Role of Hadoop in Distributed Computing
Hadoop enables:
# Parallel processing
Thousands of machines work together at the same time.
# Fault tolerance
If one machine fails, data is automatically recovered through replication.
# Scalability
You can add more machines to increase capacity.
# Cost efficiency
Runs on inexpensive commodity hardware.
# Handling any type of data
Text, images, videos, logs, social media, IoT, etc.

# 2 Historical Context and Evolution:
# Early Days (Pre-Hadoop Era)
#Before Hadoop, companies struggled with:
# 1 Huge datasets
# 2 Slow storage systems
# 3 Expensive hardware
# 4 Limited parallel processing
This led to the need for a scalable and distributed system.

# Hadoop traces back to two main innovations by Google:
# Google File System (GFS) – 2003
 # Introduced the idea of:
 1 Distributed storage
 2 File splitting
 3 Data replication

#  MapReduce – 2004
Introduced parallel data processing.

# Birth of Hadoop
Doug Cutting and Mike Cafarella created Hadoop in 2006.
It started as part of the Nutch search engine project.
They needed a system similar to GFS + MapReduce → Hadoop was born.

# 3 Hadoop Grows (Evolution Timeline)
2006: Hadoop released as an Apache open-source project
2008: Hadoop became a top-level Apache project
2011: YARN introduced → Improved resource management
2012 onwards: Hadoop ecosystem expanded
Tools like:Hive,Pig,HBase,Spark,Sqoop,Oozie,Zookeeper

# 4 Hadoop Today
Widely used in big companies (Facebook, Yahoo, Amazon, Netflix).
Foundation for modern big data technologies.
Spark and modern cloud platforms evolved from the Hadoop ecosystem.

# 2. Spark Introduction:
Apache Spark is an open-source distributed computing framework designed for fast big data processing.
It provides high-speed performance using in-memory computation, which makes it much faster than traditional big data tools like Hadoop MapReduce.

# Spark supports multiple workloads in a single unified system:
* Batch processing
* Real-time stream processing
* Machine learning
* Graph processing
* SQL-based analytics

# Spark can run on:
* Hadoop cluster (YARN)
* Standalone mode
* Kubernetes
*Cloud platforms (AWS, Azure, GCP)

Advantages of Apache Spark
1️⃣ Very Fast (In-Memory Processing)
Spark keeps data in RAM instead of reading/writing to disk repeatedly.
This makes Spark up to 100x faster than MapReduce.
2️⃣ Unified Platform
Spark supports many tasks in one framework:
Spark SQL (SQL queries)
Spark Streaming (real-time data)
MLlib (machine learning)
GraphX (graph processing)
3️⃣ Easy to Use
Supports Python (PySpark), Scala, Java, R, and SQL.
Easy APIs → fewer lines of code.
4️⃣ Real-Time Processing
Unlike MapReduce, Spark supports real-time data streams.
5️⃣ Fault Tolerant
Uses RDDs (Resilient Distributed Datasets) with lineage information.
Automatically recovers lost data.
6️⃣ Scalable
Can scale from a single laptop to thousands of cluster nodes.
7️⃣ Works with Hadoop Ecosystem
Compatible with HDFS, YARN, Hive, HBase, etc.

Comparison: Apache Spark vs Hadoop MapReduce
| Feature              | **Apache Spark**                     | **Hadoop MapReduce**         |
| -------------------- | ------------------------------------ | ---------------------------- |
| **Processing Speed** | Very fast (in-memory)                | Slow (disk-based)            |
| **Data Processing**  | Batch + Real-time                    | Batch only                   |
| **Programming Ease** | Simple APIs (Python, SQL)            | Complex (Java)               |
| **Latency**          | Low                                  | High                         |
| **Use Cases**        | ML, streaming, graphs, analytics     | Batch ETL, long-running jobs |
| **Memory Usage**     | Uses RAM for caching                 | Uses disk for all steps      |
| **Fault Tolerance**  | Through RDD lineage                  | Data replication in HDFS     |
| **Integration**      | Works with Hadoop, cloud, Kubernetes | Mainly Hadoop ecosystem      |
| **Performance**      | Up to 100x faster                    | Slower due to disk I/O       |

📌 Summary
# Apache Spark
High-speed, in-memory big data processing engine
Supports real-time + batch workloads
Easier to use and highly scalable
Widely used for ML, streaming, analytics
# Hadoop MapReduce
Disk-based batch processing
Slower and older technology
Good for long-running, heavy batch jobs
