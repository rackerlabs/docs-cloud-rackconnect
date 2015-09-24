.. _get-list-all-cloud-networks-v3-networks:

List all cloud networks
^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v3/{tenant_id}/cloud_networks

This operation lists details for all the cloud networks available to the specified ``tenant_id``.

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

**Example List all cloud networks: JSON request**

.. code::

   curl --include \
    'dfw.rackconnect.api.rackspacecloud.com/v3/{tenant_id}/cloud_networks'

Response
""""""""

**Example List all cloud networks: JSON response**

.. code::

   200 (OK)
   Content-Type: application/json

   [
       {
           "cidr": "192.168.100.0/24",
           "created": "2014-05-25T01:23:42Z",
           "id": "07426958-1ebf-4c38-b032-d456820ca21a",
           "name": "RC-CLOUD",
           "updated": "2014-05-25T02:28:44Z"
       },
       {
           "cidr": "192.168.200.0/24",
           "created": "2014-05-25T02:30:55Z",
           "id": "07426958-1ebf-5d49-c043-e566820db27b",
           "name": "RC-CLOUD2",
           "updated": "2014-05-25T02:39:22Z"
       }
   ]
