.. _gs-add-public-ip-address:

Adding a public IP address
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can use the RackConnect API to add a public IP address to a
Rackspace cloud server. The following example shows how to use a
**POST** request to add a new public IP address to a specific cloud
server for a specific tenant.

**cURL add a public IP address request**

.. code::  

    curl \
    --request POST \
    --header "X-Auth-Token: $AUTH_TOKEN" \
    --header "Content-Type: application/json" \
    --data '{ "cloud_server": { "id": "serverUuid" } }' \
    $API_ENDPOINT/v3/$TENANT_ID/public_ips \
    | python -m json.tool

Following is an example of a successful response to a **POST** request
to add a public IP address to a cloud server API request.

**Add a single public IP address response**

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


