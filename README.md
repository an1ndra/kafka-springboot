🔑 Core Kafka Concepts & Keyword Definitions 

    Apache Kafka:
    A distributed event streaming platform used for building real-time data pipelines and streaming applications. 

    Topic:
    A category or feed name to which records are published. Topics are partitioned and replicated across brokers. 

    Partition:
    Topics are split into partitions for scalability and parallelism. Each partition is an ordered, immutable sequence of records. 

    Broker:
    A Kafka server that stores data and serves clients. A Kafka cluster consists of multiple brokers. 

    Producer:
    An application that publishes (writes) records to Kafka topics. 

    Consumer:
    An application that subscribes to topics and processes records from them. 

    Consumer Group:
    A group of consumers that jointly consume a topic. Each partition is consumed by only one consumer in the group. 

    Offset:
    A unique identifier for a record within a partition. Consumers track their position using offsets. 

    ZooKeeper (Legacy):
    Used in older Kafka versions for cluster coordination and metadata management. Kafka KRaft mode (KIP-500) now replaces ZooKeeper. 

    Kafka Cluster:
    A set of brokers working together to manage topics, partitions, replication, and fault tolerance. 
     

    Replication:
    Copies of partition data across brokers for fault tolerance. The leader handles reads/writes; followers replicate data. 

    ISR (In-Sync Replicas):
    Set of replicas that are caught up with the leader. Only ISRs are eligible for election as new leader. 

    Retention Period:
    How long Kafka retains messages in a topic before deletion (time-based or size-based). 

    Log Compaction:
    A cleanup policy that retains the latest value for each key in a topic (useful for changelog-type topics). 
     

    Kafka Connect:
    A tool for scalably streaming data between Kafka and external systems (e.g., databases, S3). 

    Kafka Streams:
    A client library for building stream-processing applications directly on Kafka topics. 
     

 
💬 Common Kafka Interview Questions 
Basic Level 

    What is Apache Kafka, and what are its main use cases?
    → Real-time analytics, log aggregation, event sourcing, messaging, stream processing. 

    Explain the role of a Kafka producer and consumer.
    → Producer writes data to topics; consumer reads from topics. 
     

    What is a partition, and why is Kafka topic partitioned?
    → Enables parallelism, scalability, and ordering within a partition. 

    How does Kafka ensure fault tolerance?
    → Through replication of partitions across brokers. 
     

    What is an offset, and how is it managed?
    → Offset tracks consumer position; can be auto-committed or manually committed.
     

Intermediate Level 

    What is the difference between at-least-once, at-most-once, and exactly-once semantics?
    → Relates to message delivery guarantees. Kafka supports exactly-once via idempotent producers and transactional APIs. 

    How does Kafka handle consumer failures?
    → Other consumers in the group rebalance and take over partitions. 

    What is log compaction, and when would you use it?
    → Keeps the latest value per key—ideal for maintaining state (e.g., user profiles). 

    Explain Kafka’s replication protocol.
    → Leader handles I/O; followers replicate. ISR ensures consistency. 

    What is the role of ZooKeeper in Kafka (pre-KRaft)?
       → Managed broker metadata, controller election, ACLs. Now deprecated in favor of KRaft. 
     

Advanced Level 

    How does Kafka achieve high throughput?
       → Sequential I/O, batching, zero-copy (sendfile), and efficient disk usage.
     

    What is Kafka KRaft mode?
       → ZooKeeper-free mode using internal Raft-based consensus for metadata.
     

    How do you monitor Kafka performance?
       → Use tools like Kafka Manager, Confluent Control Center, Prometheus + Grafana, or JMX metrics. 

    How would you handle a slow consumer?
       → Increase resources, optimize processing logic, or isolate it in its own consumer group. 

    Explain Kafka Streams vs. Kafka Connect.
       → Streams: for stream processing logic inside apps. Connect: for moving data in/out of Kafka. 
     
