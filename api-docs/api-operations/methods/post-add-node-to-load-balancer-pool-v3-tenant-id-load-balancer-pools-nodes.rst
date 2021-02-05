.. _post-add-node-to-load-balancer-pool-v3-load-balancer-pools:

Add node to load balancer pool
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    POST /v3/{tenant_id}/load_balancer_pools/nodes

This operation adds a node to one load balancer pool identified by ``load_balancer_pool_id``.

This table shows the possible response codes for this operation:

+--------------------------+-------------------------+-------------------------+
|Response Code             |Name                     |Description              |
+==========================+=========================+=========================+
|201                       |OK                       |Created                  |
+--------------------------+-------------------------+-------------------------+
|400                       |Bad request              |The input was not in the |
|                          |                         |correct format.          |
+--------------------------+-------------------------+-------------------------+
|409                       |Add node to load         |Conflict Cloud Server    |
|                          |balancer pool            |{cloud_server_id} does   |
|                          |                         |not exist or Cloud       |
|                          |                         |Server {cloud_server_id} |
|                          |                         |is already a member of   |
|                          |                         |Load Balancer Pool       |
|                          |                         |{load_balancer_pool_id}  |
|                          |                         |or Load Balancer Pool    |
|                          |                         |{load_balancer_pool_id}  |
|                          |                         |is not in an ACTIVE state|
+--------------------------+-------------------------+-------------------------+
|500                       |Internal server error    |An unexpected error has  |
|                          |                         |occurred.                |
+--------------------------+-------------------------+-------------------------+


Request
"""""""

This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{tenant_id}               |String *(Required)*      |Specifies the unique     |
|                          |                         |identifier of the tenant |
|                          |                         |or account in a multi-   |
|                          |                         |tenancy cloud.           |
+--------------------------+-------------------------+-------------------------+

**Example Add node to load balancer pool: JSON request**

.. code::

   {
       "cloud_server": {
           "id": "d95ae0c4-6ab8-4873-b82f-f8433840cff2"
       }
   }


Response
""""""""

**Example Add node to load balancer pool: JSON response**

.. code::

   201 (Created)
   Content-Type: application/json

   {
       "created": "2014-05-30T03:23:42Z",
       "cloud_server": {
           "id": "d95ae0c4-6ab8-4873-b82f-f8433840cff2"
       },
       "id": "1860451d-fb89-45b8-b54e-151afceb50e5",
       "load_balancer_pool": {
           "id": "d6d3aa7c-dfa5-4e61-96ee-1d54ac1075d2"
       },
       "status": "ADDING",
       "status_detail": null,
       "updated": null
   }
