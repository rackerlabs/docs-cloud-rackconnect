=============================================================================
Delete One Public Ip Address -  rackconnect
=============================================================================

Delete One Public Ip Address
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <DELETE_delete_one_public_ip_address_v3_public_ips_public_ip_id_.rst#request>`__
`Response <DELETE_delete_one_public_ip_address_v3_public_ips_public_ip_id_.rst#response>`__

.. code-block:: javascript

    DELETE /v3/public_ips/{public_IP_id}

Delete one public IP address.

This operation deletes the public IP address identified by the specified ``public_IP_id``.



This table shows the possible response codes for this operation:

None

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








Response
^^^^^^^^^^^^^^^^^^




