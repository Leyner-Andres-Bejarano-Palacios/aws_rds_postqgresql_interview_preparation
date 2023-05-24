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

### Theorical Question 9

Do you know what the performance insights are and where to find them is ?


<details><summary><b>Answer</b></summary>

Performance Insights in Amazon RDS expands on existing Amazon RDS monitoring features to illustrate and help you analyze your database performance. With the Performance Insights dashboard, you can visualize the database load on your Amazon RDS DB instance. You can also filter the load by waits, SQL statements, hosts, or users

In the picture below click where it say session

![Image](img/performanceInsights.png "performance Insights")

</details>

<details><summary><b>Source</b></summary>
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.RDS_Fea_Regions_DB-eng.Feature.DualStackMode.html#Concepts.RDS_Fea_Regions_DB-eng.Feature.DualStackMode.pg
</details>

### Theorical Question 10

what is the DB instance RAM recommendations ?


<details><summary><b>Answer</b></summary>

An Amazon RDS performance best practice is to allocate enough RAM so that your working set resides almost completely in memory. The working set is the data and indexes that are frequently in use on your instance. The more you use the DB instance, the more the working set will grow.

To tell if your working set is almost all in memory, check the ReadIOPS metric (using Amazon CloudWatch) while the DB instance is under load. The value of ReadIOPS should be small and stable. In some cases, scaling up the DB instance class to a class with more RAM results in a dramatic drop in ReadIOPS. In these cases, your working set was not almost completely in memory. Continue to scale up until ReadIOPS no longer drops dramatically after a scaling operation, or ReadIOPS is reduced to a very small amount.

</details>

<details><summary><b>Source</b></summary>
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_BestPractices.html
</details>

### Theorical Question 11

Do you know what the vacuum command is for in posgresql ?


<details><summary><b>Answer</b></summary>

VACUUM reclaims storage occupied by dead tuples. In normal PostgreSQL operation, tuples that are deleted or obsoleted by an update are not physically removed from their table; they remain present until a VACUUM is done. Therefore it's necessary to do VACUUM periodically, especially on frequently-updated tables.

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/current/sql-vacuum.html
</details>


### Theorical Question 12

Do you know what the analize command is for in posgresql ?


<details><summary><b>Answer</b></summary>

ANALYZE collects statistics about the contents of tables in the database, and stores the results in the pg_statistic system catalog. Subsequently, the query planner uses these statistics to help determine the most efficient execution plans for queries.

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/current/sql-analyze.html
</details>


### Theorical Question 13

Do you know what types of scans can you see in the explain command in posgresql ?


<details><summary><b>Answer</b></summary>

 sequential scans, index scans, and bitmap index scans. There are also non-table row sources, such as VALUES clauses and set-returning functions in FROM, which have their own scan node types. If the query requires joining, aggregation, sorting, or other operations on the raw rows, then there will be additional nodes above the scan nodes to perform these operations.

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/current/sql-analyze.html
</details>

### Theorical Question 14

How can you optimize postgreql in aws rds ?


<details><summary><b>Answer</b></summary>

https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_BestPractices.html#CHAP_BestPractices.PostgreSQL

</details>

<details><summary><b>Source</b></summary>
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_BestPractices.html#CHAP_BestPractices.PostgreSQL
</details>

### Theorical Question 15

How would you filter a query with aggregate ?


<details><summary><b>Answer</b></summary>

The fundamental difference between WHERE and HAVING is this: WHERE selects input rows before groups and aggregates are computed (thus, it controls which rows go into the aggregate computation), whereas HAVING selects group rows after groups and aggregates are computed. Thus, the WHERE clause must not contain aggregate functions; it makes no sense to try to use an aggregate to determine which rows will be inputs to the aggregates. On the other hand, the HAVING clause always contains aggregate functions. 

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/current/tutorial-agg.html
</details>



### Theorical Question 16

How do you know by the cli in postgresql that you are seeing a superuser ?


<details><summary><b>Answer</b></summary>

![Image](img/superUserCli.png "super UserCli")

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/current/tutorial-agg.html
</details>

### Theorical Question 17

Casting is pretty similar to how we do it in snowflake


<details><summary><b>Answer</b></summary>

![Image](img/castingInPostgresql.png "casting In Postgresql")

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/current/tutorial-agg.html
</details>

### Theorical Question 18

What is filter for in postgresql


<details><summary><b>Answer</b></summary>

![Image](img/filterPosgresql.png "filter Posgresql")

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/current/tutorial-agg.html
</details>

### Theorical Question 19

What are generated columns in posqgresql


<details><summary><b>Answer</b></summary>

![Image](img/generatedColumns.png "generated Columns")

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/current/tutorial-agg.html
</details>

### Theorical Question 20

The primary key section is essential


<details><summary><b>Answer</b></summary>

![Image](img/primaryKeySection.png "primary Key Section")

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/current/tutorial-agg.html
</details>


### Theorical Question 21

Do you know what cascade is for in postgresql


<details><summary><b>Answer</b></summary>

![Image](img/cascade.png "cascade")

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/current/tutorial-agg.html
</details>

### Theorical Question 22

In postgresql is not necessary to have an authorized view for doing row level security, it has a feature for granting permission in a per row basis


<details><summary><b>Answer</b></summary>

![Image](img/rowSecurity.png "rowSecurity")

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/current/tutorial-agg.html
</details>

### Theorical Question 23

When do we need a partition in postgresql and when a sequential scan is better than an index

<details><summary><b>Answer</b></summary>

![Image](img/partition_part1.png "partition_part1")

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/current/tutorial-agg.html
</details>

### Theorical Question 24

Well we can have an index per partition and is also important to enable prunning

<details><summary><b>Answer</b></summary>

![Image](img/partition_part2.png "partition_part2")

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/current/tutorial-agg.html
</details>

### Theorical Question 25

Great example of using the explain command for optimizing partitions

<details><summary><b>Answer</b></summary>

![Image](img/explaningWithExplain.png "explaningWithExplain")

![Image](img/explaining_with_explain_part2.png "explaining_with_explain_part2")

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/current/tutorial-agg.html
</details>

### Theorical Question 26

are cte evaluated only once per execution in postgresql ?

<details><summary><b>Answer</b></summary>

A useful property of WITH queries is that they are normally evaluated only once per execution of the parent query, even if they are referred to more than once by the parent query or sibling WITH queries. Thus, expensive calculations that are needed in multiple places can be placed within a WITH query to avoid redundant work.

![Image](img/snowflakeMaterializeQuery.png "snowflakeMaterializeQuery")

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/current/tutorial-agg.html
</details>

### Theorical Question 27

how do you control The fractional precision of a monetary daata type ?

<details><summary><b>Answer</b></summary>

The fractional precision is determined by the database's lc_monetary setting.

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/15/datatype-money.html
</details>

### Theorical Question 28

the character Tip  of posgresql

<details><summary><b>Answer</b></summary>

There is no performance difference among these three types, apart from increased storage space when using the blank-padded type, and a few extra CPU cycles to check the length when storing into a length-constrained column. While character(n) has performance advantages in some other database systems, there is no such advantage in PostgreSQL; in fact character(n) is usually the slowest of the three because of its additional storage costs. In most situations text or character varying should be used instead.

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/15/datatype-character.html
</details>

### Theorical Question 29

Optimizing multiRange with indixes

<details><summary><b>Answer</b></summary>

![Image](img/multiRangeIndex.png "multiRangeIndex")

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/15/datatype-character.html
</details>

### Theorical Question 30

Useful postgres administration function

<details><summary><b>Answer</b></summary>

https://www.postgresql.org/docs/15/functions-admin.html

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/15/functions-admin.html
</details>

### Theorical Question 31

Use case of indexes

<details><summary><b>Answer</b></summary>

If there are many rows in test1 and only a few rows (perhaps zero or one) that would be returned by such a query, this is clearly an inefficient method. But if the system has been instructed to maintain an index on the id column, it can use a more efficient method for locating matching rows. For instance, it might only have to walk a few levels deep into a search tree.

Once an index is created, no further intervention is required: the system will update the index when the table is modified, and it will use the index in queries when it thinks doing so would be more efficient than a sequential table scan. But you might have to run the ANALYZE command regularly to update statistics to allow the query planner to make educated decisions.

Creating an index on a large table can take a long time. By default, PostgreSQL allows reads (SELECT statements) to occur on the table in parallel with index creation, but writes (INSERT, UPDATE, DELETE) are blocked until the index build is finished. In production environments this is often unacceptable. It is possible to allow writes to occur in parallel with index creation, but there are several caveats to be aware of — for more information see Building Indexes Concurrently.

After an index is created, the system has to keep it synchronized with the table. This adds overhead to data manipulation operations. Indexes can also prevent the creation of heap-only tuples. Therefore indexes that are seldom or never used in queries should be removed.

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/15/indexes-intro.html
</details>


### Theorical Question 32

Use case of indexes

<details><summary><b>Answer</b></summary>

https://www.postgresql.org/docs/15/indexes-types.html

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/15/indexes-types.html
</details>

### Theorical Question 33

Why you should not create indexes in a unique columns ?

<details><summary><b>Answer</b></summary>

There's no need to manually create indexes on unique columns; doing so would just duplicate the automatically-created index.

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/15/indexes-unique.html
</details>

### Theorical Question 34

How can we use an index in one column to extract data from another column ?

<details><summary><b>Answer</b></summary>

https://www.postgresql.org/docs/15/indexes-index-only-scans.html

</details>

<details><summary><b>Source</b></summary>
https://www.postgresql.org/docs/15/indexes-index-only-scans.html
</details>