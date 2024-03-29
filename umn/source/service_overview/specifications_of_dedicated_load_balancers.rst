:original_name: en-us_topic_0287737145.html

.. _en-us_topic_0287737145:

Specifications of Dedicated Load Balancers
==========================================

Load balancers are available in different specifications. Choose the specifications that best meet your needs. If the traffic exceeds the selected specifications, new requests will be discarded.

-  Maximum concurrent connections

   Indicates the maximum number of concurrent connections that a load balancer can handle. If the number reaches the maximum connections that defined in the specification, new requests will be discarded to ensure the performance of the established connections.

-  Connections per second (CPS)

   Indicates the number of new connections that a load balancer can establish per second. If the number reaches the CPS that defined in the specification, new requests will be discarded to ensure the performance of established connections.

   HTTPS listeners need to create SSL handshakes to establish connections with clients, and such SSL handshakes occupy more system resources than HTTP listeners. For example, a small I application load balancer can establish 2,000 new HTTP connections per second but only 200 new HTTPS connections per second.

   For a small I application load balancer:

   -  If you only add an HTTP listener, the load balancer can establish up to 2,000 new HTTP connections.

   -  If you only add an HTTPS listener, the load balancer can establish up to 200 new HTTPS connections.

   -  If you add an HTTPS listener and an HTTP listener, the new connections are calculated using the following formula:

      New connections = New HTTP connections + New HTTPS connections x Ratio of HTTP connections to HTTPS connections

      For a small I application load balancer, the ratio of HTTP connections to HTTPS connections is 10. For details, see :ref:`Table 1 <en-us_topic_0287737145__table2863652175713>`.

      .. _en-us_topic_0287737145__table2863652175713:

      .. table:: **Table 1** New connections that a small I application load balancer can establish

         +--------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Parameter                      | Scenario 1                                                                                                                                                      | Scenario 2                                                                                                                                           |
         +================================+=================================================================================================================================================================+======================================================================================================================================================+
         | New HTTP connections           | 1,000                                                                                                                                                           | 1,000                                                                                                                                                |
         +--------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
         | New HTTPS connections          | 50                                                                                                                                                              | 150                                                                                                                                                  |
         +--------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
         | New HTTP and HTTPS connections | 1,000 + 50 x 10 = 1,500                                                                                                                                         | 1,000 + 150 x 10 = 2,500                                                                                                                             |
         +--------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Description                    | The new connections do not reach the CPS (HTTP) defined in :ref:`Table 3 <en-us_topic_0287737145__table201281815505>`, and new requests can be properly routed. | The new connections exceed the CPS (HTTP) defined in :ref:`Table 3 <en-us_topic_0287737145__table201281815505>`, and new requests will be discarded. |
         +--------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------+

      .. note::

         Details in the :ref:`Table 1 <en-us_topic_0287737145__table2863652175713>` are for reference only.

-  Queries per second (QPS)

   Indicates the number of HTTP or HTTPS requests sent to a backend server per second. If the QPS reaches that defined in the specification, new requests will be discarded to ensure the performance of established connections.

-  Bandwidth (Mbit/s)

   Indicates the maximum amount of data that can be transmitted over a load balancer per second.

:ref:`Table 2 <en-us_topic_0287737145__table14428152722818>` and :ref:`Table 3 <en-us_topic_0287737145__table201281815505>` list the specifications of dedicated load balancers.

.. caution::

   -  **Available fixed specifications are displayed on the console and may vary depending on the resources in different regions.**

   -  The load balancing type cannot be changed after being selected.

      For example, after you select network load balancing, you cannot change it to application load balancing. You can add only TCP and UDP listeners and cannot add HTTP and HTTPS listeners.

.. _en-us_topic_0287737145__table14428152722818:

.. table:: **Table 2** Specifications for network load balancing (TCP/UDP)

   +-----------+--------------------------------+---------+--------------------+---------------+
   | Type      | Maximum Concurrent Connections | CPS     | Bandwidth (Mbit/s) | LCUs in an AZ |
   +===========+================================+=========+====================+===============+
   | Small I   | 500,000                        | 10,000  | 50                 | 10            |
   +-----------+--------------------------------+---------+--------------------+---------------+
   | Small II  | 1,000,000                      | 20,000  | 100                | 20            |
   +-----------+--------------------------------+---------+--------------------+---------------+
   | Medium I  | 2,000,000                      | 40,000  | 200                | 40            |
   +-----------+--------------------------------+---------+--------------------+---------------+
   | Medium II | 4,000,000                      | 80,000  | 400                | 80            |
   +-----------+--------------------------------+---------+--------------------+---------------+
   | Large I   | 10,000,000                     | 200,000 | 1,000              | 200           |
   +-----------+--------------------------------+---------+--------------------+---------------+
   | Large II  | 20,000,000                     | 400,000 | 2,000              | 400           |
   +-----------+--------------------------------+---------+--------------------+---------------+

.. _en-us_topic_0287737145__table201281815505:

.. table:: **Table 3** Specifications for application load balancing (HTTP/HTTPS)

   +-----------+--------------------------------+------------+-------------+------------+-------------+--------------------+-------------------------+
   | Type      | Maximum Concurrent Connections | CPS (HTTP) | CPS (HTTPS) | QPS (HTTP) | QPS (HTTPS) | Bandwidth (Mbit/s) | Number of LCUs in an AZ |
   +===========+================================+============+=============+============+=============+====================+=========================+
   | Small I   | 200,000                        | 2,000      | 200         | 4,000      | 2,000       | 50                 | 10                      |
   +-----------+--------------------------------+------------+-------------+------------+-------------+--------------------+-------------------------+
   | Small II  | 400,000                        | 4,000      | 400         | 8,000      | 4,000       | 100                | 20                      |
   +-----------+--------------------------------+------------+-------------+------------+-------------+--------------------+-------------------------+
   | Medium I  | 800,000                        | 8,000      | 800         | 16,000     | 8,000       | 200                | 40                      |
   +-----------+--------------------------------+------------+-------------+------------+-------------+--------------------+-------------------------+
   | Medium II | 2,000,000                      | 20,000     | 2,000       | 40,000     | 20,000      | 400                | 100                     |
   +-----------+--------------------------------+------------+-------------+------------+-------------+--------------------+-------------------------+
   | Large I   | 4,000,000                      | 40,000     | 4,000       | 80,000     | 40,000      | 1,000              | 200                     |
   +-----------+--------------------------------+------------+-------------+------------+-------------+--------------------+-------------------------+
   | Large II  | 8,000,000                      | 80,000     | 8,000       | 160,000    | 80,000      | 2,000              | 400                     |
   +-----------+--------------------------------+------------+-------------+------------+-------------+--------------------+-------------------------+

.. note::

   -  If you add multiple listeners to a load balancer, the sum of QPS values of all listeners cannot exceed the QPS defined in each specification.
   -  The bandwidth is the upper limit of the inbound or the outbound traffic. For example, for small I load balancers, the inbound or outbound traffic cannot exceed 50 Mbit/s.
   -  The bandwidth included in each specification is the maximum bandwidth provided by ELB. If the maximum bandwidth is exceeded, the network performance may be affected.
