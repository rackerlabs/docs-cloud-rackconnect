.. _gs-list-public-ip-address:

Listing public IP addresses for a cloud server
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

After you have obtained your authentication token, you can use the
RackConnect API to list all public IP addresses that apply to a specific
cloud server.

The following example shows how to issue a **GET** request that lists
all the public IP addresses that pertain to a specific server that has
been set up for a specific tenant.

**cURL list all public IP addresses request**

.. code::

    curl --include \ 
    --request GET \
    --header "X-Auth-Token: $AUTH_TOKEN" \
    --header "Content-Type: application/json" \
    $API_ENDPOINT/v3/$TENANT_ID/public_ips?cloud_server_id=serverUuid


.. note:: You can obtain the UUID (universally unique identifier) of your cloud
   server from within its server details page in the `Cloud Control
   Panel <https://mycloud.rackspace.com>`__ or with the `Cloud Servers
   API—Get Server Details <https://developer.rackspace.com/docs/cloud-servers/v2/developer-guide/#get-list-servers-with-details-servers-detail>`__
   operation. The UUID is a 32-character entry with four hyphens in the
   **ID** or **id** section of the server details page.

The following example shows a successful response for a cloud server
that has a public IP address assigned.

**List all public IP addresses response**

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

**cURL list a single public IP address request**

.. code::  

    curl --include \ 
    --request GET \
    --header "X-Auth-Token: $AUTH_TOKEN" \
    --header "Content-Type: application/json" \
    $API_ENDPOINT/v3/$TENANT_ID/public_ips/serverUuid

The following example shows a successful response to a **GET** request
to retrieve a single public ID address for a specific tenant.

**List a single public IP address response**

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

