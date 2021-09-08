# Table of contents

1. [Repo Introduction](#repo-introduction)
1. [Exam Info](#exam-info)
1. [Meet Kafka](#meet-kafka)
1. Installing Kafka (#installing-kafka)
1. Kafka Producers
1. Kafka Consumers
1. Managing Kafka Programmatically
1. Kafka Internals
1. Reliable Data Delivery
1. Exactly Once Semantics
1. Building Data Pipelines
1. Cross Cluster Data Mirroring
1. Securing Kafka
1. Administering Kafka
1. Monitoring Kafka
1. Stream Processing

# Repo Introduction

This repo contains notes for [Kafka: The Definitive Guide (2nd Edition)](https://www.amazon.com/Kafka-Definitive-Real-Time-Stream-Processing-dp-1492043087/dp/1492043087/ref=dp_ob_title_bk). 

This will help you to pass the CCDAK exam.

# Exam Info

1. Exam blueprint - https://assets.confluent.io/m/3be6a7e566940163/original/20200331-Exam_Confluent_Certified_Developer.pdf?_ga=2.64271471.1934257699.1620549594-946330800.1620139033

1. Sample questions - https://assets.confluent.io/m/1eb934ef619a0ccc/original/20200331-Developer_Certification_Sample_Questions.pdf?_ga=2.64271471.1934257699.1620549594-946330800.1620139033

1. Schedule the exam - https://www.confluent.io/certification/

# Meet Kafka

1. Messages & Batches
    1. Message is a simple array of bytes to Kafka without any specific format.
    1. A key is an optional metadata of a message. Similar to the message, for Kafka, it is a array of bytes.
    1. By using a key & consistent hashing, Kafka makes sure that messages with the same key are always written in the same partition (unless partition count does not change).
1. Schemas
    1. Allows to keep data type-safe.
    1. Allows applications to be more decoupled & standardized.
1. Topics & Partitions
    1. Each topic can have multiple partitions.
    1. Data time ordering is only guaranteed in a  partition.
    1. Partitions can be spread across servers, but each one has only one leader.
1. Producers & Consumers
    1. By default, producer will balance out message across partitions using round robin. However, this can be altered to ask a producer to write in specific partitions based on conditions.
    1. Consumers keep the offset of what has been consumed either in ZooKeeper or Kafka itself.
    1. Consumer groups allow to scale horizontally & make sure that only one consumer in the group consumes the message.
1. Brokers & clusters
    1. Each server acts a broker.
    1. One broker in a cluster will act as the controller for administrative tasks.
    1. Default retention for messages is 7 days.
    1. Log compacted settings, if enabled, only saves the last message with a specific key.
    1. All producers must connect to the partition leader to publish message. However, consumers can read message from partition leader or followers.

# Installing Kafka

We will be using Confluent Kafka for the exercises.

Quick start (local install) - https://docs.confluent.io/platform/current/quickstart/ce-quickstart.html
# Kafka Producers

1. 
