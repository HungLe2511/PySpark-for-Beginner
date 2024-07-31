# PySpark-for-Beginner-ETL

! This project is built using Linux operating system (ubuntu 22.04)

This document is designed to be read in parallel with the code in the `PySpark-for-Beginner-ETL` repository. Together, these constitute what we consider to be a 'best practices' approach to writing ETL jobs using Apache Spark and its Python ('PySpark') APIs. This project addresses the following topics:

- set up environment, var environment;
- Resilient Distributed Datasets(RDD), Data Frame(DF), Spark SQL;
- Spark architechture;
- how to pass configuration parameters to a PySpark job;
- how to handle dependencies on other modules and packages; and,
- what constitutes a 'meaningful' test for an ETL job.

## Set up environment, var environment

Install java 11
```sh
sudo apt-get install openjdk-11-jdk
```

Install python 3.10
```sh
sudo apt install python3.10
```

Install spark (should install the full version of spark to use it, the version you install with `pip install pyspark` will be difficult to understand). After downloaded, install it
```sh
wget https://dlcdn.apache.org/spark/spark-3.5.1/spark-3.5.1-bin-hadoop3.tgz
tar -xzvf spark-3.5.1-bin-hadoop3.tgz
```

Set up variable environment, open file .bashrc by 
```sh
# open file
nano ~/.bashrc

# save config
source ~/.bashrc
```

and add
```sh
export SPARK_HOME=/path/to/spark
export PATH=$PATH:$SPARK_HOME/bin
```
## Resilient Distributed Datasets(RDD), Data Frame(DF), Spark SQL

![Codespace](image/RDD_DF_2.png)

All the data unit types used for calculations in spark
- Resilient Distributed Datasets(RDD) : data file in `RAM`, meta data `no`
- Data Frame(DF)                      : data file in `RAM`, meta data `yes`
- Spark SQL                           : data file in `Disk`, meta data `yes`



## How Spark Works

When spark is running, there are two most important operations in data transformation:
- Transformations : is a transformation on DDF, DF, spark SQL but in reality these transformations will not be performed until spark receives actions
- Actions : In Apache Spark, actions are operations that trigger the execution of computations defined on RDDs (Resilient Distributed Datasets), DataFrames, or Datasets. Unlike transformations, which define a new RDD, DataFrame, or Dataset from an existing one (but are lazy and do not trigger computation), actions cause Spark to execute the actual computation and produce a result.
![Codespace](image/1707004360663.png)

`Lazy transformation` : its very important for understand `How Spark work`
Example:





## Spark architechture
The system currently supports several cluster managers:

- Standalone — a simple cluster manager included with Spark that makes it easy to set up a cluster.
  
![Codespace](image/Standalone-Cluster.webp)

  
- Apache Mesos — a general cluster manager that can also run Hadoop MapReduce and service applications.

![Codespace](image/Apache-Mesos.png)


- Hadoop YARN — the resource manager in Hadoop 2.

![Codespace](image/yarn_arch.webp)
- Kubernetes — an open-source system for automating deployment, scaling, and management of containerized applications.

![Codespace](image/1_FIuvzHDPvibv6fV-2qdLrQ.webp)
