# aws_rds_postqgresql_interview_preparation

here we go !!

## Theorical Questions Section

### Theorical Question 1

why would you use aws rds instead of just putting databases into ec2 instances ?

<details><summary><b>Answer</b></summary>
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html#Welcome.Concepts.RDS
</details>

<details><summary><b>Source</b></summary>
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html#Welcome.Concepts.RDS
</details>


### Theorical Question 2

how pricing works for aws rds

<details><summary><b>Answer</b></summary>

This is a database in a ec2 instance managed by aws, the reserved instances also apply here

</details>

<details><summary><b>Source</b></summary>
https://aws.amazon.com/rds/pricing/
</details>

### Theorical Question 3

how would you know what type of instance do you need ?

<details><summary><b>Answer</b></summary>

By cheking the cloudwatch monitoring section in the UI

![Image](img/monitorringRDS.png "monitorring RDS")

</details>

<details><summary><b>Source</b></summary>
https://www.youtube.com/watch?v=vXZLUL309ek
</details>

### Theorical Question 4

What is the shared responsability model ?

<details><summary><b>Answer</b></summary>

Amazon RDS is responsible for hosting the software components and infrastructure of DB instances and DB cluster. You are responsible for query tuning, which is the process of adjusting SQL queries to improve performance. Query performance is highly dependent on database design, data size, data distribution, application workload, and query patterns, which can vary greatly. Monitoring and tuning are highly individualized processes that you own for your RDS databases

</details>

<details><summary><b>Source</b></summary>
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html#Welcome.Concepts.RDS
</details>

### Theorical Question 5

There are new generations of each storage classes coming every often, how can you modify the db instance class ?

<details><summary><b>Answer</b></summary>

Some modifications result in downtime because Amazon RDS must reboot your DB instance for the change to take effect.

https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.DBInstance.Modifying.html

</details>

<details><summary><b>Source</b></summary>
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html#Welcome.Concepts.RDS
</details>

### Theorical Question 6

what type of instance storage would you use when you need Provisioned IOPS storage is designed to meet the needs of I/O-intensive workloads, particularly database workloads, that require low I/O latency and consistent I/O throughput.?

<details><summary><b>Answer</b></summary>

Provisioned IOPS SSD – Provisioned IOPS storage is designed to meet the needs of I/O-intensive workloads, particularly database workloads, that require low I/O latency and consistent I/O throughput. Provisioned IOPS storage is best suited for production environments.

</details>

<details><summary><b>Source</b></summary>
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Storage.html
</details>

### Theorical Question 7

Do you know what these metrics are ?

- IOPS
- Latency
- Throughput
- Queue Depth

<details><summary><b>Answer</b></summary>

IOPS – The number of I/O operations completed each second. This metric is reported as the average IOPS for a given time interval. Amazon RDS reports read and write IOPS separately on 1-minute intervals. Total IOPS is the sum of the read and write IOPS. Typical values for IOPS range from zero to tens of thousands per second.

Latency – The elapsed time between the submission of an I/O request and its completion. This metric is reported as the average latency for a given time interval. Amazon RDS reports read and write latency separately at 1-minute intervals. Typical values for latency are in milliseconds (ms).

Throughput – The number of bytes each second that are transferred to or from disk. This metric is reported as the average throughput for a given time interval. Amazon RDS reports read and write throughput separately on 1-minute intervals using units of megabytes per second (MB/s). Typical values for throughput range from zero to the I/O channel's maximum bandwidth.

Queue Depth – The number of I/O requests in the queue waiting to be serviced. These are I/O requests that have been submitted by the application but have not been sent to the device because the device is busy servicing other I/O requests. Time spent waiting in the queue is a component of latency and service time (not available as a metric). This metric is reported as the average queue depth for a given time interval. Amazon RDS reports queue depth in 1-minute intervals. Typical values for queue depth range from zero to several hundred

</details>

<details><summary><b>Source</b></summary>
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Storage.html
</details>

### Theorical Question 8

Do you know what dual stack is ?


<details><summary><b>Answer</b></summary>

By using dual-stack mode in RDS, resources can communicate with a DB instance over Internet Protocol version 4 (IPv4), Internet Protocol version 6 (IPv6), or both

</details>

<details><summary><b>Source</b></summary>
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.RDS_Fea_Regions_DB-eng.Feature.DualStackMode.html#Concepts.RDS_Fea_Regions_DB-eng.Feature.DualStackMode.pg
</details>