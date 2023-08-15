:original_name: vpn_03_0801.html

.. _vpn_03_0801:

Creating a Security Group
=========================

Scenarios
---------

You can create security groups, define security group rules, and add ECSs in the VPC to the security groups, improving ECS access security. It is recommended that you allocate ECSs that have different Internet access policies to different security groups.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. On the console homepage, under **Network**, click **Virtual Private Cloud**.

#. In the navigation pane on the left, choose **Access Control** > **Security Groups**.

#. On the **Security Groups** page, click **Create Security Group**.

#. In the **Create Security Group** area, set the parameters as prompted. :ref:`Table 1 <vpn_03_0801__en-us_topic_0118534004_table65377617111335>` lists the parameters to be configured.


   .. figure:: /_static/images/en-us_image_0249852263.png
      :alt: **Figure 1** Create Security Group

      **Figure 1** Create Security Group

   .. _vpn_03_0801__en-us_topic_0118534004_table65377617111335:

   .. table:: **Table 1** Parameter descriptions

      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                           | Example Value         |
      +=======================+=======================================================================================================================================================================+=======================+
      | Name                  | Specifies the security group name. This parameter is mandatory.                                                                                                       | sg-318b               |
      |                       |                                                                                                                                                                       |                       |
      |                       | The name can contain a maximum of 64 characters, which may consist of letters, digits, underscores (_), hyphens (-), and periods (.). The name cannot contain spaces. |                       |
      |                       |                                                                                                                                                                       |                       |
      |                       | .. note::                                                                                                                                                             |                       |
      |                       |                                                                                                                                                                       |                       |
      |                       |    You can change the security group name after a security group is created. It is recommended that you give each security group a different name.                    |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Provides supplementary information about the security group. This parameter is optional.                                                                              | ``-``                 |
      |                       |                                                                                                                                                                       |                       |
      |                       | The description can contain a maximum of 255 characters and cannot contain angle brackets (< or >).                                                                   |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0264455395.png
