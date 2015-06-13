Concepts
~~~~~~~~~~~~~~~~~~~~~

RackConnect v3.0 is the hybrid connectivity offering from Rackspace that
enables you to combine features of Rackspace dedicated and cloud hosting
into one all-encompassing solution.

This section describes the concepts that apply to Cloud Metrics.

Load balancer pools
^^^^^^^^^^^^^^^^^^^^^

Load balancers distribute workloads across two or more servers, network
links or other resources. This distribution maximizes throughput,
minimizes response time and helps avoid overload.

RackConnect v3.0 supports the dedicated F5 BIG-IP Local Traffic Manager
(LTM) and Brocade ADX Series load balancers for use with the management
of RackConnect automated pool membership. 

When your cloud servers host an application that scales up and down (for
example, the web tier of an application), it is important to have a
method for adding and removing cloud servers from their associated load
balancer pools. If you use a dedicated load balancer with RackConnect,
you can specify the load balancer pool that a cloud server should be
placed in when it is created. When you delete the cloud server, it will
automatically be removed from the pool.

After you initially create a cloud server, you can use the following
RackConnect API load balancer pool operations:

-  Retrieve a list of load balancer pools

-  Retrieve pool details for a specific load balancer pool

-  Retrieve a list of all pool member nodes for a specific load balancer
   pool

-  Retrieve details for a specific pool member node (servers) within a
   specific load balancer pool

-  Add a pool member node to a specific load balancer pool

-  Remove a pool member node from a specific load balancer pool

-  Bulk add multiple pool member nodes to one or more load balancer
   pools

-  Bulk remove multiple pool member nodes from one or more load balancer
   pools

The RackConnect API is region-specific and returns results only for the
region specified in the URL of the API call itself. 
