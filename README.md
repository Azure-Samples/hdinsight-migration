# HDInsight Migration Workshop

In this lab, you'll learn how to migrate some common workloads running on a Cloudera cluster to HDInsight 4.0.

---

**IMPORTANT:**

This lab creates several HDInsight clusters and a virtual machine for running Cloudera. Make sure that you delete these resources when you have finished, otherwise you will generate considerable charges.

Additionally, an HDInsight cluster comprises a number of virtual machines. You may need to request an increase in the quota for the number of CPU cores for your subscription before starting this lab. For more information, read [Requesting quota increases for Azure HDInsight](https://docs.microsoft.com/en-us/azure/hdinsight/quota-increase-request).

---

Before starting this lab, [read the introduction and perform the setup steps](Cloudera%20Migration/Instructions/0-Introduction.md).

This lab contains four exercises showing how to:

1. [Migrate a Cloudera Kafka workload to an Azure HDInsight Kafka cluster by using Kafka Mirroring](Cloudera%20Migration/Instructions/1-KafkaMigration.md),

1. [Migrate a Cloudera Hive workload to an Azure HDInsight LLAP cluster by using Hive export and import](Cloudera%20Migration/Instructions/2-HiveMigration.md),

1. [Migrate a Cloudera Spark workload to an Azure HDInsight Spark cluster, using HDFS tools to transfer data](Cloudera%20Migration/Instructions/3-SparkMigration.md), and 

1. [Migrate a Cloudera HBase database to an Azure HDInsight HBase cluster by using HBase snapshots](Cloudera%20Migration/Instructions/4-HBaseMigration.md).


