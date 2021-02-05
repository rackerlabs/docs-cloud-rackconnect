==========
Public IPs
==========

The RackConnect v3.0 API enables you to add and remove public IP addresses from
your RackConnect v3.0 cloud servers. These public IP addresses are being allocated
out of your dedicated environment's assigned public IP blocks.

Public IP address status values are as follows:

- `ADDING`

- `ACTIVE`

- `REMOVING`

- `ADD_FAILED`

- `REMOVE_FAILED`

These values will appear in the response body of an API request.

.. include:: methods/get-list-all-public-ip-addresses-v3-public-ips.rst
.. include:: methods/post-add-one-public-ip-v3-public-ips.rst
.. include:: methods/get-list-public-ips-for-a-server-v3-public-ips-cloud-server-id.rst
.. include:: methods/get-list-one-public-ip-addresses-v3-public-ips-public-ip-id.rst
.. include:: methods/delete-delete-one-public-ip-address-v3-public-ips-public-ip-id.rst
