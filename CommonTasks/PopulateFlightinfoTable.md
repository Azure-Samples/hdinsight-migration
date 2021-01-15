## Populate the SQL database

---

**NOTE:**
This procedure shows a quick way to transfer a small amount of data held as a CSV file into a temporary table Hive in . This approach is not scalable; you should not follow this approach for large-scale production data.

---

1.  In the Azure portal, open a Cloud Shell prompt running PowerShell.

1. Run the following command to create a directory named **temp** in the filesystem for the HDInsight cluster. Replace **\<9999\>** with the numeric suffix you used for the cluster storage account:

    ```PowerShell
    az storage fs directory create `
        --name temp `
        --file-system cluster<9999> `
        --account-name clusterstorage<9999>
    ```

1. Retrieve the storage account keys for the storage account:

    ```PowerShell
    Get-AzStorageAccountKey `
        -ResourceGroupName 'workshoprg<9999>' `
        -AccountName 'clusterstorage<9999>'
    ```

1. Return to the shell prompt for the SSH session connected to the Azure HDInsight head node.

1. Start the **beeline** utility:

    ```bash
    beeline -u 'jdbc:hive2://localhost:10001/;transportMode=http'
    ```

1. Run the following command to create the **flightinfo** table:

    ```sql
    CREATE TABLE IF NOT EXISTS flightinfo ( 
        `timestamp` string,
        year string,
        month string,
        dayofmonth string,
        deptime string,
        depdelay int,
        arrtime string,
        arrdelay int,
        carrier string,
        flightnum string,
        elapsedtime int,
        origin string,
        dest string,
        distance int)
    COMMENT 'Flight information'
    ROW FORMAT DELIMITED
    FIELDS TERMINATED BY ','
    LINES TERMINATED BY '\n'
    STORED AS TEXTFILE LOCATION '/temp/flightinfo.csv';
    ```

1. Exit the **beeline** utility and return to the shell prompt:

    ```sql
    !quit
    ```

1. Switch to the **Command Prompt** window running the SSH session for the Cloudera or MapR virtual machine.

1. Move to the apps/reports folder:

    ```bash
    cd ~/apps/reports
    ```

1. Copy the **flightinfo.csv** file to the **temp** folder in Azure storage. Replace **\<key\>** with the storage account key you just noted. This is the location of the table in Hive:


    ```bash
    hdfs dfs \
    -D fs.azure.account.key.clusterstorage<9999>.blob.core.windows.net='<key>' \
    -copyFromLocal \
        flightinfo.csv \
        'wasbs://cluster<9999>@clusterstorage<9999>.blob.core.windows.net/temp/flightinfo.csv'
    ```

1. Return to the shell prompt for the SSH session connected to the Azure HDInsight head node.

1. Start the **beeline** utility:

    ```bash
    beeline -u 'jdbc:hive2://localhost:10001/;transportMode=http'
    ```

1. Run the following command to update the statistical data for the **flightinfo** table:

    ```sql
    ANALYZE TABLE flightinfo COMPUTE STATISTICS;
    ```

1. Exit the **beeline** utility and return to the shell prompt:

    ```sql
    !quit
    ```

