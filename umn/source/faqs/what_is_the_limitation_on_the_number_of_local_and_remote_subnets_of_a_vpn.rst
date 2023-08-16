:original_name: vpn_07_0007.html

.. _vpn_07_0007:

What Is the Limitation on the Number of Local and Remote Subnets of a VPN?
==========================================================================

-  You can use VPN to connect up to 5 local subnets. The product of the number of local subnets and that of remote subnets cannot exceed 2500.
-  A VPC delivers VPC subnet routes based on the remote subnets of a VPN connection, remote subnets of a Direct Connect connection, and subnets of a VPC peering connection. Each subnet has one subnet route.
-  The number of VPC subnet routes cannot exceed 200. That is, the total number of remote subnets of a VPN connection, remote subnets of a Direct Connect connection, subnets of a VPC peering connection, and custom routes in a VPC cannot exceed 200.
