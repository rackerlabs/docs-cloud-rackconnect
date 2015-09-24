.. _delete-one-public-ip-address-v3-public-ips:

Delete one public IP address
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code::

    DELETE /v3/public_ips/{public_IP_id}

This operation deletes the public IP address identified by the specified ``public_IP_id``.

Request
"""""""

This table shows the URI parameters for the request:

+--------------------------+-------------------------+-------------------------+
|Name                      |Type                     |Description              |
+==========================+=========================+=========================+
|{public_IP_id}            |String *(Required)*      |Specifies the unique     |
|                          |                         |identifier of a public   |
|                          |                         |IP address.              |
+--------------------------+-------------------------+-------------------------+

This operation does not accept a request body.
