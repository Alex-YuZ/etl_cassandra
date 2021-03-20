# Introduction
A startup called **Sparkify** wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analysis team is particularly interested in understanding what songs users are listening to. Currently, there is no easy way to query the data to generate the results, since the data reside in a directory of CSV files on user activity on the app.

The goal of this project is to create an <font color=green>**[Apache Cassandra](https://cassandra.apache.org/)**</font> database which can create queries on song play data to answer the questions of interest.

Generally speaking, in this project, we model the data by creating tables in Apache Cassandra to run queries. We are provided with part of the ETL pipeline that transfers data from a set of CSV files within a directory to create a streamlined CSV file to model and insert data into Apache Cassandra tables.

<br></br>

# About the Datasets
In this project, we'll be working with one dataset: `event_data`. The directory of CSV files partitioned by date. Here are examples of filepaths to two files in the dataset:
```
event_data/2018-11-08-events.csv
event_data/2018-11-09-events.csv
event_data/2018-11-10-events.csv
event_data/2018-11-11-events.csv
event_data/2018-11-12-events.csv

...

```
There are **30** csv files in total in the `event_data` file.

The whole dataset has been already uploaded to [Dropbox](https://www.dropbox.com/sh/d56wvr5d1b5o10l/AACQlikmha7EtfTPZnfH-F6Ka?dl=0).

<br></br>

# The Main Steps

## STEP 1. Modeling your NoSQL database or Apache Cassandra database.
1. Design tables to answer the **queries outlined in the notebook**.

2. Write Apache Cassandra `CREATE KEYSPACE` and `SET KEYSPACE` statements.

3. Develop the `CREATE` statement for each of the tables to address each question.

4. Load the data with `INSERT` statement for each of the tables.

5. Include `IF NOT EXISTS` clauses in the `CREATE` statements to create tables only if the tables do not already exist. Include `DROP TABLE` statement for each table, this way we can run drop and create tables whenever we want to reset the database and test the ETL pipeline.


6. Test by running the proper select statements with the correct `WHERE` clause.

## STEP 2. Build ETL Pipeline.
1. Implement the logic in the notebook to iterate through each event file in `event_data` to process and create a new CSV file in Python.

2. Implement the Apache Cassandra `CREATE` and `INSERT` statements to load processed records into relevant tables in the data model.

3. Test by running `SELECT` statements after running the queries on your database.

<br></br>

# To Be Improved ...
There are still some of improvements that can be made in near future. For example, 
- When printng our the query results, we can define a function to enclose this process.
- As this project was implemented in the classroom virtual envirnment, it is highly necessary to be tested in our local machine for better unstanding the whole process such as env setup, debugging and other playarounds.

<br></br>

# Reference Links
1. [Understanding Cassandra’s data model and Cassandra Query Language (CQL)](https://www.oreilly.com/library/view/cassandra-the-definitive/9781491933657/ch04.html)

2. [Apache Cassandra: Compound Primary Key](https://docs.datastax.com/en/archived/cql/3.3/cql/cql_using/useCompoundPrimaryKeyConcept.html)

3. [Available Cassandra data types](https://docs.datastax.com/en/archived/cql/3.3/cql/cql_reference/cql_data_types_c.html)

4. [Composite Partition Key](https://docs.datastax.com/en/archived/cql/3.3/cql/cql_using/useCompositePartitionKeyConcept.html#useCompositePartitionKeyConcept)

5. [Difference between partition key, composite key and clustering key in Cassandra](https://stackoverflow.com/questions/24949676/difference-between-partition-key-composite-key-and-clustering-key-in-cassandra)
