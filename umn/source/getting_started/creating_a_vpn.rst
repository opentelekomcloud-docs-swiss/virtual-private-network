:original_name: en-us_topic_0060118606.html

.. _en-us_topic_0060118606:

Creating a VPN
==============

Overview
--------

By default, ECSs in a VPC cannot communicate with your on-premises network. To enable communications between them, use a VPN. You need to create a VPN in your VPC and update the security group rules.

Simple IPsec VPN Intranet Topology
----------------------------------

In :ref:`Figure 1 <en-us_topic_0060118606__fig19884520114220>`, the VPC has subnets 192.168.1.0/24 and 192.168.2.0/24. Your on-premises data center has subnets 192.168.3.0/24 and 192.168.4.0/24. You can create a VPN to enable subnets in your VPC to communicate with those in your data center.

.. _en-us_topic_0060118606__fig19884520114220:

.. figure:: /_static/images/en-us_image_0159197475.png
   :alt: **Figure 1** IPsec VPN

   **Figure 1** IPsec VPN

Both site-to-site and hub-and-spoke VPNs are supported. Set up VPNs in both your on-premises data center and the VPC to establish the VPN connection.

Ensure that the Internet Key Exchange (IKE) and IPsec policies at both ends of the VPN are the same.

Scenarios
---------

Perform the following procedure to create a VPN that sets up a secure, isolated communications tunnel between your data center and cloud services.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. On the console homepage, under **Network**, click **Virtual Private Network**.

#. On the **Virtual Private Network** page, click **Create VPN**.

#. Configure required parameters and click **Create Now**.


   .. figure:: /_static/images/en-us_image_0000001178055594.png
      :alt: **Figure 2** Create VPN

      **Figure 2** Create VPN

   .. table:: **Table 1** Basic parameters

      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                                                                                                                                                                  | Example Value         |
      +=======================+==============================================================================================================================================================================================================================================================================================================+=======================+
      | Region                | Regions are geographic areas that are physically isolated from each other. The networks inside different regions are not connected to each other, so resources cannot be shared across different regions. For low network latency and quick resource access, select the region nearest to your target users. | eu-ch2                |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Name                  | The VPN name                                                                                                                                                                                                                                                                                                 | VPN-001               |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | VPC                   | The VPC name                                                                                                                                                                                                                                                                                                 | VPC-001               |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Local Subnet          | The VPC subnets that will access your on-premises network through a VPN                                                                                                                                                                                                                                      | 192.168.1.0/24,       |
      |                       |                                                                                                                                                                                                                                                                                                              |                       |
      |                       | -  **Select subnet**: Select the subnets that will access your on-premises network through a VPN.                                                                                                                                                                                                            | 192.168.2.0/24        |
      |                       | -  **Specify CIDR block**: Enter the CIDR blocks that will access your on-premises network through a VPN.                                                                                                                                                                                                    |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Remote Gateway        | The public IP address of the gateway in your on-premises network. This IP address is used for communications with your VPC.                                                                                                                                                                                  | N/A                   |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Remote Subnet         | The subnets of your on-premises network that will access a VPC through a VPN The remote and local subnets cannot overlap. The remote subnet cannot overlap with CIDR blocks involved in existing VPC peering connections created for the VPC.                                                                | 192.168.3.0/24,       |
      |                       |                                                                                                                                                                                                                                                                                                              |                       |
      |                       | .. note::                                                                                                                                                                                                                                                                                                    | 192.168.4.0/24        |
      |                       |                                                                                                                                                                                                                                                                                                              |                       |
      |                       |    Using 100.64.0.0/10 as the customer subnet may cause services such as OBS, DNS, API Gateway to become unavailable.                                                                                                                                                                                        |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | PSK                   | The pre-shared key, a private key shared by two ends of a VPN connection for negotiation                                                                                                                                                                                                                     | Test@123              |
      |                       |                                                                                                                                                                                                                                                                                                              |                       |
      |                       | PSKs configured at both ends of the VPN connection must be the same.                                                                                                                                                                                                                                         |                       |
      |                       |                                                                                                                                                                                                                                                                                                              |                       |
      |                       | The key:                                                                                                                                                                                                                                                                                                     |                       |
      |                       |                                                                                                                                                                                                                                                                                                              |                       |
      |                       | -  Must be 6 to 128 characters long.                                                                                                                                                                                                                                                                         |                       |
      |                       | -  Can contain only:                                                                                                                                                                                                                                                                                         |                       |
      |                       |                                                                                                                                                                                                                                                                                                              |                       |
      |                       |    -  Digits                                                                                                                                                                                                                                                                                                 |                       |
      |                       |    -  Uppercase letters                                                                                                                                                                                                                                                                                      |                       |
      |                       |    -  Lowercase letters                                                                                                                                                                                                                                                                                      |                       |
      |                       |    -  Special characters: :literal:`~`!@#$%^()-_+=[]{}|\\,./:;`                                                                                                                                                                                                                                              |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Confirm PSK           | Enter the pre-shared key again.                                                                                                                                                                                                                                                                              | Test@123              |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Advanced Settings     | -  **Default**: uses default IKE and IPsec policies.                                                                                                                                                                                                                                                         | Custom                |
      |                       | -  **Existing**: uses existing IKE and IPsec policies. This option is available only after you have created IKE and IPsec policies.                                                                                                                                                                          |                       |
      |                       | -  **Custom**: uses custom IKE and IPsec policies. For details about the policies, see :ref:`Table 2 <en-us_topic_0060118606__en-us_topic_0013748707_table505541520388>` and :ref:`Table 3 <en-us_topic_0060118606__en-us_topic_0013748707_table4625367220388>`.                                             |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

   .. _en-us_topic_0060118606__en-us_topic_0013748707_table505541520388:

   .. table:: **Table 2** IKE policy

      +--------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter                | Description                                                                                                                                                             | Example Value         |
      +==========================+=========================================================================================================================================================================+=======================+
      | Authentication Algorithm | The hash algorithm used for authentication, which can be **SHA1**, **SHA2-256**, **SHA2-384**, **SHA2-512**, or **MD5**                                                 | SHA2-256              |
      |                          |                                                                                                                                                                         |                       |
      |                          | The default algorithm is **SHA2-256**.                                                                                                                                  |                       |
      +--------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Encryption Algorithm     | The encryption algorithm, which can be **AES-128**, **AES-192**, **AES-256**, or **3DES**                                                                               | AES-128               |
      |                          |                                                                                                                                                                         |                       |
      |                          | **3DES** is not recommended because it is not strong enough to protect data.                                                                                            |                       |
      |                          |                                                                                                                                                                         |                       |
      |                          | The default algorithm is **AES-128**.                                                                                                                                   |                       |
      +--------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | DH Algorithm             | The Diffie-Hellman key exchange algorithm, which can be **Group 2**, **Group 5**, **Group 14**, **Group 15**, **Group 16**, **Group 19**, **Group 20**, or **Group 21** | Group 14              |
      |                          |                                                                                                                                                                         |                       |
      |                          | The DH group security level from the highest to lowest is as follows: Group 21 > Group 20 > Group 19 > Group 16 > Group 15 > Group 14 > Group 5 > Group 2.              |                       |
      |                          |                                                                                                                                                                         |                       |
      |                          | The default algorithm is **Group 14**.                                                                                                                                  |                       |
      +--------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Version                  | The version of the IKE protocol, which can be **v1** or **v2**                                                                                                          | v2                    |
      |                          |                                                                                                                                                                         |                       |
      |                          | The default version is **v2**.                                                                                                                                          |                       |
      +--------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Lifecycle (s)            | The lifetime of the SA, in seconds.                                                                                                                                     | 86400                 |
      |                          |                                                                                                                                                                         |                       |
      |                          | The SA will be renegotiated if its lifetime expires.                                                                                                                    |                       |
      |                          |                                                                                                                                                                         |                       |
      |                          | The default lifecycle is **86400** seconds.                                                                                                                             |                       |
      +--------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Negotiation Mode         | If the IKE policy version is **v1**, the negotiation mode can be set to **Main** or **Aggressive**.                                                                     | Main                  |
      |                          |                                                                                                                                                                         |                       |
      |                          | The default mode is **Main**.                                                                                                                                           |                       |
      +--------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

   .. _en-us_topic_0060118606__en-us_topic_0013748707_table4625367220388:

   .. table:: **Table 3** IPsec policy

      +--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter                | Description                                                                                                                                                                                        | Example Value         |
      +==========================+====================================================================================================================================================================================================+=======================+
      | Authentication Algorithm | The hash algorithm used for authentication, which can be **SHA1**, **SHA2-256**, **SHA2-384**, **SHA2-512**, or **MD5**                                                                            | SHA2-256              |
      |                          |                                                                                                                                                                                                    |                       |
      |                          | The default algorithm is **SHA2-256**.                                                                                                                                                             |                       |
      +--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Encryption Algorithm     | The encryption algorithm, which can be **AES-128**, **AES-192**, **AES-256**, or **3DES**                                                                                                          | AES-128               |
      |                          |                                                                                                                                                                                                    |                       |
      |                          | **3DES** is not recommended because it is not strong enough to protect data.                                                                                                                       |                       |
      |                          |                                                                                                                                                                                                    |                       |
      |                          | The default algorithm is **AES-128**.                                                                                                                                                              |                       |
      +--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | PFS                      | The perfect forward secrecy (PFS), which is used to configure the IPsec tunnel negotiation                                                                                                         | DH group 14           |
      |                          |                                                                                                                                                                                                    |                       |
      |                          | This function enables two parties to exchange the DH keys during the phase-two negotiation, improving key security. It is recommended that you enable this function.                               |                       |
      |                          |                                                                                                                                                                                                    |                       |
      |                          | You can disable this function by selecting **Disable** from the drop-down list.                                                                                                                    |                       |
      |                          |                                                                                                                                                                                                    |                       |
      |                          | PFSs configured at both of a VPN must be the same. Otherwise, the negotiation will fail. If you disable this function on the console, you also need to disable it at the customer side of the VPN. |                       |
      |                          |                                                                                                                                                                                                    |                       |
      |                          | The PFS algorithm can be **DH group 2**, **DH group 5**, **DH group 14**, **DH group 15**, **DH group 16**, **DH group 19**, **DH group 20**, or **DH group 21**.                                  |                       |
      |                          |                                                                                                                                                                                                    |                       |
      |                          | The PFS group security level from the highest to lowest is as follows: DH group 21 > DH group 20 > DH group 19 > DH group 16 > DH group 15 > DH group 14 > DH group 5 > DH group 2.                |                       |
      |                          |                                                                                                                                                                                                    |                       |
      |                          | The default algorithm is **DH group 14**.                                                                                                                                                          |                       |
      +--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Transfer Protocol        | The security protocol used for IPsec to transmit and encapsulate user data, which can be **AH**, **ESP**, or **AH-ESP**                                                                            | ESP                   |
      |                          |                                                                                                                                                                                                    |                       |
      |                          | The default protocol is **ESP**.                                                                                                                                                                   |                       |
      +--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Lifecycle (s)            | The lifetime of the SA, in seconds.                                                                                                                                                                | 3600                  |
      |                          |                                                                                                                                                                                                    |                       |
      |                          | The SA will be renegotiated if its lifetime expires.                                                                                                                                               |                       |
      |                          |                                                                                                                                                                                                    |                       |
      |                          | The default lifecycle is **3600** seconds.                                                                                                                                                         |                       |
      +--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

   .. note::

      The IKE policy specifies the encryption and authentication algorithms to use in the negotiation phase of an IPsec tunnel. The IPsec policy specifies the protocol, encryption algorithm, and authentication algorithm to use in the data transmission phase of an IPsec tunnel. Settings of these parameters must be the same at both ends of the VPN connection. If they are different, the VPN connection cannot be set up.

#. Click **Submit**.

   After the IPsec VPN is created, a public IP address is assigned to it. The IP address is the local gateway address of a created VPN on the network console. When configuring the remote tunnel in your data center, you must set the remote gateway address to this IP address.


   .. figure:: /_static/images/en-us_image_0152926732.png
      :alt: **Figure 3** Gateway egress IP address

      **Figure 3** Gateway egress IP address

#. Due to the symmetry of the tunnel, you also need to configure the IPsec VPN on your router or firewall in the data center.

   -  For the protocols supported by VPN connections, see section :ref:`Reference Standards and Protocols <vpn_01_0006>`.
   -  For a list of supported VPN devices, see :ref:`Which Remote VPN Devices Are Supported? <vpn_07_0011>`

.. |image1| image:: /_static/images/en-us_image_0123091916.png
