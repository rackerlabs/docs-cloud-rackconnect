
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

=============================================================================
List All Load Balancer Pools -  rackconnect
=============================================================================

List All Load Balancer Pools
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <get-list-all-load-balancer-pools-v3-tenant-id-load-balancer-pools.html#request>`__
`Response <get-list-all-load-balancer-pools-v3-tenant-id-load-balancer-pools.html#response>`__

.. code::

    GET /v3/{tenant_id}/load_balancer_pools

				List details for all load balancer pools.

This operation 				lists details for 				all load balancer pools 				available to the specified ``tenant_id``.



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








**Example List All Load Balancer Pools: JSON request**


.. code::

    curl --include \
     'http://dfw.rackconnect.api.rackspacecloud.com/v3/{tenant_id}/load_balancer_pools'


Response
^^^^^^^^^^^^^^^^^^





**Example List All Load Balancer Pools: JSON response**


.. code::

    200 (OK)
    Content-Type: application/json
    [
        {
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
        {
            "id": "33021100-4abf-4836-9080-465a6d87ab68",
            "name": "RCv3Test2",
            "node_counts": {
                "cloud_servers": 1,
                "external": 0,
                "total": 1
            },
            "port": 80,
            "status": "ACTIVE",
            "status_detail": null,
            "virtual_ip": "203.0.113.7"
        },
        {
            "id": "b644350a-301b-47b5-a411-c6e0f933c347",
            "name": "RCv3Test3",
            "node_counts": {
                "cloud_servers": 2,
                "external": 3,
                "total": 5
            },
            "port": 443,
            "status": "ACTIVE,
            "status_detail": null",
            "virtual_ip": "203.0.113.15"
        }
    ]

