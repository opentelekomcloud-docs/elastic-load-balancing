:original_name: elb_zq_pe_0001.html

.. _elb_zq_pe_0001:

Querying Default Resource Quotas
================================

Function
--------

This API is used to query default quotas of load balancer, listener, backend server group, backend server, health check, forwarding policy, and certificate.

URI
---

GET /v2.0/lbaas/quotas/defaults

Request
-------

None

Response
--------

.. table:: **Table 1** Response parameters

   +-----------+--------+----------------------------------------------------------------------------------------------------------------------------------+
   | Parameter | Type   | Description                                                                                                                      |
   +===========+========+==================================================================================================================================+
   | quota     | String | Specifies the resource quotas. For details, see :ref:`Table 2 <elb_zq_pe_0001__en-us_topic_0000001175381421_table125937123518>`. |
   +-----------+--------+----------------------------------------------------------------------------------------------------------------------------------+

.. _elb_zq_pe_0001__en-us_topic_0000001175381421_table125937123518:

.. table:: **Table 2** **quota** parameter description

   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+
   | Parameter                                | Type    | Description                                                                                       |
   +==========================================+=========+===================================================================================================+
   | healthmonitor                            | Integer | Specifies the health check quota.                                                                 |
   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+
   | listener                                 | Integer | Specifies the listener quota.                                                                     |
   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+
   | loadbalancer                             | Integer | Specifies the load balancer quota.                                                                |
   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+
   | member                                   | Integer | Specifies the backend server quota.                                                               |
   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+
   | pool                                     | Integer | Specifies the backend server group quota.                                                         |
   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+
   | l7policy                                 | Integer | Specifies the forwarding policy quota.                                                            |
   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+
   | certificate                              | Integer | Specifies the certificate quota.                                                                  |
   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+
   | ipgroup                                  | Integer | Specifies the IP address group quota.                                                             |
   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+
   | security_policy                          | Integer | Specifies the custom security policy quota.                                                       |
   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+
   | listeners_per_loadbalancer               | Integer | Specifies the maximum number of listeners that can be added to a load balancer.                   |
   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+
   | listeners_per_pool                       | Integer | Specifies the maximum number of listeners that can be associated with a backend server group.     |
   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+
   | condition_per_policy                     | Integer | Specifies the maximum number of forwarding conditions per forwarding policy.                      |
   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+
   | members_per_pool                         | Integer | Specifies the maximum number of backend servers that can be added to a backend server group.      |
   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+
   | ipgroup_bindings                         | Integer | Specifies the maximum number of listeners that can be associated with an IP address group.        |
   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+
   | ipgroup_max_length                       | Integer | Specifies the maximum number of IP entries that can be added to an IP address group.              |
   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+
   | free_instance_listeners_per_loadbalancer | Integer | Specifies the maximum number of free listeners that can be added to a load balancer.              |
   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+
   | free_instance_members_per_pool           | Integer | Specifies the maximum number of free backend servers that can be added to a backend server group. |
   +------------------------------------------+---------+---------------------------------------------------------------------------------------------------+

.. note::

   **-1** indicates that the quota is not limited.

Example Request
---------------

-  Example request: Querying default resource quotas

   .. code-block:: text

      GET https://{Endpoint}/v2.0/lbaas/quotas/defaults

Example Response
----------------

-  Example response

   .. code-block::

      {
          "quota": {
              "ipgroup_bindings": 50,
              "condition_per_policy": 10,
              "listeners_per_loadbalancer": 50,
              "member": 500,
              "free_instance_members_per_pool": 10,
              "loadbalancer": 50,
              "ipgroup": 50,
              "listeners_per_pool": 50,
              "certificate": 120,
              "healthmonitor": -1,
              "ipgroup_max_length": 300,
              "l7policy": 500,
              "listener": 100,
              "free_instance_listeners_per_loadbalancer": 5,
              "members_per_pool": 500,
              "security_policy": 50,
              "pool": 500
          }
      }

Status Code
-----------

For details, see :ref:`HTTP Status Codes of Shared Load Balancers <elb_gc_0002>`.
