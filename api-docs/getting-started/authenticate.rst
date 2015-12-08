.. _authentication:

Authenticate to the Rackspace Cloud
-------------------------------------

Whether you use cURL or a REST client to interact with the RackConnect API, you
need an authentication token that you include in the X-Auth-Token header in
each API request. You also need your account number  also known as your tenant
ID.

With a valid token, you can submit API requests to any of the API service
endpoints included in the service catalog. A token is valid for only 24 hours,
which means that you must generate a new token each day.

.. note:: 
     These instructions show how to authenticate by using username and API key
     credentials, which is a more secure way to communicate with API services.
     For information about other types of credentials you can use to
     authenticate, see
     :rax-devdocs:`Authentication requests <cloud-identity/v2/developer-guide/#document-api-operations/token-operations>`
     in the Rackspace Cloud Identity service developer guide.


.. include:: ../common-gs/auth-using-curl.rst

