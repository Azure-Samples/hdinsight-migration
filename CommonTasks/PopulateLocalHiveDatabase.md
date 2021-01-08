## Create and populate the local Hive database

1. Return to the SSH session on the Cloudera of MapR virtual machine.

1. Move to the apps/reports folder:

    ```bash
    cd ~/apps/reports
    ```
    
1. if you are connected to the Cloudera virtual machine, start the **hive** utility:

    ```bash
    hive
    ```

    If you are connected to the MapR virtual machine, start the **beeline** utility:

    ```bash
    beeline -n azureuser -u jdbc:hive2://localhost:10000/default
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
   
1. Run the command below to populate the **flightinfo** table with sample data:

    ```sql
    SET hive.strict.checks.bucketing=false;
    LOAD DATA LOCAL INPATH '/home/azureuser/apps/reports/flightinfo.tsv' 
    OVERWRITE 
    INTO TABLE flightinfo;
    ```

1. Run the following command to quit the **hive** or **beeline** utility and return to the shell prompt:

    ```sql
    # hive
    exit;

    # beeline
    !quit
    ```