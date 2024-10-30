# Smart City Streaming Data Pipeline
The Smart City Streaming Data Pipeline simulates a dynamic, real-time data infrastructure, streaming information from simulated smart city sensors such as vehicle, GPS, weather, traffic, and emergency incident data. Using ```Kafka``` for robust data streaming and ```Apache Spark``` for real-time processing, this pipeline efficiently routes and processes large-scale data, storing it in ```S3``` as ```Parquet files``` for optimized access and storage. Key features include realistic data generation simulating a vehicle journey covering aspects like location, speed, weather conditions, and incident status. ```JSON``` serialization with Kafka producer callbacks ensures reliable data handling, while configurable environment variables offer deployment flexibility. Built with Docker, the pipeline leverages a containerized environment for isolated, scalable, and modular development.

# Architecture
This architecture leverages Docker containers to encapsulate Spark, Kafka, and Zookeeper, enabling consistent and modular deployments

  1. **Data Generation:** Each data type (vehicle, GPS, weather, traffic, and emergency) is generated with Python and serialized to JSON.
  
  2. **Kafka Streaming:** Kafka serves as the data bus, with dedicated topics for each data source.
  
  3. **Spark Streaming:** Spark processes and stores data streams, using schemas to parse each data type.
     
  4. **S3 Storage:** Final data is stored as Parquet files on S3 with checkpoints, supporting historical analysis.
