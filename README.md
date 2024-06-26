# IoT Data Streaming powered by Apache Kafka and Databricks: Harnessing Windows Performance Monitor to Power BI Dashboards

![databricks-streaming-project2 drawio](https://github.com/FlorentineDev/PerformanceMonitor_over_IoT/assets/16971296/9574a9de-ee13-4d04-a62d-d668849ed540)


This IoT project is designed to provide hands-on experience with Spark Structured Streaming while developing a data pipeline for Internet-of-Things application. The project focuses on extracting computer performance metrics monitored by Windows Performance Monitor, and employs a series of steps and technologies to expose produced data to Cloud through ETL Pipeline. After Data Cleaning and Processing into Databricks, Data is loaded into a table to allow visualization and dashboarding through Microsoft Power BI Client application, potentially installed on any Internet-connected device.

Key Components:

\ **Microsoft Windows Performance Monitor** : The project initiates with the setup of Windows Performance Monitor to generate continuous performance data at 1-minute intervals.

![performancemonitor](https://github.com/FlorentineDev/IoT-powered-PerformanceMonitor/assets/16971296/9d9155c2-776f-43a1-bef8-1c68c720fea5)


\ **Python Script** : A custom Python script manages the produced CSV files, converts them into JSON strings, and transmit them to an Apache Kafka Server running on Confluent Cloud. This script is also responsible to search CSV files into Performance Monitor folder, and move them into a Destination Folder once data is properly transmitted to Kafka Server.

\ **Kafka Server on Confluent Cloud** : JSON-formatted performance data is published on a Kafka server hosted on Confluent Cloud, serving as the central hub for data dissemination.

![confluent 2](https://github.com/FlorentineDev/PerformanceMonitor_over_IoT/assets/16971296/4b2b8fff-5332-4618-8770-c0435a6a21fc)


\ **Databricks Cluster** : A Databricks Spark Cluster is established to consume data from the Kafka Server, by continuously ingesting data using Spark Structured Streaming technology. PySpark (Python) is programmed on the Cluster to execute multiple transformations, clean the data, and load it into a table. This facilitates external software, such as Microsoft Power BI, to connect to the Cluster for data analysis.

![databricks](https://github.com/FlorentineDev/PerformanceMonitor_over_IoT/assets/16971296/d4636f50-66b7-4ef4-8208-bccd6d392bd7)

\ **Microsoft Power BI** : The project integrates with Microsoft Power BI, allowing users to connect from their devices to the Databricks-generated table. Through Power BI, users can create dashboards and conduct in-depth data analysis.

![power BI dashboard](https://github.com/FlorentineDev/IoT-powered-PerformanceMonitor/assets/16971296/f57416fb-a238-4e00-9117-f8c66e9acbe8)
![power BI dashboard2](https://github.com/FlorentineDev/IoT-powered-PerformanceMonitor/assets/16971296/b6d163d4-1181-49d0-92a8-6abfe7ed36f9)


This Project leverages and takes inspiration from material of course **"Apache Spark and Databricks - Stream Processing in Lakehouse"** (https://www.udemy.com/course/spark-streaming-using-python).
I want to thank **Prashant Kumar Pandey** for the course and for the material provided with the course.
