:original_name: en-us_topic_0160974607.html

.. _en-us_topic_0160974607:

IPsec VPN
=========

The Internet Protocol Security (IPsec) VPN is an encrypted tunneling technology that can establish confidential and secure communications tunnels between different networks.

In :ref:`Figure 1 <en-us_topic_0160974607__fig489417475262>`, the VPC has subnets 192.168.1.0/24 and 192.168.2.0/24. Your on-premises data center has subnets 192.168.3.0/24 and 192.168.4.0/24. You can create a VPN to enable subnets in your VPC to communicate with those in your data center.

.. _en-us_topic_0160974607__fig489417475262:

.. figure:: /_static/images/en-us_image_0291702085.png
   :alt: **Figure 1** IPsec VPN

   **Figure 1** IPsec VPN

Both site-to-site and hub-and-spoke VPNs are supported. You need to set up VPNs in both your on-premises data center and the VPC to establish the VPN connection.

Ensure that the Internet Key Exchange (IKE) and IPsec policies at both ends of the VPN are the same. Your device should comply with IPsec standards and protocols.
