:original_name: DeleteLoadBalancerForce.html

.. _DeleteLoadBalancerForce:

Deleting a Load Balancer and Its Associated Resources
=====================================================

Function
--------

This API is used to delete a load balancer and its associated resources, including the listeners, backend server groups, and backend servers.

Note:

-  If a load balancer has EIPs bound to it, the EIPs will be unbound from the load balancer.

-  If Deletion protection feature is enabled for ELB, it won’t be possible to delete the ELB and it’s resources.

-  If Removal protection feature is enabled for a Backend Server Group used by the ELB, it won’t be possible to delete the ELB and it’s resources.

-  If only Modification protection feature is enabled it won’t protect it from force-deletion.

URI
---

DELETE /v3/{project_id}/elb/loadbalancers/{loadbalancer_id}/force-elb

.. table:: **Table 1** Path Parameters

   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                          |
   +=================+=================+=================+======================================================================================================+
   | project_id      | Yes             | String          | **Definition**: Specifies the project ID.                                                            |
   |                 |                 |                 |                                                                                                      |
   |                 |                 |                 | **Constraints**: N/A                                                                                 |
   |                 |                 |                 |                                                                                                      |
   |                 |                 |                 | **Range**: The value can contain a maximum of 32 characters, including digits and lowercase letters. |
   |                 |                 |                 |                                                                                                      |
   |                 |                 |                 | **Default value**: N/A                                                                               |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------+
   | loadbalancer_id | Yes             | String          | **Definition**: Specifies the load balancer ID.                                                      |
   |                 |                 |                 |                                                                                                      |
   |                 |                 |                 | **Constraints**: N/A                                                                                 |
   |                 |                 |                 |                                                                                                      |
   |                 |                 |                 | **Range**: N/A                                                                                       |
   |                 |                 |                 |                                                                                                      |
   |                 |                 |                 | **Default value**: N/A                                                                               |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

   +-----------------+-----------------+-----------------+------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                      |
   +=================+=================+=================+==================================================================+
   | X-Auth-Token    | Yes             | String          | **Definition**: Specifies the token used for IAM authentication. |
   |                 |                 |                 |                                                                  |
   |                 |                 |                 | **Constraints**: N/A                                             |
   |                 |                 |                 |                                                                  |
   |                 |                 |                 | **Range**: N/A                                                   |
   |                 |                 |                 |                                                                  |
   |                 |                 |                 | **Default value**: N/A                                           |
   +-----------------+-----------------+-----------------+------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 204**

Successful request.

None

Example Requests
----------------

Deleting a load balancer and resources associated with it

.. code-block:: text

   DELETE https://{ELB_Endpoint}/v3/060576782980d5762f9ec014dd2f1148/elb/loadbalancers/32c1057f-74a1-42d6-9b20-d55b80ab89c4/force-elb

Example Responses
-----------------

None

Status Codes
------------

=========== ===================
Status Code Description
=========== ===================
204         Successful request.
=========== ===================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
