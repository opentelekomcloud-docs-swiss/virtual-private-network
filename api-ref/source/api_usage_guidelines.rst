:original_name: en_topic_0093011471.html

.. _en_topic_0093011471:

API Usage Guidelines
====================

Cloud platform APIs comply with the RESTful API design principles. REST-based web services are organized into resources. Each resource is identified by one or more Uniform Resource Identifiers (URIs). An application accesses a resource based on the resource's Unified Resource Locator (URL). A URL is usually in the following format: https://*Endpoint/uri*. In the URL, *uri* indicates the resource path, that is, the API access path.

Cloud platform APIs use HTTPS as the transmission protocol. Requests/Responses are transmitted by using JSON messages, with media type represented by **Application/json**.
