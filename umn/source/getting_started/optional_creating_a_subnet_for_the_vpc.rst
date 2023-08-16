:original_name: vpn_03_0003.html

.. _vpn_03_0003:

(Optional) Creating a Subnet for the VPC
========================================

Scenarios
---------

A VPC comes with a default subnet. If the default subnet cannot meet your requirements, you can create one.

The subnet is configured with DHCP by default. When an ECS using this VPC starts, the ECS automatically uses DHCP to obtain an IP address.

Procedure
---------

#. Log in to the management console.

2. Click |image1| in the upper left corner and select the desired region and project.

3. On the console homepage, under **Network**, click **Virtual Private Cloud**.

4. In the navigation pane on the left, click **Virtual Private Cloud**.

5. On the **Virtual Private Cloud** page, locate the VPC for which a subnet is to be created and click the VPC name.

6. On the displayed **Subnets** tab, click **Create Subnet**.

7. Configure the required parameters.


   .. figure:: /_static/images/en-us_image_0000001177896070.png
      :alt: **Figure 1** Create Subnet

      **Figure 1** Create Subnet

   .. table:: **Table 1** Parameter descriptions

      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                                                                              | Example Value         |
      +=======================+==========================================================================================================================================================================================================================+=======================+
      | AZ                    | The AZ of a VPC subnet.                                                                                                                                                                                                  | eu-ch2-01             |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Name                  | The subnet name.                                                                                                                                                                                                         | Subnet                |
      |                       |                                                                                                                                                                                                                          |                       |
      |                       | The name can contain a maximum of 64 characters, including only letters, digits, underscores (_), hyphens (-), and periods (.). Spaces are not allowed.                                                                  |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | IPv4 CIDR Block       | The CIDR block for the subnet. This value must be within the VPC CIDR block.                                                                                                                                             | 192.168.0.0/24        |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | IPv6 CIDR Block       | Specifies whether to enable IPv6.                                                                                                                                                                                        | ``-``                 |
      |                       |                                                                                                                                                                                                                          |                       |
      |                       | After the IPv6 function is enabled, the system automatically assigns an IPv6 CIDR block to the created subnet. Currently, the IPv6 CIDR block cannot be customized. IPv6 cannot be disabled after the subnet is created. |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Advanced Settings     | Click the drop-down arrow to set advanced settings for the subnet, including **Gateway** and **DNS Server Address**.                                                                                                     | Default               |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Gateway               | The gateway address of the subnet.                                                                                                                                                                                       | 192.168.0.1           |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | DNS Server Address    | By default, two DNS server addresses are configured. You can change them if necessary. A maximum of five DNS server addresses can be configured. Multiple IP addresses must be separated using commas (,).               | 100.125.x.x           |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Tag                   | The subnet tag, which consists of a key and value pair. You can add a maximum of ten tags to each subnet.                                                                                                                | -  Key: subnet_key1   |
      |                       |                                                                                                                                                                                                                          | -  Value: subnet-01   |
      |                       | The tag key and value must meet the requirements listed in :ref:`Table 2 <vpn_03_0003__table42131827173915>`.                                                                                                            |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Supplementary information about the subnet. This parameter is optional.                                                                                                                                                  | ``-``                 |
      |                       |                                                                                                                                                                                                                          |                       |
      |                       | The description can contain a maximum of 255 characters and cannot contain angle brackets (< or >).                                                                                                                      |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

   .. _vpn_03_0003__table42131827173915:

   .. table:: **Table 2** Subnet tag key and value requirements

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

8. Click **OK**.

Notes
-----

When a subnet is created, there are five reserved IP addresses, which cannot be used. For example, in a subnet with CIDR block 192.168.0.0/24, the following IP addresses are reserved:

-  192.168.0.0: Network ID. This address is the beginning of the private IP address range and will not be assigned to any instance.
-  192.168.0.1: Gateway address.
-  192.168.0.253: Reserved for the system interface. This IP address is used by the VPC for external communication.
-  192.168.0.254: DHCP service address.
-  192.168.0.255: Network broadcast address.

If you set **Advanced Settings** to **Custom** during subnet creation, the reserved IP addresses may be different from the default ones, but there will still be five of them. The specific addresses depend on your subnet settings.

.. |image1| image:: /_static/images/en-us_image_0264435822.png
