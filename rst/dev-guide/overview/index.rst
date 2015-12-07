=========================
About the Rackconnect API
=========================

The Rackspace RackConnect service allows customers connect dedicated Rackspace resources to the Rackspac Cloud servers by using Cisco ASA Firewall or an F5 load balancer.

You can use the RackConnect 3.0 API to accomplish the following tasks:

-  Seamlessly add and remove cloud servers from your load balancer pools

-  List your available load balancer pools

-  Add and remove public IP addresses from your cloud servers

-  List your public IP addresses

-  List the cloud networks associated with your RackConnect
   configuration

RackConnect is based on and requires Rackspace Cloud Networks for
cloud-side connectivity. Because of this, RackConnect is compatible only
with the same types of Cloud Servers that Cloud Networks supports, which
excludes first-generation Cloud Servers.

RackConnect has configuration options that can improve security for your
Cloud Servers environment, including support for servers built with only
a single network interface connected to an isolated cloud network.

You can choose to create a truly isolated and secure Cloud Servers
environment that has connectivity only with other servers on the same
isolated network, or you can allow network access to your dedicated
networks or the Internet.

To further increase the security of your RackConnect environment, you
also have the ability to use the Rackspace dedicated intrusion detection
system (IDS) and web application firewall (WAF) offerings.

.. toctree:: :hidden:
   :maxdepth: 2

   additional-resources
   document-change-history
   Pricing and terms of service <pricing-service-level>
