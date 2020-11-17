# HDInsight Migration Workshop

In this lab, you'll learn how to migrate some common workloads running on a Cloudera cluster to HDInsight 4.0.

---

**IMPORTANT:**

This lab creates several HDInsight clusters and a virtual machine for running Cloudera. Make sure that you delete these resources when you have finished, otherwise you will generate considerable charges.

Additionally, an HDInsight cluster comprises a number of virtual machines. You may need to request an increase in the quota for the number of CPU cores for your subscription (96 cores recommended, for DSv2, DSv3, Dv2, and Dv3 series virtual machines). For more information, read [Standard quota: Increase limits by VM series](https://docs.microsoft.com/azure/azure-portal/supportability/per-vm-quota-requests).

---

Before starting this lab, [read the introduction and perform the setup steps](Cloudera%20Migration/Instructions/0-Introduction.md).

This lab contains four exercises showing how to:

1. [Migrate a Cloudera Kafka workload to an Azure HDInsight Kafka cluster by using Kafka Mirroring](Cloudera%20Migration/Instructions/1-KafkaMigration.md),

1. [Migrate a Cloudera Hive workload to an Azure HDInsight LLAP cluster by using Hive replication](Cloudera%20Migration/Instructions/2-HiveMigration.md),

1. [Migrate a Cloudera HBase database to an Azure HDInsight HBase cluster by using HBase snapshots](Cloudera%20Migration/Instructions/3-HBaseMigration.md), and

1. [Migrate a Cloudera Spark workload to an Azure HDInsight Spark cluster, using HDFS tools and AzCopy to transfer data](Cloudera%20Migration/Instructions/4-SparkMigration.md). 
