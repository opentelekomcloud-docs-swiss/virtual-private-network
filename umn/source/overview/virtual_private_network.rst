:original_name: en-us_topic_0035391393.html

.. _en-us_topic_0035391393:

Virtual Private Network
=======================

Overview
--------

A Virtual Private Network (VPN) establishes an encrypted, Internet-based communications tunnel between your on-premises data center and a Virtual Private Cloud (VPC). With VPN, you can connect to a VPC and access the resources deployed there from your data center.

By default, ECSs in a VPC cannot communicate with your data center or private network. To enable communications between them, use a VPN.

A VPN consists of a VPN gateway and one or more VPN connections. A VPN gateway provides an Internet egress for a VPC and works together with the remote gateway in an on-premises data center. A VPN connection uses the Internet-based encryption technology to connect a VPN gateway and a remote gateway to establish cross-premises connectivity between your data center and your VPC. The VPN connection allows you to quickly build secure hybrid cloud environment.

:ref:`Figure 1 <en-us_topic_0035391393__fig681916843511>` shows the VPN networking.

.. _en-us_topic_0035391393__fig681916843511:

.. figure:: /_static/images/en-us_image_0294835465.png
   :alt: **Figure 1** VPN networking

   **Figure 1** VPN networking
