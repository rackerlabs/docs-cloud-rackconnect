.. _gs-remove-public-ip-address:

Removing a public IP address
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can use the RackConnect API to remove a public IP address from a
cloud server.

To remove a public IP address, issue a **DELETE** request against the
RackConnect endpoint by providing the cloud server's public IP v4 UUID.
This value is listed as the id entry just above the public\_ip\_v4 entry
in the responses of operations to list and add public IP addresses.

**cURL remove a public IP address request**

.. code::

    curl --include \
    --request DELETE \
    --header "X-Auth-Token: $AUTH_TOKEN" \
    --header "Content-Type: application/json" \
    $API_ENDPOINT/v3/$TENANT_ID/public_ips/serverPublicIPv4Uuid

This call does not return any JSON data—only an HTTP response code as
shown in the following example. A **204** response code signifies that
the public IP address was successfully removed from the cloud server.

**Remove a public IP address response**

.. code::

    HTTP/1.1 204 No
        Content
    Server: Apache-Coyote/1.1
    cache-control: no-cache
    via: 1.1 Repose (Repose/3.0.1)
    expires: -1
    date: Thu, 13 Sep 2014 14:48:58 GMT
    pragma: no-cache
