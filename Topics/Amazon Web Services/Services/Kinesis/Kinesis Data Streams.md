
# What is Kinesis Data Streams?
You can use Amazon Kinesis Data Streams to collect and process large [streams](https://aws.amazon.com/streaming-data/) of data records in real time. You can create data-processing applications, known as _Kinesis Data Streams applications_. A typical Kinesis Data Streams application reads data from a _data stream_ as data records. These applications can use the Kinesis Client Library, and they can run on Amazon EC2 instances. You can send the processed records to dashboards, use them to generate alerts, dynamically change pricing and advertising strategies, or send data to a variety of other AWS services.

# Concepts
![[Pasted image 20230507160939.png]]

# Architecture
![[Pasted image 20230507161201.png]]

# SQS vs Kinesis
![[Pasted image 20230507161416.png]]
Kinesis for huge scale data ingestion. Otherwise, SQS by default

# References
[What Is Amazon Kinesis Data Streams?](https://docs.aws.amazon.com/streams/latest/dev/introduction.html)