:original_name: vpn_03_0802.html

.. _vpn_03_0802:

Adding a Security Group Rule
============================

Scenarios
---------

After you create a security group, you can add rules to the security group. A rule applies either to inbound traffic or outbound traffic. After you add cloud resources to the security group, they are protected by the rules of the group.

-  Inbound rules control incoming traffic to ECSs associated with the security group.
-  Outbound rules control outgoing traffic from ECSs associated with the security group.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. On the console homepage, under **Network**, click **Virtual Private Cloud**.

#. In the navigation pane on the left, choose **Access Control** > **Security Groups**.

#. On the **Security Groups** page, locate the target security group and click **Manage Rule** in the **Operation** column to switch to the page for managing inbound and outbound rules.

#. On the **Inbound Rules** tab, click **Add Rule**. In the displayed dialog box, set required parameters.

   You can click **+** to add more inbound rules.


   .. figure:: /_static/images/en-us_image_0000001223494611.png
      :alt: **Figure 1** Add Inbound Rule

      **Figure 1** Add Inbound Rule

   .. table:: **Table 1** Inbound rule parameter descriptions

      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                | Example Value         |
      +=======================+============================================================================================================================================+=======================+
      | Protocol/Application  | Specifies the network protocol. The option can be **All**, **TCP**, **UDP**, **ICMP**, or **GRE**.                                         | TCP                   |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Type                  | Specifies the IP address type.                                                                                                             | IPv4                  |
      |                       |                                                                                                                                            |                       |
      |                       | -  IPv4                                                                                                                                    |                       |
      |                       | -  IPv6                                                                                                                                    |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Port & Source         | **Port**: specifies the port or port range over which the traffic can reach your ECS.                                                      | 22, or 22-30          |
      |                       |                                                                                                                                            |                       |
      |                       | Supported range: 1 to 65535                                                                                                                |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      |                       | **Source**: specifies the source of the security group rule. The source can be another security group or a single IP address. For example: | 0.0.0.0/0             |
      |                       |                                                                                                                                            |                       |
      |                       | -  xxx.xxx.xxx.xxx/32 (IPv4 address)                                                                                                       |                       |
      |                       | -  xxx.xxx.xxx.0/24 (subnet CIDR block)                                                                                                    |                       |
      |                       | -  0.0.0.0/0 (any IP address)                                                                                                              |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | (Optional) Provides supplementary information about the security group rule.                                                               | N/A                   |
      |                       |                                                                                                                                            |                       |
      |                       | The description can contain a maximum of 255 characters and cannot contain angle brackets (< or >).                                        |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. On the **Outbound Rules** tab, click **Add Rule**. In the displayed dialog box, set required parameters.

   You can click **+** to add more outbound rules.


   .. figure:: /_static/images/en-us_image_0000001223173339.png
      :alt: **Figure 2** Add Outbound Rule

      **Figure 2** Add Outbound Rule

   .. table:: **Table 2** Outbound rule parameter descriptions

      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                               | Example Value         |
      +=======================+===========================================================================================================================================================+=======================+
      | Protocol/Application  | Specifies the network protocol. The option can be **All**, **TCP**, **UDP**, **ICMP**, or **GRE**.                                                        | TCP                   |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Type                  | Specifies the IP address type.                                                                                                                            | IPv4                  |
      |                       |                                                                                                                                                           |                       |
      |                       | -  IPv4                                                                                                                                                   |                       |
      |                       | -  IPv6                                                                                                                                                   |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Port & Destination    | **Port**: specifies the port or port range over which the traffic can leave your ECS.                                                                     | 22, or 22-30          |
      |                       |                                                                                                                                                           |                       |
      |                       | Supported range: 1 to 65535                                                                                                                               |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      |                       | **Destination**: specifies the destination of the security group rule. The destination can be another security group or a single IP address. For example: | 0.0.0.0/0             |
      |                       |                                                                                                                                                           |                       |
      |                       | -  xxx.xxx.xxx.xxx/32 (IPv4 address)                                                                                                                      |                       |
      |                       | -  xxx.xxx.xxx.0/24 (subnet CIDR block)                                                                                                                   |                       |
      |                       | -  0.0.0.0/0 (any IP address)                                                                                                                             |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | (Optional) Provides supplementary information about the security group rule.                                                                              | N/A                   |
      |                       |                                                                                                                                                           |                       |
      |                       | The description can contain a maximum of 255 characters and cannot contain angle brackets (< or >).                                                       |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0264455393.png
