## Populate the SQL Database

1. If you haven't already done so, on your desktop, open a **Command Prompt** window and sign in to the Cloudera virtual machine. The username is **azureuser***. Replace *\<ip_address\>* with the IP address of the virtual machine.

    ```PowerShell
    ssh azureuser@<ip address>
    ```

1. Start the **hive** utility:

    ```bash
    hive
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
    FIELDS TERMINATED BY '\t'
    ```
   
1. Run the command below to populate the **flighhtinfo** table with sample data:

    ```sql
    SET hive.strict.checks.bucketing=false;
    LOAD DATA LOCAL INPATH '/home/azureuser/apps/reports/flightinfo.tsv' 
    OVERWRITE 
    INTO TABLE flightinfo;
    ```

1. Run the following command to quit the **hive** utility and return to the shell prompt:

    ```sql
    exit;
    ```