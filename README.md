# DE-Project-AWStoSnowflake
End-to-end real-time data pipeline using AWS Lambda, DynamoDB, and Snowflake via Snowpipe.



This project demonstrates my hands-on implementation of a real-time data pipeline on AWS. The solution involves ingesting weather data via an external API, storing it in DynamoDB, and then transferring it to Snowflake using AWS Lambda and Snowpipe. The goal was to build an efficient, scalable, and near real-time data pipeline leveraging AWS-native and cloud data warehouse tools.

Project Components

 1. DynamoDB & Snowflake Integration

I utilized Amazon DynamoDB as the initial data store for incoming API data due to its low latency and scalability. I then set up Snowflake as the analytical data warehouse to enable querying and analysis of historical weather trends.

 2. AWS Lambda for Real-Time Processing

AWS Lambda was used to:

 Fetch data periodically from a weather API.
 Transform and load the weather data into DynamoDB.
 Trigger further processing (or S3 staging) for Snowpipe ingestion.

3. Real-Time Weather Data Ingestion

Using a public Weather API, I scheduled Lambda to fetch and store weather metrics like temperature, humidity, and wind speed in DynamoDB at regular intervals.

4. Data Transfer to Snowflake Using Snowpipe

I configured Snowpipe for automatic loading of staged data (via S3) into Snowflake. This enabled near real-time analytics with minimal lag and no manual intervention.

5. Pipeline Optimization

Implemented strategies to:

 Minimize Lambda execution time.
 Ensure efficient writes to DynamoDB.
 Optimize Snowpipe performance for cost and latency.

6. Challenges Faced & Learnings

During the project, I encountered challenges with:

 Setting up cross-service permissions (IAM roles and policies).
 Tuning Lambda memory/runtime.
 Managing data format conversions for Snowflake ingestion.

I addressed these through detailed debugging, AWS documentation, and logs from CloudWatch.



Tools & Technologies Used

 AWS Lambda
 Amazon DynamoDB
 Amazon S3
 Snowflake & Snowpipe
 Python (Boto3, Requests)
 Weather API (OpenWeatherMap / similar)
