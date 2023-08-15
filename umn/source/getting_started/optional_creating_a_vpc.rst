:original_name: us_topic_0055391336.html

.. _us_topic_0055391336:

(Optional) Creating a VPC
=========================

Scenarios
---------

A VPC provides an isolated virtual network for ECSs. You can configure and manage the network as required.

You can create a VPC by following the procedure provided in this section. Then, create subnets, security groups, and assign EIPs by following the procedure provided in subsequent sections based on your actual network requirements.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. On the console homepage, under **Network**, click **Virtual Private Cloud**.

#. On the **Virtual Private Cloud** page, click **Create VPC**.

#. On the **Create VPC** page, set parameters as prompted.

   A default subnet will be created together with a VPC and you can also click **Add Subnet** to create more subnets for the VPC.

   .. table:: **Table 1** Parameter descriptions

      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Category          | Parameter          | Description                                                                                                                                                                                                                                                                                                  | Example Value       |
      +===================+====================+==============================================================================================================================================================================================================================================================================================================+=====================+
      | Basic Information | Region             | Regions are geographic areas that are physically isolated from each other. The networks inside different regions are not connected to each other, so resources cannot be shared across different regions. For low network latency and quick resource access, select the region nearest to your target users. | N/A                 |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Basic Information | Name               | The VPC name                                                                                                                                                                                                                                                                                                 | VPC-001             |
      |                   |                    |                                                                                                                                                                                                                                                                                                              |                     |
      |                   |                    | The name can contain a maximum of 64 characters, including only letters, digits, underscores (_), hyphens (-), and periods (.). Spaces are not allowed.                                                                                                                                                      |                     |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Basic Information | IPv4 CIDR Block    | The CIDR block of the VPC. The CIDR block of a subnet can be the same as the CIDR block for the VPC (for a single subnet in the VPC) or a subset of the CIDR block for the VPC (for multiple subnets in the VPC).                                                                                            | 192.168.0.0/16      |
      |                   |                    |                                                                                                                                                                                                                                                                                                              |                     |
      |                   |                    | The following CIDR blocks are supported:                                                                                                                                                                                                                                                                     |                     |
      |                   |                    |                                                                                                                                                                                                                                                                                                              |                     |
      |                   |                    | 10.0.0.0 - 10.255.255.255                                                                                                                                                                                                                                                                                    |                     |
      |                   |                    |                                                                                                                                                                                                                                                                                                              |                     |
      |                   |                    | 172.16.0.0 - 172.31.255.255                                                                                                                                                                                                                                                                                  |                     |
      |                   |                    |                                                                                                                                                                                                                                                                                                              |                     |
      |                   |                    | 192.168.0.0 - 192.168.255.255                                                                                                                                                                                                                                                                                |                     |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Basic Information | Tag                | The VPC tag, which consists of a key and value pair. You can add a maximum of ten tags to each VPC.                                                                                                                                                                                                          | -  Key: vpc_key1    |
      |                   |                    |                                                                                                                                                                                                                                                                                                              | -  Value: vpc-01    |
      |                   |                    | The tag key and value must meet the requirements listed in :ref:`Table 2 <us_topic_0055391336__table248245914136>`.                                                                                                                                                                                          |                     |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Basic Information | Description        | Supplementary information about the VPC. This parameter is optional.                                                                                                                                                                                                                                         | N/A                 |
      |                   |                    |                                                                                                                                                                                                                                                                                                              |                     |
      |                   |                    | The description can contain a maximum of 255 characters and cannot contain angle brackets (< or >).                                                                                                                                                                                                          |                     |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet Settings   | AZ                 | The AZ of a VPC subnet.                                                                                                                                                                                                                                                                                      | eu-ch2-01           |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet Settings   | Name               | The subnet name.                                                                                                                                                                                                                                                                                             | Subnet-001          |
      |                   |                    |                                                                                                                                                                                                                                                                                                              |                     |
      |                   |                    | The name can contain a maximum of 64 characters, including only letters, digits, underscores (_), hyphens (-), and periods (.). Spaces are not allowed.                                                                                                                                                      |                     |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet Settings   | IPv4 CIDR Block    | The CIDR block for the subnet. This value must be within the VPC CIDR block.                                                                                                                                                                                                                                 | 192.168.0.0/24      |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet Settings   | IPv6 CIDR Block    | Specifies whether to enable IPv6.                                                                                                                                                                                                                                                                            | N/A                 |
      |                   |                    |                                                                                                                                                                                                                                                                                                              |                     |
      |                   |                    | If you select this option, the system automatically assigns an IPv6 CIDR block to the created subnet. Currently, the IPv6 CIDR block cannot be customized. IPv6 cannot be disabled after the subnet is created.                                                                                              |                     |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet Settings   | Advanced Settings  | Click the drop-down arrow to set advanced settings for the subnet, including **Gateway** and **DNS Server Address**.                                                                                                                                                                                         | ``-``               |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet Settings   | Gateway            | The gateway address of the subnet.                                                                                                                                                                                                                                                                           | 192.168.0.1         |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet Settings   | DNS Server Address | By default, two DNS server addresses are configured. You can change them if necessary. A maximum of five DNS server addresses can be configured. Multiple IP addresses must be separated using commas (,).                                                                                                   | 100.125.x.x         |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet Settings   | NTP Server Address | The IP address of the NTP server. This parameter is optional.                                                                                                                                                                                                                                                | 192.168.2.1         |
      |                   |                    |                                                                                                                                                                                                                                                                                                              |                     |
      |                   |                    | You can configure the NTP server IP addresses as required. The IP addresses are added in addition to the default NTP server addresses. If this parameter is left empty, no IP address of the NTP server is added.                                                                                            |                     |
      |                   |                    |                                                                                                                                                                                                                                                                                                              |                     |
      |                   |                    | A maximum of four IP addresses can be configured. Multiple IP addresses must be separated using commas (,).                                                                                                                                                                                                  |                     |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet Settings   | Tag                | The subnet tag, which consists of a key and value pair. You can add a maximum of ten tags to each subnet.                                                                                                                                                                                                    | -  Key: subnet_key1 |
      |                   |                    |                                                                                                                                                                                                                                                                                                              | -  Value: subnet-01 |
      |                   |                    | The tag key and value must meet the requirements listed in :ref:`Table 3 <us_topic_0055391336__table6536185812515>`.                                                                                                                                                                                         |                     |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet Settings   | Description        | Supplementary information about the subnet. This parameter is optional.                                                                                                                                                                                                                                      | ``-``               |
      |                   |                    |                                                                                                                                                                                                                                                                                                              |                     |
      |                   |                    | The description can contain a maximum of 255 characters and cannot contain angle brackets (< or >).                                                                                                                                                                                                          |                     |
      +-------------------+--------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+

   .. _us_topic_0055391336__table248245914136:

   .. table:: **Table 2** VPC tag key and value requirements

      +-----------------------+----------------------------------------------------------------------------+-----------------------+
      | Parameter             | Requirements                                                               | Example Value         |
      +=======================+============================================================================+=======================+
      | Key                   | -  Cannot be left blank.                                                   | vpc_key1              |
      |                       | -  Must be unique for the same VPC and can be the same for different VPCs. |                       |
      |                       | -  Can contain a maximum of 36 characters.                                 |                       |
      |                       | -  Can contain only the following character types:                         |                       |
      |                       |                                                                            |                       |
      |                       |    -  Uppercase letters                                                    |                       |
      |                       |    -  Lowercase letters                                                    |                       |
      |                       |    -  Digits                                                               |                       |
      |                       |    -  Special characters, including hyphens (-) and underscores (_)        |                       |
      +-----------------------+----------------------------------------------------------------------------+-----------------------+
      | Value                 | -  Can contain a maximum of 43 characters.                                 | vpc-01                |
      |                       | -  Can contain only the following character types:                         |                       |
      |                       |                                                                            |                       |
      |                       |    -  Uppercase letters                                                    |                       |
      |                       |    -  Lowercase letters                                                    |                       |
      |                       |    -  Digits                                                               |                       |
      |                       |    -  Special characters, including hyphens (-) and underscores (_)        |                       |
      +-----------------------+----------------------------------------------------------------------------+-----------------------+

   .. _us_topic_0055391336__table6536185812515:

   .. table:: **Table 3** Subnet tag key and value requirements

      +-----------------------+---------------------------------------------------------------------+-----------------------+
      | Parameter             | Requirements                                                        | Example Value         |
      +=======================+=====================================================================+=======================+
      | Key                   | -  Cannot be left blank.                                            | subnet_key1           |
      |                       | -  Must be unique for each subnet.                                  |                       |
      |                       | -  Can contain a maximum of 36 characters.                          |                       |
      |                       | -  Can contain only the following character types:                  |                       |
      |                       |                                                                     |                       |
      |                       |    -  Uppercase letters                                             |                       |
      |                       |    -  Lowercase letters                                             |                       |
      |                       |    -  Digits                                                        |                       |
      |                       |    -  Special characters, including hyphens (-) and underscores (_) |                       |
      +-----------------------+---------------------------------------------------------------------+-----------------------+
      | Value                 | -  Can contain a maximum of 43 characters.                          | subnet-01             |
      |                       | -  Can contain only the following character types:                  |                       |
      |                       |                                                                     |                       |
      |                       |    -  Uppercase letters                                             |                       |
      |                       |    -  Lowercase letters                                             |                       |
      |                       |    -  Digits                                                        |                       |
      |                       |    -  Special characters, including hyphens (-) and underscores (_) |                       |
      +-----------------------+---------------------------------------------------------------------+-----------------------+

#. Click **Create Now**.

.. |image1| image:: /_static/images/en-us_image_0000001175484388.png
