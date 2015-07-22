
.. THIS OUTPUT IS GENERATED FROM THE WADL. DO NOT EDIT.

=============================================================================
Delete One Public Ip Address -  rackconnect
=============================================================================

Delete One Public Ip Address
~~~~~~~~~~~~~~~~~~~~~~~~~

`Request <delete-delete-one-public-ip-address-v3-public-ips-public-ip-id.html#request>`__
`Response <delete-delete-one-public-ip-address-v3-public-ips-public-ip-id.html#response>`__

.. code::

    DELETE /v3/public_ips/{public_IP_id}

				Delete one public IP address.

This operation 				deletes 				the public IP 				address identified by the specified ``public_IP_id``.



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




