=============================================================================
List One Public Ip Adresses -  rackconnect
=============================================================================

List One Public Ip Adresses
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <GET_list_one_public_ip_adresses_v3_public_ips_public_ip_id_.rst#request>`__
`Response <GET_list_one_public_ip_adresses_v3_public_ips_public_ip_id_.rst#response>`__

.. code-block:: javascript

    GET /v3/public_ips/{public_IP_id}

List details for one public IP address.

This operation lists details for one public IP address identified by the specified ``public_IP_id``.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success.                 |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad request              |The input was not in the |
|                          |                         |correct format.          |
+--------------------------+-------------------------+-------------------------+
|404                       |Not found                |The requested item was   |
|                          |                         |not found.               |
+--------------------------+-------------------------+-------------------------+
|500                       |Internal server error    |An unexpected error has  |
|                          |                         |occurred.                |
+--------------------------+-------------------------+-------------------------+


Request
^^^^^^^^^^^^^^^^^

This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{public_IP_id}            |xsd:string *(Required)*  |Specifies the unique     |
|                          |                         |identifier of a public   |
|                          |                         |IP address.              |
+--------------------------+-------------------------+-------------------------+








**Example List One Public Ip Adresses: JSON request**


.. code::

    curl --include \
     'https://dfw.rackconnect.api.rackspacecloud.com/v3/{tenant_id}/public_ips/{id}'


Response
^^^^^^^^^^^^^^^^^^





**Example List One Public Ip Adresses: JSON request**


.. code::

    200 (OK)
    Content-Type: application/json
    
    {
        "created": "2014-05-30T03:23:42Z",
        "cloud_server": {
            "cloud_network": {
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

