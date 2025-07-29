# Stock Market Real-Time Data Analysis Using Kafka
This project demonstrates my journey in building an end-to-end real-time data engineering pipeline that processes stock market data using Apache Kafka and AWS services. I developed this system to understand streaming data architectures and gain hands-on experience with modern data engineering tools.

## Project Overview
I built a complete data pipeline that simulates real-time stock market feeds, processes them through Kafka, stores them in AWS S3, and enables SQL-based analytics. The entire system handles thousands of events per minute and provides sub-second query responses.

## Why I Built This Project
As a data engineering student, I wanted to understand how financial companies handle real-time data streams. Stock market data is perfect for this because it's high-frequency, time-sensitive, and requires reliable processing. This project helped me learn industry-standard tools like Kafka while working with realistic financial data scenarios.

## Technical Architecture
My pipeline follows this flow:
![Image Alt](https://github.com/AjinkyaDahiwal/StockMarket-Data-Engineering-Project/blob/8027179a6ee1f2c91eb586556d5f3f53bb45f168/Stock%20Market%20Data%20Engineering%20Project/Architecture/Architecture.jpg)

Data Source: Python script that reads historical stock data and simulates live market feeds

Stream Processing: Apache Kafka cluster running on AWS EC2 for reliable message handling

Storage: Amazon S3 as the data lake for all processed records

Schema Management: AWS Glue Crawler for automatic table creation and updates

Analytics: Amazon Athena for serverless SQL queries

### Stream Processing
My producer application converts stock data to JSON and publishes to Kafka topics. The consumer application subscribes to these topics, batches the messages, and writes them to S3 in an organized folder structure partitioned by date.

### Data Lake and Analytics
I configured AWS Glue Crawler to automatically detect new data files in S3 and update the schema in the Glue Data Catalog. This enables analysts to query the data using standard SQL through Amazon Athena without managing any infrastructure.

### Note :
1. To not incurr any charges I stopped all the aws services after use.
2. Final codes are in respective folders for producer and consumer and also the cli commands to create kafka server and test it.
3. All related screenshots are in screenshots folder.

### Bucket to store data and crawler runned on this bucket's stored data to build glue catalog to run queries on athena :
![Image Alt](https://github.com/AjinkyaDahiwal/StockMarket-Data-Engineering-Project/blob/7f60844479ee4d6dd47b8e6722f292c382387f95/Stock%20Market%20Data%20Engineering%20Project/Screenshots/Screenshot%20(31).png)
![Image Alt](https://github.com/AjinkyaDahiwal/StockMarket-Data-Engineering-Project/blob/27f76707d9bf7447d5d03ca157a2266189582d60/Stock%20Market%20Data%20Engineering%20Project/Screenshots/Screenshot%20(42).png)
![Image Alt](https://github.com/AjinkyaDahiwal/StockMarket-Data-Engineering-Project/blob/27f76707d9bf7447d5d03ca157a2266189582d60/Stock%20Market%20Data%20Engineering%20Project/Screenshots/Screenshot%20(43).png)

### Testing the kafka server , broker, producer and consumer :
![Image Alt](https://github.com/AjinkyaDahiwal/StockMarket-Data-Engineering-Project/blob/7f60844479ee4d6dd47b8e6722f292c382387f95/Stock%20Market%20Data%20Engineering%20Project/Screenshots/Screenshot%20(32).png)
![Image Alt](https://github.com/AjinkyaDahiwal/StockMarket-Data-Engineering-Project/blob/7f60844479ee4d6dd47b8e6722f292c382387f95/Stock%20Market%20Data%20Engineering%20Project/Screenshots/Screenshot%20(30).png)

### Each second the data getting updated which satisfies our goal to build real time pipeline : 
![Image Alt](https://github.com/AjinkyaDahiwal/StockMarket-Data-Engineering-Project/blob/7f60844479ee4d6dd47b8e6722f292c382387f95/Stock%20Market%20Data%20Engineering%20Project/Screenshots/Screenshot%20(35).png)
![Image Alt](https://github.com/AjinkyaDahiwal/StockMarket-Data-Engineering-Project/blob/7f60844479ee4d6dd47b8e6722f292c382387f95/Stock%20Market%20Data%20Engineering%20Project/Screenshots/Screenshot%20(38).png)
![Image Alt](https://github.com/AjinkyaDahiwal/StockMarket-Data-Engineering-Project/blob/7f60844479ee4d6dd47b8e6722f292c382387f95/Stock%20Market%20Data%20Engineering%20Project/Screenshots/Screenshot%20(39).png)
