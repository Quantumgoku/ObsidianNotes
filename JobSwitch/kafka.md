---
created: 2026-10-05T11:44
updated: 2026-10-05T11:51
---
Topic
a topic is a logical stream/category of records
Topics are divided into partitions.
Topic
    |-> Partition 0
    |-> Partition 1
    |-> Partition 2

partitions provides scalability and parallelism

**Consumer Group**
a cg is a set of consumers cooperating to consume a topic/
within a cg, a partition is noramally assigned to one consumer at a time
 Ex:
 3 partitions
 3 consumers
P0 - C1
P1 - C2
P2 - C3

if there are 5 consumers and only 3 partitions, at most 3 consumers can actively consume those partitions at that time..

**Kafka Ordering**
kafka guarantees ordering within a partition
does not provides global ordering across all partitions of a topic
if order matters for a particular entity, mssgs can be partitioned using a consistent key.














