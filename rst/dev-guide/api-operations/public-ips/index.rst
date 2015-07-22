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

.. toctree::
    :maxdepth: 2

    List all public IP addresses <get-list-all-public-ip-addresses-v3-public-ips.rst>
    Add one public IP <post-add-one-public-ip-v3-public-ips.rst>
    List public IPs for a server <get-list-public-ips-for-a-server-v3-public-ips-cloud-server-id.rst>
    List one public IP addresses <get-list-one-public-ip-addresses-v3-public-ips-public-ip-id.rst>
    Delete one public IP address <delete-delete-one-public-ip-address-v3-public-ips-public-ip-id.rst>
