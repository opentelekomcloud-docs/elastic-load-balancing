:original_name: elb_faq_21020223.html

.. _elb_faq_21020223:

Does ELB Support IPv6 Networks?
===============================

When a client communicates with a dedicated network load balancer using an IPv6 address, the load balancer must communicate with backend servers using an IPv6 address. When a client communicates with an application dedicated load balancer using an IPv6 address, the load balancer must communicate with backend servers using an IPv4 address.

.. note::

   -  If IPv6 is not enabled for the backend subnet you select when creating a dedicated load balancer, the load balancer cannot route IPv6 requests.
   -  If you need IPv6 networks, you must select a backend subnet with IPv6 enabled for your dedicated load balancer.
