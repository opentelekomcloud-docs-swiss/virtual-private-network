:original_name: en_topic_0093011478.html

.. _en_topic_0093011478:

Example
=======

This section describes how to call the API to create an IPsec connection.

.. note::

   The token obtained from IAM is valid for only 24 hours. If you want to use one token for authentication, you can cache it to avoid frequently obtaining the token.

Involved APIs
-------------

To use token authentication, you need to obtain a token and add **X-Auth-Token** to the request header of API calls.

-  API for obtaining tokens from IAM
-  VPN API for creating an IPsec connection

Procedure
---------

#. Obtain the token by performing the steps provided in section :ref:`Authentication <en_topic_0093011474>`.

#. Send **POST https://**\ *VPN endpoint*\ **/v1/{tenant_id}/cloudservers**.

#. Add **X-Auth-Token** to the request header.

#. Specify the following parameters in the request body:

   .. code-block::

      {
        "ipsec_site_connection" : {
          "psk" : "secret",
          "initiator" : "bi-directional",
          "ipsecpolicy_id" : "e6e23d0c-9519-4d52-8ea4-5b1f96d857b1",
          "admin_state_up" : true,
          "mtu" : 1500,
          "peer_ep_group_id" : "9ad5a7e0-6dac-41b4-b20d-a7b8645fddf1",
          "ikepolicy_id" : "9b00d6b0-6c93-4ca5-9747-b8ade7bb514f",
          "vpnservice_id" : "5c561d9d-eaea-45f6-ae3e-08d1a7080828",
          "local_ep_group_id" : "3e1815dd-e212-43d0-8f13-b494fa553e68",
          "peer_address" : "172.24.4.233",
          "peer_id" : "172.24.4.233",
          "name" : "vpnconnection1"
        }
      }

   After the request is successfully processed, information about the created resource is returned.

   .. code-block::

      {
        "ipsec_site_connection" : {
          "status" : "PENDING_CREATE",
          "psk" : "secret",
          "initiator" : "bi-directional",
          "name" : "vpnconnection1",
          "admin_state_up" : true,
          "project_id" : "10039663455a446d8ba2cbb058b0f578",
          "tenant_id" : "10039663455a446d8ba2cbb058b0f578",
          "auth_mode" : "psk",
          "peer_cidrs" : [ ],
          "mtu" : 1500,
          "peer_ep_group_id" : "9ad5a7e0-6dac-41b4-b20d-a7b8645fddf1",
          "ikepolicy_id" : "9b00d6b0-6c93-4ca5-9747-b8ade7bb514f",
          "vpnservice_id" : "5c561d9d-eaea-45f6-ae3e-08d1a7080828",
          "dpd" : {
            "action" : "hold",
            "interval" : 30,
            "timeout" : 120
          },
          "route_mode" : "static",
          "ipsecpolicy_id" : "e6e23d0c-9519-4d52-8ea4-5b1f96d857b1",
          "local_ep_group_id" : "3e1815dd-e212-43d0-8f13-b494fa553e68",
          "peer_address" : "172.24.4.233",
          "peer_id" : "172.24.4.233",
          "id" : "851f280f-5639-4ea3-81aa-e298525ab74b",
          "description" : ""
        }
      }

   If the request fails, an error code and error information are returned. For details, see section :ref:`Error Codes <en_topic_0093011523>`.
