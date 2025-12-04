:original_name: DeleteListenerForce.html

.. _DeleteListenerForce:

Deleting a Listener and Its Associated Resources
================================================

Function
--------

This API is used to delete a listener and its associated resources, including the forwarding policies and backend server groups.

URI
---

DELETE /v3/{project_id}/elb/listeners/{listener_id}/force

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
   | listener_id     | Yes             | String          | Specifies the listener ID.                                                                           |
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

Deleting a listener and its associated resources

.. code-block:: text

   DELETE https://{ELB_Endpoint}/v3/99a3fff0d03c428eac3678da6a7d0f24/elb/listeners/0b11747a-b139-492f-9692-2df0b1c87193/force

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
