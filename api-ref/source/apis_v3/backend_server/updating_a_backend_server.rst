:original_name: UpdateMember.html

.. _UpdateMember:

Updating a Backend Server
=========================

Function
--------

This API is used to update a backend server.

Constraints
-----------

If the provisioning status of the associated load balancer is not **ACTIVE**, the backend server cannot be updated.

URI
---

PUT /v3/{project_id}/elb/pools/{pool_id}/members/{member_id}

.. table:: **Table 1** Path Parameters

   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                          |
   +=================+=================+=================+======================================================================================================================================================================+
   | member_id       | Yes             | String          | Specifies the backend server ID.                                                                                                                                     |
   |                 |                 |                 |                                                                                                                                                                      |
   |                 |                 |                 | Note:                                                                                                                                                                |
   |                 |                 |                 |                                                                                                                                                                      |
   |                 |                 |                 | The value of this parameter is not the ID of the server but an ID automatically generated for the backend server that has already associated with the load balancer. |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | pool_id         | Yes             | String          | Specifies the ID of the backend server group.                                                                                                                        |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | project_id      | Yes             | String          | Specifies the project ID.                                                                                                                                            |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

   +--------------+-----------+--------+--------------------------------------------------+
   | Parameter    | Mandatory | Type   | Description                                      |
   +==============+===========+========+==================================================+
   | X-Auth-Token | Yes       | String | Specifies the token used for IAM authentication. |
   +--------------+-----------+--------+--------------------------------------------------+

.. table:: **Table 3** Request body parameters

   +-----------+-----------+-----------------------------------------------------------------------------+-------------------------------+
   | Parameter | Mandatory | Type                                                                        | Description                   |
   +===========+===========+=============================================================================+===============================+
   | member    | Yes       | :ref:`UpdateMemberOption <updatemember__request_updatememberoption>` object | Specifies the backend server. |
   +-----------+-----------+-----------------------------------------------------------------------------+-------------------------------+

.. _updatemember__request_updatememberoption:

.. table:: **Table 4** UpdateMemberOption

   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                                                  |
   +=================+=================+=================+==============================================================================================================================================================================================================================================+
   | admin_state_up  | No              | Boolean         | Specifies the administrative status of the backend server.                                                                                                                                                                                   |
   |                 |                 |                 |                                                                                                                                                                                                                                              |
   |                 |                 |                 | Although this parameter can be used in the APIs for creating and updating backend servers, its actual value depends on whether cloud servers exist. If cloud servers exist, the value is **true**. Otherwise, the value is **false**.        |
   |                 |                 |                 |                                                                                                                                                                                                                                              |
   |                 |                 |                 | This parameter is unsupported. Please do not use it.                                                                                                                                                                                         |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name            | No              | String          | Specifies the backend server name.                                                                                                                                                                                                           |
   |                 |                 |                 |                                                                                                                                                                                                                                              |
   |                 |                 |                 | Minimum: **0**                                                                                                                                                                                                                               |
   |                 |                 |                 |                                                                                                                                                                                                                                              |
   |                 |                 |                 | Maximum: **255**                                                                                                                                                                                                                             |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | weight          | No              | Integer         | Specifies the weight of the backend server. Requests are routed to backend servers in the same backend server group based on their weights.                                                                                                  |
   |                 |                 |                 |                                                                                                                                                                                                                                              |
   |                 |                 |                 | The value ranges from **0** to **100**, and the default value is **1**. The larger the weight is, the higher proportion of requests the backend server receives. If the weight is set to 0, the backend server will not accept new requests. |
   |                 |                 |                 |                                                                                                                                                                                                                                              |
   |                 |                 |                 | If **lb_algorithm** is set to **SOURCE_IP**, this parameter will not take effect.                                                                                                                                                            |
   |                 |                 |                 |                                                                                                                                                                                                                                              |
   |                 |                 |                 | Minimum: **0**                                                                                                                                                                                                                               |
   |                 |                 |                 |                                                                                                                                                                                                                                              |
   |                 |                 |                 | Maximum: **100**                                                                                                                                                                                                                             |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 5** Response body parameters

   +------------+------------------------------------------------------+-----------------------------------------------------------------+
   | Parameter  | Type                                                 | Description                                                     |
   +============+======================================================+=================================================================+
   | request_id | String                                               | Specifies the request ID. The value is automatically generated. |
   +------------+------------------------------------------------------+-----------------------------------------------------------------+
   | member     | :ref:`Member <updatemember__response_member>` object | Specifies the backend server.                                   |
   +------------+------------------------------------------------------+-----------------------------------------------------------------+

.. _updatemember__response_member:

.. table:: **Table 6** Member

   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                                                                       | Description                                                                                                                                                                                                                                                        |
   +=======================+============================================================================+====================================================================================================================================================================================================================================================================+
   | id                    | String                                                                     | Specifies the backend server ID.                                                                                                                                                                                                                                   |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | Note:                                                                                                                                                                                                                                                              |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | The value of this parameter is not the ID of the server but an ID automatically generated for the backend server that has already associated with the load balancer.                                                                                               |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name                  | String                                                                     | Specifies the backend server name.                                                                                                                                                                                                                                 |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | project_id            | String                                                                     | Specifies the project ID of the backend server.                                                                                                                                                                                                                    |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up        | Boolean                                                                    | Specifies the administrative status of the backend server. The value can be **true** or **false**.                                                                                                                                                                 |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | Although this parameter can be used in the APIs for creating and updating backend servers, its actual value depends on whether cloud servers exist. If cloud servers exist, the value is **true**. Otherwise, the value is **false**.                              |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | subnet_cidr_id        | String                                                                     | Specifies the ID of the IPv4 or IPv6 subnet where the backend server resides.                                                                                                                                                                                      |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | This parameter can be left blank, indicating that **IP as a Backend Server** has been enabled for the load balancer. In this case, IP addresses of these servers must be IPv4 addresses, and the protocol of the backend server group must be TCP, HTTP, or HTTPS. |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | The IPv4 or IPv6 subnet must be in the same VPC as the subnet of the load balancer.                                                                                                                                                                                |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | protocol_port         | Integer                                                                    | Specifies the port used by the backend server to receive requests.                                                                                                                                                                                                 |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | Minimum: **1**                                                                                                                                                                                                                                                     |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | Maximum: **65535**                                                                                                                                                                                                                                                 |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | weight                | Integer                                                                    | Specifies the weight of the backend server. Requests are routed to backend servers in the same backend server group based on their weights.                                                                                                                        |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | The value ranges from **0** to **100**, and the default value is **1**. The larger the weight is, the higher proportion of requests the backend server receives. If the weight is set to 0, the backend server will not accept new requests.                       |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | If **lb_algorithm** is set to **SOURCE_IP**, this parameter will not take effect.                                                                                                                                                                                  |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | Minimum: **0**                                                                                                                                                                                                                                                     |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | Maximum: **100**                                                                                                                                                                                                                                                   |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | address               | String                                                                     | Specifies the private IP address bound to the backend server.                                                                                                                                                                                                      |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | -  If **subnet_cidr_id** is left blank, **IP as a Backend Server** is enabled. In this case, the IP address must be an IPv4 address.                                                                                                                               |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | -  If **subnet_cidr_id** is not left blank, the IP address can be IPv4 or IPv6. It must be in the subnet specified by **subnet_cidr_id** and can only be bound to the primary NIC of the backend server.                                                           |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | ip_version            | String                                                                     | Specifies the IP version supported by the backend server. The value can be **v4** (IPv4) or **v6** (IPv6), depending on the value of **address** returned by the system.                                                                                           |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | operating_status      | String                                                                     | Specifies the health status of the backend server if **listener_id** under **status** is not specified. The value can be one of the following:                                                                                                                     |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | -  **ONLINE**: The backend server is running normally.                                                                                                                                                                                                             |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | -  **NO_MONITOR**: No health check is configured for the backend server group to which the backend server belongs.                                                                                                                                                 |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | -  **OFFLINE**: The cloud server used as the backend server is stopped or does not exist.                                                                                                                                                                          |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | Array of :ref:`MemberStatus <updatemember__response_memberstatus>` objects | Specifies the health status of the backend server if **listener_id** is specified.                                                                                                                                                                                 |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | loadbalancer_id       | String                                                                     | Specifies the ID of the load balancer with which the backend server is associated.                                                                                                                                                                                 |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | This parameter is unsupported. Please do not use it.                                                                                                                                                                                                               |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | loadbalancers         | Array of :ref:`ResourceID <updatemember__response_resourceid>` objects     | Specifies the IDs of the load balancers associated with the backend server.                                                                                                                                                                                        |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | This parameter is unsupported. Please do not use it.                                                                                                                                                                                                               |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | created_at            | String                                                                     | Specifies the time when a backend server was added. The format is yyyy-MM-dd'T'HH:mm:ss'Z' (UTC time).                                                                                                                                                             |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | This is a new field in this version, and it will not be returned for resources associated with existing dedicated load balancers and for resources associated with existing and new shared load balancers.                                                         |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | updated_at            | String                                                                     | Specifies the time when a backend server was updated. The format is yyyy-MM-dd'T'HH:mm:ss'Z' (UTC time).                                                                                                                                                           |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | This is a new field in this version, and it will not be returned for resources associated with existing dedicated load balancers and for resources associated with existing and new shared load balancers.                                                         |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | member_type           | String                                                                     | Specifies the type of the backend server. Values:                                                                                                                                                                                                                  |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | -  **ip**: IP as Backend servers                                                                                                                                                                                                                                   |
   |                       |                                                                            |                                                                                                                                                                                                                                                                    |
   |                       |                                                                            | -  **instance**: ECSs used as backend servers                                                                                                                                                                                                                      |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | instance_id           | String                                                                     | Specifies the ID of the ECS used as the backend server. If this parameter is left blank, the backend server is not an ECS. For example, it may be an IP address.                                                                                                   |
   +-----------------------+----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _updatemember__response_memberstatus:

.. table:: **Table 7** MemberStatus

   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                        |
   +=======================+=======================+====================================================================================================================+
   | listener_id           | String                | Specifies the listener ID.                                                                                         |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------+
   | operating_status      | String                | Specifies the health status of the backend server. The value can be one of the following:                          |
   |                       |                       |                                                                                                                    |
   |                       |                       | -  **ONLINE**: The backend server is running normally.                                                             |
   |                       |                       |                                                                                                                    |
   |                       |                       | -  **NO_MONITOR**: No health check is configured for the backend server group to which the backend server belongs. |
   |                       |                       |                                                                                                                    |
   |                       |                       | -  **OFFLINE**: The cloud server used as the backend server is stopped or does not exist.                          |
   +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------+

.. _updatemember__response_resourceid:

.. table:: **Table 8** ResourceID

   ========= ====== ==========================
   Parameter Type   Description
   ========= ====== ==========================
   id        String Specifies the resource ID.
   ========= ====== ==========================

Example Requests
----------------

.. code-block:: text

   PUT https://{ELB_Endpoint}/v3/99a3fff0d03c428eac3678da6a7d0f24/elb/pools/36ce7086-a496-4666-9064-5ba0e6840c75/members/1923923e-fe8a-484f-bdbc-e11559b1f48f

   {
     "member" : {
       "name" : "My member",
       "weight" : 10
     }
   }

Example Responses
-----------------

**Status code: 200**

Successful request.

.. code-block::

   {
     "member" : {
       "name" : "My member",
       "weight" : 10,
       "admin_state_up" : false,
       "subnet_cidr_id" : "c09f620e-3492-4429-ac15-445d5dd9ca74",
       "project_id" : "99a3fff0d03c428eac3678da6a7d0f24",
       "address" : "120.10.10.16",
       "protocol_port" : 89,
       "id" : "1923923e-fe8a-484f-bdbc-e11559b1f48f",
       "operating_status" : "NO_MONITOR",
       "ip_version" : "v4"
     },
     "request_id" : "e7b569d4-15ad-494d-9dd9-8cd740eef8f6"
   }

Status Codes
------------

=========== ===================
Status Code Description
=========== ===================
200         Successful request.
=========== ===================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
