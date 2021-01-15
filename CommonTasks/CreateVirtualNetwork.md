## Create the virtual network

1. Return to the Azure portal in the web browser.

1. If the Home page isn't currently displayed, click select the **Home** link in the upper left hand corner:

     ![The **Home** link on a page in the Azure portal](../ClouderaMigration/Images/1-Home-Link.png)

1. On the Home page select **Create a resource**.

    ![The Resource Groups icon on the Home page in the Azure portal](../ClouderaMigration/Images/1-Home-Page.png)

1. On the **New** page, in the **Search the Marketplace** box, type **virtual network**, and then select **Virtual Network** from the list that appears:

    ![The New page in the Azure portal. The user has selected **Virtual Network**](../ClouderaMigration/Images/1-New-Virtual-Network.png)

1. On the **Virtual Network** page, select **Create**.

1. On the **Basics** tab of the **Create virtual network** page, enter the following settings, and then select **Next : IP Addresses**:

    > [!NOTE]
    > In this table, replace the **9999** with the suffix that was generated to uniquely identify your resources as part of the lab setup.

    | Field | Value|
    |-|-|
    | Resource group | workshoprg*9999* |
    | Name | clustervnet*9999* |
    | Region | Select the same region used by the Cloudera or MapR virtual machine and the workshoprg*9999* resource group |

1. On the **IP Addresses** tab, enter the following settings, and then select **Review + create**:

    | Field | Value|
    |-|-|
    | IPv4 address space | Accept the default address space |
    | Add IPv6 address space | Leave unchecked |
    | Add subnet | Click the **default** subnet. In the **Edit subnet** pane, change the name of the subnet to **clustersubnet**, and then select **Save** |

    ![The **IP Addresses** tab for a new virtual network. The user has changed the name of the subnet to **clustersubnet**](../ClouderaMigration/Images/1-Edit-Subnet.png)

1. On the validation page, select **Create**, and wait while the virtual network is created.
