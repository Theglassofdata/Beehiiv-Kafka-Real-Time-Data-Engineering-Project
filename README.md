Real-Time Data Pipeline with Kafka and Snowflake
This project demonstrates a real-time data pipeline that reads data from a CSV file, simulates real-time ingestion using Kafka, and loads the data into Snowflake for storage and analysis. The CSV file is used to mimic a live data stream by introducing delays between records, making it a simple yet effective way to showcase a real-time data workflow.

Table of Contents
Technologies Used
Architecture
Prerequisites
Setup Instructions
Running the Project
Troubleshooting
License
Technologies Used
CSV Data Source: A static file used to simulate real-time data.
Apache Kafka: A distributed streaming platform with a producer and consumer.
Snowflake: A cloud data warehouse for storing and analyzing the data.
Python: The programming language used for scripting (version 3.x).
Architecture
The pipeline follows this flow:

CSV Data Source: Contains sample data in a file (e.g., data/data.csv) with columns like id, name, and value. This simulates a real-time feed.
Kafka Producer: A Python script (producer.py) reads the CSV row by row, adding a delay (e.g., 1 second) to mimic real-time data generation, and sends each row as a message to a Kafka topic (my_topic).
Kafka Consumer: Another Python script (consumer.py) subscribes to the my_topic topic, receives messages, and loads them into Snowflake.
Snowflake: Stores the data in a table (e.g., my_table) within a specified database and schema.
Here’s a simple diagram of the flow:

text
Wrap
Copy
CSV File --> Kafka Producer --> Kafka Topic (my_topic) --> Kafka Consumer --> Snowflake
Note: In a real-world scenario, the CSV would be replaced by a live data stream, but this project uses a file with delays for demonstration purposes.

Prerequisites
Before running the project, ensure you have:

Python 3.x installed on your system.
Access to a Kafka cluster (local or cloud-based).
A Snowflake account with permissions to create databases, schemas, and tables.
Required Python libraries: confluent_kafka, snowflake-connector-python, and pandas.
