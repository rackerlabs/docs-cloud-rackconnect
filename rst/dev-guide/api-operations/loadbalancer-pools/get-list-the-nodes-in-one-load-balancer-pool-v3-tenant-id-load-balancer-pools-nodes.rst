
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

List the nodes in one load balancer pool
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v3/{tenant_id}/load_balancer_pools/nodes

List nodes for one load balancer pool.

This operation 				lists the nodes in 				one load balancer pool 				identified by ``load_balancer_pool_id``.



This table shows the possible response codes for this operation:


+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|200                       |OK                       |Success.                 |
+--------------------------+-------------------------+-------------------------+


Request
""""""""""""""""

This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{tenant_id}               |String *(Required)*      |Specifies the unique     |
|                          |                         |identifier of the tenant |
|                          |                         |or account in a multi-   |
|                          |                         |tenancy cloud.           |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




**Example List the nodes in one load balancer pool: JSON request**


.. code::

    curl --include \
     'https://dfw.rackconnect.api.rackspacecloud.com/v3/{tenant_id}/load_balancer_pools/{load_balancer_pool_id}/nodes'


Response
""""""""""""""""





**Example List the nodes in one load balancer pool: JSON response**


.. code::

    200 (OK)
    Content-Type: application/json
    
    [
        {
            "created": "2014-05-30T03:23:42Z",
            "cloud_server": {
                "id": "d95ae0c4-6ab8-4873-b82f-f8433840cff2"
            }, 
            "id": "1860451d-fb89-45b8-b54e-151afceb50e5",
            "load_balancer_pool": {
                "id": "d6d3aa7c-dfa5-4e61-96ee-1d54ac1075d2"
            },
            "status": "ACTIVE",
            "status_detail": null,
            "updated": "2014-05-30T03:24:18Z"
        },
        {
            "created": "2014-05-31T08:23:12Z",
            "cloud_server": {
                "id": "f28b870f-a063-498a-8b12-7025e5b1caa6"
            },
            "id": "b70481dd-7edf-4dbb-a44b-41cc7679d4fb",
            "load_balancer_pool": {
                "id": "d6d3aa7c-dfa5-4e61-96ee-1d54ac1075d2"
            },
            "status": "ADDING",
            "status_detail": null,
            "updated": "2014-05-31T08:23:26Z"
        },
        {
            "created": "2014-05-31T08:23:18Z",
            "cloud_server": {
                "id": "a3d3a6b3-e4e4-496f-9a3d-5c987163e458"
            },
            "id": "ced9ddc8-6fae-4e72-9457-16ead52b5515",
            "load_balancer_pool": {
                "id": "d6d3aa7c-dfa5-4e61-96ee-1d54ac1075d2"
            },
            "status": "ADD_FAILED",
            "status_detail": "Unable to communicate with network device",
            "updated": "2014-05-31T08:24:36Z"
        }
    ]


