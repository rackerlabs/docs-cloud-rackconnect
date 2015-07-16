=============================================================================
List One Load Balancer Pool -  rackconnect
=============================================================================

List One Load Balancer Pool
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <GET_list_one_load_balancer_pool_v3_tenant_id_load_balancer_pools_load_balancer_pool_id_.rst#request>`__
`Response <GET_list_one_load_balancer_pool_v3_tenant_id_load_balancer_pools_load_balancer_pool_id_.rst#response>`__

.. code-block:: javascript

    GET /v3/{tenant_id}/load_balancer_pools/{load_balancer_pool_id}

List summary for one load balancer pool.

This operation provides basic information about the load balancer pool identified by the specified ``load_balancer_pool_id``.



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
|{load_balancer_pool_id}   |xsd:string *(Required)*  |Specifies the unique     |
|                          |                         |identifier of a load     |
|                          |                         |balancer pool.           |
+--------------------------+-------------------------+-------------------------+








**Example List One Load Balancer Pool: JSON request**


.. code::

    curl --include \
     'https://dfw.rackconnect.api.rackspacecloud.com/v3/{tenant_id}/load_balancer_pools/{id}'


Response
^^^^^^^^^^^^^^^^^^





**Example List One Load Balancer Pool: JSON request**


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
      }
    ]

