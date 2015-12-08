

=====================================
Working with the RackConnect v3.0 API
=====================================

.. note:: As you complete these tasks, keep in mind that these public IP
   addresses are being allocated out of your dedicated environment's assigned
   public IP blocks. Also, after your RackConnect v3.0 cloud servers are built
   and active, you can use the RackConnect v3.0 API to add and remove public IP
   addresses from them at any time.

Listing public IP addresses for a cloud server
----------------------------------------------

After you have obtained your authentication token, you can use the
RackConnect API to list all public IP addresses that apply to a specific
cloud server.

The following example shows how to issue a **GET** request that lists
all the public IP addresses that pertain to a specific server that has
been set up for a specific tenant.

**Example: List all public IP addresses - Request**

.. code::

    curl --include \ 
    --request GET \
    --header "X-Auth-Token: authTokenId" \
    --header "Content-Type: application/json" \
    https://region.rackconnect.api.rackspacecloud.com/v3/tenantId/public_ips?cloud_server_id=serverUuid


.. note:: You can obtain the UUID (universally unique identifier) of your cloud
   server from within its server details page in the `Cloud Control
   Panel <https://mycloud.rackspace.com>`__ or with the `Cloud Servers
   API—Get Server Details <https://developer.rackspace.com/docs/cloud-servers/v2/developer-guide/#get-list-servers-with-details-servers-detail>`__
   operation. The UUID is a 32-character entry with four hyphens in the
   **ID** or **id** section of the server details page.

The following example shows a successful response for a cloud server
that has a public IP address assigned.

**Example: List all public IP addresses - Response**

.. code::

    [ 
      {
       "created": "2014-05-30T03:23:42Z",
       "cloud_server":
         {
           "cloud_network":
              { 
                 "cidr": "192.168.100.0/24",
                 "created": "2014-05-25T01:23:42Z",
                 "id": "07426958-1ebf-4c38-b032-d456820ca21a",
                 "name": "RC-CLOUD",
                 "private_ip_v4": "192.168.100.5",
                 "updated": "2014-05-25T02:28:44Z"
              },
           "created": "2014-05-30T02:18:42Z",
           "id": "d95ae0c4-6ab8-4873-b82f-f8433840cff2",
           "name": "RCv3TestServer1",
           "updated": "2014-05-30T02:19:18Z"
         },
        "id": "2d0f586b-37a7-4ae0-adac-2743d5feb450",
        "public_ip_v4": "203.0.113.110",
        "status": "ACTIVE",
        "status_detail": null,
        "updated": "2014-05-30T03:24:18Z" 
      }
    ]


The following command shows how to list a single public IP address for a
specific Cloud Server that has been created for a specific tenant.

**Example: List a single public IP address - request**

.. code::  

    curl --include \ 
    --request GET \
    --header "X-Auth-Token: authTokenId" \
    --header "Content-Type: application/json" \
    https://region.rackconnect.api.rackspacecloud.com/v3/tenantId/public_ips/serverUuid

The following example shows a successful response to a **GET** request
to retrieve a single public ID address for a specific tenant.

**Example: List a single public IP address - response**

.. code::

     {
       "created": "2014-05-30T03:23:42Z",
       "cloud_server":
         { 
          "cloud_network":
            {
             "cidr": "192.168.100.0/24",
             "created": "2014-05-25T01:23:42Z",
             "id": "07426958-1ebf-4c38-b032-d456820ca21a",
             "name": "RC-CLOUD",
             "private_ip_v4": "192.168.100.5",
             "updated": "2014-05-25T02:28:44Z"
             },
              "created": "2014-05-30T02:18:42Z",
              "id": "d95ae0c4-6ab8-4873-b82f-f8433840cff2",
              "name": "RCv3TestServer1",
              "updated": "2014-05-30T02:19:18Z"
           },
            "id": "2d0f586b-37a7-4ae0-adac-2743d5feb450",
            "public_ip_v4": "203.0.113.110",
            "status": "ACTIVE",
            "status_detail": null,
            "updated": "2014-05-30T03:24:18Z"
     }

Adding a public IP address
--------------------------

You can use the RackConnect API to add a public IP address to a
Rackspace cloud server. The following example shows how to use a
**POST** request to add a new public IP address to a specific cloud
server for a specific tenant.

**Example: Add a public IP address - Request**

.. code::  

    curl \
    --request POST \
    --header "X-Auth-Token: authTokenId" \
    --header "Content-Type: application/json" \
    --data '{ "cloud_server": { "id": "serverUuid" } }' \
    https://region.rackconnect.api.rackspacecloud.com/v3/tenantId/public_ips \
    | python -m json.tool

Following is an example of a successful response to a **POST** request
to add a public IP address to a cloud server API request.

**Example: Add a single public IP address - Response**

.. code::

    { 
      "created": "2014-05-30T03:23:42Z",
      "cloud_server":
       {
        "cloud_network": 
         {
          "cidr": "192.168.100.0/24",
          "created": "2014-05-25T01:23:42Z",
          "id": "07426958-1ebf-4c38-b032-d456820ca21a",
          "name": "RC-CLOUD",
          "private_ip_v4": "192.168.100.5",
          "updated": "2014-05-25T02:28:44Z"
         },
       "created": "2014-05-30T02:18:42Z",
       "id": "d95ae0c4-6ab8-4873-b82f-f8433840cff2",
       "name": "RCv3TestServer1",
       "updated": "2014-05-30T02:19:18Z"
       },
        "id": "2d0f586b-37a7-4ae0-adac-2743d5feb450",
        "public_ip_v4": null,
        "status": "ADDING",
        "status_detail": null,
        "updated": null 
    }

.. note:: Be sure to record the id value of new IP addresses that you add. You
   need the ID to perform operations such as deleting an IP address. In the
   preceding example, the ID is 2d0f586b-37a7-4ae0- adac-2743d5feb450.


Removing a public IP address
----------------------------

You can use the RackConnect API to remove a public IP address from a
cloud server.

To remove a public IP address, issue a **DELETE** request against the
RackConnect endpoint by providing the cloud server's public IP v4 UUID.
This value is listed as the id entry just above the public\_ip\_v4 entry
in the responses of operations to list and add public IP addresses.

**Example: Remove a public IP address - Request**

.. code::

    curl --include \
    --request DELETE \
    --header "X-Auth-Token: authTokenId" \
    --header "Content-Type: application/json" \
    https://region.rackconnect.api.rackspacecloud.com/v3/tenantId/public_ips/serverPublicIPv4Uuid

This call does not return any JSON data—only an HTTP response code as
shown in the following example. A **204** response code signifies that
the public IP address was successfully removed from the cloud server.

**Example: Remove a public IP address - Response**

.. code::

    HTTP/1.1 204 No
        Content
    Server: Apache-Coyote/1.1
    cache-control: no-cache
    via: 1.1 Repose (Repose/3.0.1)
    expires: -1
    date: Thu, 13 Sep 2014 14:48:58 GMT
    pragma: no-cache
