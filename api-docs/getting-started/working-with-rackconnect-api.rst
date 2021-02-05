.. _manage-public-ip-address:

Manage public IP address
------------------------------------

You can use the examples in the following sections to manage the public IP address 
by using RackConnect API operations. Before running the examples, 
review the :ref:`RackConnect concepts<concepts>`.  

.. note:: 
     These examples use the ``$API_ENDPOINT``, ``$AUTH_TOKEN``, and ``$TENANT_ID`` environment 
     variables to specify the API endpoint, authentication token, and account ID values 
     for accessing the service. Make sure you 
     :ref:`configure these variables<configure-environment-variables>` before running the 
     code samples. 

As you complete these tasks, keep in mind that these public IP
addresses are being allocated out of your dedicated environment's assigned
public IP blocks. Also, after your RackConnect v3.0 cloud servers are built
and active, you can use the RackConnect v3.0 API to add and remove public IP
addresses from them at any time.

.. include:: examples/list-public-ip-address.rst
.. include:: examples/add-public-ip-address.rst
.. include:: examples/remove-public-ip-address.rst

