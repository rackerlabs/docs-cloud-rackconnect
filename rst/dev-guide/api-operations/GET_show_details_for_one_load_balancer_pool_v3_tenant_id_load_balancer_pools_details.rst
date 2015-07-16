=============================================================================
Show Details For One Load Balancer Pool -  rackconnect
=============================================================================

Show Details For One Load Balancer Pool
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <GET_show_details_for_one_load_balancer_pool_v3_tenant_id_load_balancer_pools_details.rst#request>`__
`Response <GET_show_details_for_one_load_balancer_pool_v3_tenant_id_load_balancer_pools_details.rst#response>`__

.. code-block:: javascript

    GET /v3/{tenant_id}/load_balancer_pools/details

List details for one load balancer pool.

This operation provides detailed information about all the nodes in one load balancer pool identified by ``load_balancer_pool_id``.



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
|{tenant_id}               |xsd:string *(Required)*  |Specifies the unique     |
|                          |                         |identifier of the tenant |
|                          |                         |or account in a multi-   |
|                          |                         |tenancy cloud.           |
+--------------------------+-------------------------+-------------------------+








**Example Show Details For One Load Balancer Pool: JSON request**


.. code::

    curl --include \
     'https://dfw.rackconnect.api.rackspacecloud.com/v3/{tenant_id}/load_balancer_pools/{load_balancer_pool_id}/nodes/details'


Response
^^^^^^^^^^^^^^^^^^





**Example Show Details For One Load Balancer Pool: JSON request**


.. code::

    200 (OK)
    Content-Type: application/json
    
    [
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
            "id": "1860451d-fb89-45b8-b54e-151afceb50e5",
            "load_balancer_pool": {
                "id": "d6d3aa7c-dfa5-4e61-96ee-1d54ac1075d2",
                "name": "RCv3Test",
                "node_counts": {
                    "cloud_servers": 3,
                    "external": 4,
                    "total": 7
                },
                "port": 80,
                "status": "ACTIVE",
                "status_detail": null,
                "virtual_ip": "203.0.113.5"
            },
            "status": "ACTIVE",
            "status_detail": null,
            "updated": "2014-05-30T03:24:18Z"
        },
        {
            "created": "2014-05-31T08:23:12Z",
            "cloud_server": {
                "cloud_network": {
                    "cidr": "192.168.100.0/24",
                    "created": "2014-05-25T01:23:42Z",
                    "id": "07426958-1ebf-4c38-b032-d456820ca21a",
                    "name": "RC-CLOUD",
                    "private_ip_v4": "192.168.100.5",
                    "updated": "2014-05-25T02:28:44Z"
                },
                "created": "2014-05-30T02:19:42Z",
                "id": "f28b870f-a063-498a-8b12-7025e5b1caa6",
                "name": "RCv3TestServer2",
                "updated": "2014-05-30T02:20:18Z"
            },
            "id": "b70481dd-7edf-4dbb-a44b-41cc7679d4fb",
            "load_balancer_pool": {
                "id": "d6d3aa7c-dfa5-4e61-96ee-1d54ac1075d2",
                "name": "RCv3Test",
                "node_counts": {
                    "cloud_servers": 3,
                    "external": 4,
                    "total": 7
                },
                "port": 80,
                "status": "ACTIVE",
                "status_detail": null,
                "virtual_ip": "203.0.113.5"
            },
            "status": "ADDING",
            "status_detail": null,
            "updated": "2014-05-31T08:23:26Z"
        },
        {
            "created": "2014-05-31T08:23:18Z",
            "cloud_server": {
                "cloud_network": {
                    "cidr": "192.168.100.0/24",
                    "created": "2014-05-25T01:23:42Z",
                    "id": "07426958-1ebf-4c38-b032-d456820ca21a",
                    "name": "RC-CLOUD",
                    "private_ip_v4": "192.168.100.5",
                    "updated": "2014-05-25T02:28:44Z"
                },
                "created": "2014-05-30T02:21:42Z",
                "id": "a3d3a6b3-e4e4-496f-9a3d-5c987163e458",
                "name": "RCv3TestServer3",
                "updated": "2014-05-30T02:22:18Z"
            },
            "id": "ced9ddc8-6fae-4e72-9457-16ead52b5515",
            "load_balancer_pool": {
                "id": "d6d3aa7c-dfa5-4e61-96ee-1d54ac1075d2",
                "name": "RCv3Test",
                "node_counts": {
                    "cloud_servers": 3,
                    "external": 4,
                    "total": 7
                },
                "port": 80,
                "status": "ACTIVE",
                "status_detail": null,
                "virtual_ip": "203.0.113.5"
            },
            "status": "ADD_FAILED",
            "status_detail": "Unable to communicate with network device",
            "updated": "2014-05-31T08:24:36Z"
        }
    ]

