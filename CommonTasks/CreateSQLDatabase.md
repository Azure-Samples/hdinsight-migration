## Create the SQL database

1. Go to the Azure Home page and select **Create a resource**.

1. On the **New** page, in the **Search the Marketplace** box, type **SQL Database**, and then press Enter.

1. On the **SQL Database** page, select **Create**.

1. On the **Basics** tab of the **Create SQL Database** page, enter the following settings, and then select **Review + create**:

    | Field | Value|
    |-|-|
    | Subscription | Select your subscription |
    | Resource group | workshoprg*9999*, where *9999* is your unique identifier assigned when you created the Cloudera or MapR virtual machine |
    | Database name | hivedb*9999* |
    | Server | Select **Create new**. In the **New Server** pane, name the server **hiveserver*9999***, set the server admin login name to **azuresa**, provide a password of your choice, and specify the same location that you have used for other resources created during this lab. Select **OK**. |
    | Want to use SQL elastic pool | No |
    | Compute + storage | Select **Configure database**. On the **General Purpose** tab, select **Serverless**, and then click **Apply**. |

1. On the **Create SQL Database** page, select **Create**, and wait while the database and server are created.

1. On the Home page in the Azure portal, select **Resource Groups**, and then select the **workshoprg*9999*** resource group. 

1. On the **workshoprg*9999*** resource group page, select  **hivedb*9999***.

1. On the **hivedb*9999*** page, select **Set server firewall**.

    ![The SQL Database properties page in the Azure portal. The user has selected **Set server firewall**](../ClouderaMigration/Images/2-SQLDatabase.png)

1. On the **Firewall settings** page, set **Allow Azure services and resources to access this server** to **Yes**, select **Save**, and then select **OK** when the firewall has been updated.

    ![The **Firewall settings** page in the Azure portal. The user has opened the firewall to Azure services and resources](../ClouderaMigration/Images/2-SetFirewall.png)
