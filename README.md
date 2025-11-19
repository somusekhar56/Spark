# SPARK
# 1 Hadoop Introduction:
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
 # 1 Very Fast (In-Memory Processing)
 Spark keeps data in RAM instead of reading/writing to disk repeatedly.
This makes Spark up to 100x faster than MapReduce.

# 2 Unified Platform
Spark supports many tasks in one framework:
Spark SQL (SQL queries)
Spark Streaming (real-time data)
MLlib (machine learning)
GraphX (graph processing)

# 3 Easy to Use
Supports Python (PySpark), Scala, Java, R, and SQL.
Easy APIs → fewer lines of code.
# 4 Real-Time Processing
Unlike MapReduce, Spark supports real-time data streams.
# 5 Fault Tolerant
Uses RDDs (Resilient Distributed Datasets) with lineage information.
Automatically recovers lost data.
# 6 Scalable
Can scale from a single laptop to thousands of cluster nodes.
# 7 Works with Hadoop Ecosystem
Compatible with HDFS, YARN, Hive, HBase, etc.

# 2 Comparison: Apache Spark vs Hadoop MapReduce
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

# 3 Spark Architecture Overview:
3.1 Understanding the Key Components of the Spark Architecture. Below are the main components of the Spark architecture:
# Spark Architecture Diagram 
<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/f4f29aa3-9b94-4bd1-8db5-f82dfb53d08e" />

# 1 Driver Program
The main control process of a Spark application.
Contains the SparkContext which coordinates all activities.
# Responsible for:
Converting the user program into tasks
Scheduling tasks
Tracking job progress
Communicating with the cluster manager

# 2 SparkContext
The “heart” of any Spark application.
Creates RDDs, accumulators, broadcast variables.
Connects the Driver with the Cluster Manager.

# 3 Cluster Manager
Responsible for providing resources (CPU, memory) to run Spark jobs.
Spark can work with:
Standalone cluster manager (default)
YARN (Hadoop)
Mesos
Kubernetes

# 4 Executors
Worker processes launched on each cluster node.
Executed tasks sent by the Driver.
Store data in memory through caching.
Perform actual computation on RDDs/DataFrames.

# 5 Worker Nodes
Machines in the cluster where Executors run.
Each worker can run multiple executors.

# 6 Tasks
The smallest unit of work in Spark.
Each task performs operations on a partition of data.

# 7 RDD / DataFrame / Dataset
Distributed data abstractions.
RDD → low-level distributed collections
DataFrame/Dataset → high-level structured data

# Summary of Components
| Component       | Role                                |
| --------------- | ----------------------------------- |
| Driver          | Controls execution, schedules tasks |
| SparkContext    | Connects driver & cluster manager   |
| Cluster Manager | Allocates resources                 |
| Executors       | Run tasks & store data              |
| Worker Nodes    | Machines running executors          |
| Tasks           | Small units of execution            |
| RDD/DataFrame   | Distributed data                    |

# 3.2 Interaction Between Components During Execution
Here is the step-by-step flow of how a Spark application runs:

#  Step 1: Application Starts
User runs the program (PySpark, Scala, etc.).
The Driver Program starts and creates a SparkContext.

# Step 2: SparkContext Connects to Cluster Manager
SparkContext requests resources (CPU, memory).
Cluster manager finds suitable worker nodes.

#  Step 3: Executors Are Launched
Cluster manager assigns worker nodes to run executors.
Executors register themselves with the driver.

# Step 4: Driver Divides the Job into Stages & Tasks
Spark breaks RDD/DataFrame transformations into DAG (Directed Acyclic Graph).
DAG → converted into stages
Stages → broken into tasks based on data partitions

# Step 5: Tasks Are Sent to Executors
Executors run tasks in parallel across the cluster.

# Step 6: Executors Perform Computation
Read input data
Execute transformations
Store intermediate data in memory (cache)
Write results back to the driver or storage

#  Step 7: Driver Collects Results
Finally, the driver program collects results and displays output.

# Interaction Flow Diagram (Text Explanation)
User Program → Driver Program → SparkContext → Cluster Manager → Executors 
→ Execute Tasks → Return Results → Driver → Output

# Easy Summary
* Driver
Controls everything.
* SparkContext
Connects driver to cluster.
* Cluster Manager
Allocates resources.
* Executors
Do the real work.
* Tasks
Small pieces of work executed on executors.

# Core Concepts in Spark:
2.1 RDD (Resilient Distributed Dataset): Immutable distributed collections of objects.
The fundamental data structure in Spark.An immutable, distributed collection of objects.
# Supports:
Fault tolerance
Parallel processing
Lazy evaluation
# RDDs are processed using:
Transformations (map, filter, flatMap)
Actions (collect, count, reduce)

# 2.2 Spark Core: The foundation of the Spark platform.The base engine of the Spark platform.
# Provides:
Memory management
Task scheduling
Fault recovery
RDD operations
All other Spark modules (SQL, Streaming, MLlib, GraphX) run on top of Spark Core.

# 2.3 Spark SQL: Spark module for structured data processing.
Used for processing structured and semi-structured data.
# Provides:
DataFrames
Datasets
SQL query support

# 2.4 Spark Streaming: Real-time data processing 
Module for real-time data processing.Processes live data streams from:
Kafka ,Flume ,Socket streams
# Two APIs:
DStreams (older)
Structured Streaming (modern)
Used for applications like real-time dashboards and fraud detection.

# 2.5 MLlib (Machine Learning Library): Machine learning library for Spark.
Spark’s built-in machine learning library.
# Supports:
Classification
Regression
Clustering
Recommendation systems
Feature extraction
ML Pipelines
Designed for distributed machine learning on large datasets.

# 2.6 GraphX: Graph processing library for Spark.
# Used to work with:
Graph data
Network structures
Social network analysis
# Provides:
Pre-built algorithms (PageRank, Connected Components)
Graph operators
Supports both graph and RDD APIs.



