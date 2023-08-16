:original_name: en_topic_0093011501.html

.. _en_topic_0093011501:

Updating a VPN Service
======================

Function
--------

This API is used to update a VPN service.

URI
---

PUT /v2.0/vpn/vpnservices/{service_id}

.. table:: **Table 1** Parameter description

   ========== ====== ========= =============================
   Parameter  Type   Mandatory Description
   ========== ====== ========= =============================
   service_id String Yes       Specifies the VPN service ID.
   ========== ====== ========= =============================

Request
-------

:ref:`Table 2 <en_topic_0093011501__table24429894>` describes the request parameters.

.. _en_topic_0093011501__table24429894:

.. table:: **Table 2** Request parameters

   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------+
   | Parameter             | Type            | Mandatory       | Description                                                                           |
   +=======================+=================+=================+=======================================================================================+
   | description           | String          | No              | Provides supplementary information about the VPN service.                             |
   |                       |                 |                 |                                                                                       |
   |                       |                 |                 | The description can contain up to 255 characters.                                     |
   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------+
   | name                  | String          | No              | Specifies the VPN service name.                                                       |
   |                       |                 |                 |                                                                                       |
   |                       |                 |                 | The name can contain 1 to 64 characters.                                              |
   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------+
   | admin_state_up        | Boolean         | No              | Specifies the administrative status, which can be **true** or **false**.              |
   |                       |                 |                 |                                                                                       |
   |                       |                 |                 | Currently, **admin_state_up** can only be **true**.                                   |
   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------+
   | order_id              | String          | No              | Specifies the ID of a yearly/monthly order.                                           |
   |                       |                 |                 |                                                                                       |
   |                       |                 |                 | The ID can contain up to 255 characters.                                              |
   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------+
   | product_id            | String          | No              | Specifies the ID of a product that is billed on a yearly/monthly basis.               |
   |                       |                 |                 |                                                                                       |
   |                       |                 |                 | The ID can contain up to 255 characters.                                              |
   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------+
   | prepay_connection_num | Integer         | No              | Specifies the number of connections of the yearly/monthly VPN service.                |
   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------+
   | resource_speccode     | String          | No              | Specifies the specifications of the product that is billed on a yearly/monthly basis. |
   |                       |                 |                 |                                                                                       |
   |                       |                 |                 | The specifications can contain up to 255 characters.                                  |
   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------+
   | vpnservice            | Object          | Yes             | Specifies the VPN service object.                                                     |
   +-----------------------+-----------------+-----------------+---------------------------------------------------------------------------------------+

.. note::

   Parameter **project_id** is not supported.

Response
--------

:ref:`Table 3 <en_topic_0093011501__table9147936>` describes the response parameters.

.. _en_topic_0093011501__table9147936:

.. table:: **Table 3** Response parameters

   +-----------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type    | Description                                                                                                                           |
   +=======================+=========+=======================================================================================================================================+
   | id                    | String  | Specifies the VPN service ID.                                                                                                         |
   +-----------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
   | router_id             | String  | Specifies the router ID.                                                                                                              |
   +-----------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
   | status                | String  | Specifies the VPN service status, which can be **ACTIVE**, **DOWN**, **BUILD**, **ERROR**, **PENDING_UPDATE**, or **PENDING_DELETE**. |
   +-----------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
   | name                  | String  | Specifies the VPN service name.                                                                                                       |
   +-----------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
   | external_v6_ip        | String  | Specifies the IPv6 address of the VPN service external gateway.                                                                       |
   +-----------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up        | Boolean | Specifies the administrative status, which can be **true** or **false**.                                                              |
   +-----------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
   | subnet_id             | String  | Specifies the subnet ID.                                                                                                              |
   +-----------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id             | String  | Specifies the project ID.                                                                                                             |
   +-----------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
   | external_v4_ip        | String  | Specifies the IPv4 address of the VPN service external gateway.                                                                       |
   +-----------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
   | description           | String  | Provides supplementary information about the VPN service.                                                                             |
   +-----------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
   | order_id              | String  | Specifies the ID of a yearly/monthly order.                                                                                           |
   +-----------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
   | product_id            | String  | Specifies the ID of a product that is billed on a yearly/monthly basis.                                                               |
   +-----------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
   | prepay_connection_num | Integer | Specifies the number of connections of the yearly/monthly VPN service.                                                                |
   +-----------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
   | resource_speccode     | String  | Specifies the specifications of the product that is billed on a yearly/monthly basis.                                                 |
   +-----------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
   | created_at            | String  | Specifies the time when the VPN service was created.                                                                                  |
   +-----------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+
   | vpnservice            | Object  | Specifies the VPN service object.                                                                                                     |
   +-----------------------+---------+---------------------------------------------------------------------------------------------------------------------------------------+

Example
-------

-  Example request

   .. code-block:: text

      PUT /v2.0/vpn/vpnservices/{service_id}
      {
        "vpnservice" : {
          "description" : "Updated description"
        }
      }

-  Example response

   .. code-block::

      {
          "vpnservice": {
              "router_id": "881b7b30-4efb-407e-a162-5630a7af3595",
              "status": "ACTIVE",
              "name": "myvpn",
              "admin_state_up": true,
              "subnet_id": null,
              "tenant_id": "26de9cd6cae94c8cb9f79d660d628e1f",
              "id": "41bfef97-af4e-4f6b-a5d3-4678859d2485",
              "description": "Updated description",
              "order_id": "",
              "product_id": "",
              "prepay_connection_num": 0,
              "resource_speccode": "",
              "created_at": "2020-08-05 12:36:35.921257"
          }
      }

Returned Values
---------------

For details, see :ref:`Common Returned Values <en_topic_0093011522>`.
