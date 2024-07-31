# PySpark-for-Beginner-ETL

This document is designed to be read in parallel with the code in the `PySpark-for-Beginner-ETL` repository. Together, these constitute what we consider to be a 'best practices' approach to writing ETL jobs using Apache Spark and its Python ('PySpark') APIs. This project addresses the following topics:

- set up environment, var environment;
- how to structure ETL code in such a way that it can be easily tested and debugged;
- how to pass configuration parameters to a PySpark job;
- how to handle dependencies on other modules and packages; and,
- what constitutes a 'meaningful' test for an ETL job.

## Set up environment

Intall java 11
```sh
sudo apt-get install openjdk-11-jdk
```
