:original_name: vpn_05_0001.html

.. _vpn_05_0001:

Connecting to a VPC Through a VPN
=================================

Scenarios
---------

By default, ECSs in a VPC cannot communicate with your on-premises network. To enable communications between them, use a VPN. After a VPN is created, configure the security group and check the connectivity between the local and remote networks to ensure that the VPN is available. VPNs can be classified into the following two types:

-  Site-to-site VPN: The local side is a VPC on the cloud service platform, and the remote side is a user data center. A site-to-site VPN is a communications tunnel between a user data center and a single VPC.
-  Hub-and-spoke VPN: The local side is a VPC on the cloud service platform, and the remote side is user data centers. A hub-and-spoke VPN is a communications tunnel between user data centers and a VPC.

Ensure that the following requirements are met when configuring a VPN:

-  The local and remote subnets cannot overlap.
-  Different local subnets cannot overlap.
-  IKE policies, IPsec policies, and PSK at both ends of the VPN must be the same.
-  The local and remote subnet and gateway parameters must be matched pairs.
-  The security group used by ECSs in the VPC allows traffic from and to the remote side.
-  After a VPN is created, its status changes to **Normal** only after the VMs or physical servers on the two sides of the VPN communicate with each other.

Prerequisites
-------------

You have created the VPC and subnet required by the VPN.

Procedure
---------

#. On the management console, select the appropriate IKE and IPsec policies to create a VPN.

#. Check the IP address pools for the local and remote subnets.

   In :ref:`Figure 1 <vpn_05_0001__fig1141735616>`, the VPC has subnets 192.168.1.0/24 and 192.168.2.0/24. Your on-premises data center has subnets 192.168.3.0/24 and 192.168.4.0/24. You can create a VPN to enable subnets in your VPC to communicate with those in your data center.

   .. _vpn_05_0001__fig1141735616:

   .. figure:: /_static/images/en-us_image_0159201188.png
      :alt: **Figure 1** IPsec VPN

      **Figure 1** IPsec VPN

   The IP address pools for the local and remote subnets cannot overlap with each other. For example, if the local VPC has two subnets, 192.168.1.0/24 and 192.168.2.0/24, the IP address pool for the remote subnets cannot contain these two subnets.

#. Configure security group rules for the VPC.

#. Check the security group of the VPC.

   The security group must allow packets from the VPN to pass. You can run the **ping** command to check whether the security group of the VPC allows packets from the VPN to pass.

#. Check the remote LAN configuration (network configuration of the remote data center).

   A route must be configured for the remote LAN to enable VPN traffic to be forwarded to network devices on the LAN. If the VPN traffic cannot be forwarded to the network devices, check whether the remote LAN has policies configured to refuse the traffic.
