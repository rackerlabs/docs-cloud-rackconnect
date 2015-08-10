
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

List one cloud network
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    GET /v3/{tenant_id}/cloud_networks/{network_id}

List details for one cloud network.

This operation 				lists details for 				the cloud network 				identified by the specified ``network_id``.



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
|{network_id}              |String *(Required)*      |Specifies the unique     |
|                          |                         |identifier of a network. |
+--------------------------+-------------------------+-------------------------+





This operation does not accept a request body.




**Example List one cloud network: JSON request**


.. code::

    curl --include \
     'http://dfw.rackconnect.api.rackspacecloud.comv3/{tenant_id}/cloud_networks/{id}'


Response
""""""""""""""""





**Example List one cloud network: JSON response**


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
        }
    ]


