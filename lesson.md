# Lesson

## Brief

### Preparation

- Please refer to the [installation.md](./installation.md) file for application setup instructions required for this module.

- For this lesson, we also need to setup a MongoDB account. Please refer to [the setup instructions](./installation.md#preparation-for-lesson-21)

### Lesson Overview

This lesson introduces the concept of big data and data engineering. It also introduces one of the most popular NoSQL databases- MongoDB, and how to perform CRUD operations.

---

## Part 1 - Introduction to big data

Conceptual knowledge, refer to slides.


💡💡💡 **Big Data Tools and Technologies** 💡💡💡

Overview of five Apache open-source tools used to store, move and process very large datasets.

## Summary

| Tool | Main function | Real-life example |
|---|---|---|
| **Hadoop** | Stores huge datasets across many cheap servers (HDFS) and processes them in parallel batches (MapReduce). | Yahoo was an early large-scale user, storing and processing web-scale data on Hadoop clusters for search indexing and ad analysis. |
| **Kafka** | Distributed messaging system that carries streams of events (clicks, payments, sensor readings) between systems in real time, with events stored in order. | LinkedIn created Kafka to move activity data such as page views and messages between its systems. Uber and Netflix also use it for event pipelines. |
| **Spark** | Fast, in-memory engine for large-scale data processing: batch jobs, SQL, machine learning and streaming. Usually much faster than Hadoop MapReduce. | Processing viewing logs at scale to train and update recommendation models (Netflix-style analytics). Banks and retailers use it for churn and fraud analysis. |
| **Flink** | Stream-processing engine for continuous, low-latency processing of live data, with accurate handling of event timing. | Alibaba uses Flink for real-time dashboards and recommendations during Singles' Day, where results are needed within seconds. |
| **Hive** | SQL-like layer (HiveQL) on top of Hadoop, so analysts can query huge stored datasets without writing code. | Facebook built Hive so analysts could run SQL-style queries over its very large Hadoop warehouse, for example for ad reporting. |

## How they fit together in one pipeline

1. **Kafka** collects live events, such as an order or a click.
2. **Flink** processes them instantly, for example flagging a fraudulent payment.
3. **Hadoop (HDFS)** stores the full history cheaply.
4. **Spark** analyses that history in bulk, for example to train a model.
5. **Hive** lets business analysts query the stored data with SQL.

```text
Events -> Kafka -> Flink (real time) -> alerts / dashboards
                \
                 -> Hadoop HDFS -> Spark (batch / ML) -> models
                               \
                                -> Hive (SQL queries) -> reports
```

## Quick comparison

| Question | Best fit |
|---|---|
| Where do I store massive data cheaply? | Hadoop (HDFS) |
| How do I move live events between systems? | Kafka |
| How do I process data in bulk or train ML models? | Spark |
| How do I react to data in milliseconds or seconds? | Flink |
| How do I let analysts query data with SQL? | Hive |


<br>

---

## Part 2 - Introduction to data engineering

Conceptual knowledge, refer to slides.

---

## Part 3 - Hands-on with MongoDB

We will be using the `notebooks/nosql_lesson.ipynb` notebook throughout this lesson.

> Open the notebook in VSCode by double clicking on the file. Then select `bde` conda environment for the kernel.
>
> Follow on with the lesson in the notebook.
