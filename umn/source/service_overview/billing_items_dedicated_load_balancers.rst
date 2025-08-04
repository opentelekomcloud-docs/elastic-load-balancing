:original_name: elb_billing_0003.html

.. _elb_billing_0003:

Billing Items (Dedicated Load Balancers)
========================================

Billing
-------

You will be charged for how many LCUs you use and how long a load balancer is retained in your account, as described in :ref:`Table 1 <elb_billing_0003__en-us_topic_0000001819164006_table83841175717>`.

For details about the prices of billing items, see the pricing details on the creation page on the console.

.. _elb_billing_0003__en-us_topic_0000001819164006_table83841175717:

.. table:: **Table 1** Billing items

   +-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------+-------------------------------------+
   | Billing Item    | Description                                                                                                                                                                                                                      | Billing Mode    | Billing Formula                     |
   +=================+==================================================================================================================================================================================================================================+=================+=====================================+
   | LCU             | You are charged based on **the number of LCUs used by a load balancer**.                                                                                                                                                         | Pay-per-use     | **Unit price** x **Number of LCUs** |
   |                 |                                                                                                                                                                                                                                  |                 |                                     |
   |                 | An LCU measures the dimensions on which a dedicated load balancer routes the traffic. See LCU prices in LCU Pricing.                                                                                                             |                 |                                     |
   +-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------+-------------------------------------+
   | Load balancer   | You are charged for **how long a dedicated load balancer is retained in your account**. If the load balancer is retained in your account for less than 1 hour, you will be charged for the actual duration, accurate to seconds. | Pay-per-use     | **Unit price x Required duration**  |
   +-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------+-------------------------------------+
   | Specifications  | You are charged by each specification you select.                                                                                                                                                                                | Pay-per-use     | **Unit price x Required duration**  |
   +-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------+-------------------------------------+

The billing items of dedicated load balancers vary by specification type. For details, see :ref:`Table 2 <elb_billing_0003__en-us_topic_0000001819164006_table2032117912396>`.

.. _elb_billing_0003__en-us_topic_0000001819164006_table2032117912396:

.. table:: **Table 2** Billing items

   ============ ============== === =============
   Billing Mode Specifications LCU Load Balancer
   ============ ============== === =============
   Pay-per-use  Elastic        Y   Y
   Pay-per-use  Fixed          Y   x
   ============ ============== === =============

.. note::

   -  Y indicates that the billing item is involved. x indicates that the billing item is not involved.
   -  If you bind an EIP to a load balancer, you will also be charged for the EIP and the bandwidth used by the EIP.

LCU Pricing
-----------

An LCU measures the dimensions on which a dedicated load balancer routes the traffic. See LCU price in :ref:`Table 3 <elb_billing_0003__en-us_topic_0000001819164006_en-us_topic_0000001504522410_table54298422029>`.

The unit price of LCU varies depending on the specifications. See the actual price of LCU on the console. **LCU price = Unit price x Number of LCUs**.

.. _elb_billing_0003__en-us_topic_0000001819164006_en-us_topic_0000001504522410_table54298422029:

.. table:: **Table 3** LCU pricing

   +--------------+--------------------+-------------------------+----------------------------------------------------------------------------+
   | Billing Mode | Specification Type | Application Scenario    | Description                                                                |
   +==============+====================+=========================+============================================================================+
   | Pay-per-use  | Elastic            | For fluctuating traffic | You are charged for how many LCUs you use.                                 |
   +--------------+--------------------+-------------------------+----------------------------------------------------------------------------+
   |              | Fixed              | For stable traffic      | You are charged for the LCUs based on each fixed specification you select. |
   +--------------+--------------------+-------------------------+----------------------------------------------------------------------------+

.. note::

   -  If you deploy a dedicated load balancer in multiple AZs, its performance will multiply as the number of AZs increases.
   -  Note the following when calculating the number of LCUs:

      -  LCU quantity refers to the number of LCUs corresponding to a specification in a single AZ.
      -  If you select multiple AZs for a load balancer, the number of LCUs is calculated as follows: Number of LCUs = LCUs of the selected specification x Number of the selected AZs.

LCU Billing for Elastic Specifications
--------------------------------------

An LCU has four dimensions: **new connections**, **maximum concurrent connections**, **processed bytes**, and **rule evaluations**.

You can calculate the number of LCUs by taking the maximum LCUs consumed across the four dimensions.

.. note::

   The number of LCUs is rounded up to the nearest integer.

.. table:: **Table 4** LCU dimensions

   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Dimension                         | Description                                                                                                                                                         |
   +===================================+=====================================================================================================================================================================+
   | New connections                   | Number of new connections per second.                                                                                                                               |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Maximum concurrent connections    | The maximum number of concurrent connections that a load balancer can handle per minute.                                                                            |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Processed bytes                   | The number of bytes processed by a load balancer in GB.                                                                                                             |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Rule evaluations                  | The product of the number of rules processed by a load balancer and the number of queries per second (QPS).                                                         |
   |                                   |                                                                                                                                                                     |
   | (application load balancing)      | The first 10 processed rules are free.                                                                                                                              |
   |                                   |                                                                                                                                                                     |
   |                                   | -  When there are more than 10 processed rules, the number of rule evaluations is calculated as follows: Rule evaluations = QPS x (Number of processed rules - 10). |
   |                                   | -  When there are 10 or less processed rules, the number of rule evaluations is equal to the QPS.                                                                   |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+

:ref:`Table 5 <elb_billing_0003__en-us_topic_0000001819164006_table1248129113817>` lists the LCU performance supported by different protocols.

For TCP and UDP protocols, it has 3 LCU dimensions, the final LCU dimension will use the dimension which uses the most LCUs after calculation.

For HTTP and HTTPS protocol, it has 4 LCU dimensions, the final LCU dimension will use the dimension which uses the most LCUs after calculation.

.. _elb_billing_0003__en-us_topic_0000001819164006_table1248129113817:

.. table:: **Table 5** LCU performance supported by different protocols

   +------------+----------------------------+-------------------------------------------+-----------------+-----------------------------+
   | Protocol   | New Connections per Second | Maximum Concurrent Connections per Minute | Processed Bytes | Rule Evaluations per Second |
   +============+============================+===========================================+=================+=============================+
   | TCP        | 800                        | 100,000                                   | 1 GB            | ``-``                       |
   +------------+----------------------------+-------------------------------------------+-----------------+-----------------------------+
   | UDP        | 400                        | 50,000                                    | 1 GB            | ``-``                       |
   +------------+----------------------------+-------------------------------------------+-----------------+-----------------------------+
   | HTTP/HTTPS | 25                         | 3,000                                     | 1 GB            | 1,000                       |
   +------------+----------------------------+-------------------------------------------+-----------------+-----------------------------+

Billing Examples
----------------

**A pricing example for a network load balancer**

Assume your network load balancer establishes 1,000 new TCP connections per second and handles a maximum of 180,000 concurrent connections per minute. The bytes processed by your load balancer are 1,000 KB per second.

The LCU price is calculated as the table shown below.

.. table:: **Table 6** LCU calculation

   +-------------------------------------------+----------------------------------------+-----------------------------+-----------------+
   | Dimension                                 | Example                                | LCUs                        | Rounded Up LCUs |
   +===========================================+========================================+=============================+=================+
   | New connections per second                | 1,000                                  | 1,000 ÷ 800 = **1.25**      | 2               |
   +-------------------------------------------+----------------------------------------+-----------------------------+-----------------+
   | Maximum concurrent connections per minute | 180,000                                | 180,000 ÷ 100,000 = **1.8** | 2               |
   +-------------------------------------------+----------------------------------------+-----------------------------+-----------------+
   | Processed bytes per hour                  | 1,000 KB/s x 60s x 60 minutes = 3.6 GB | 3.6 ÷ 1 = **3.6**           | 4               |
   +-------------------------------------------+----------------------------------------+-----------------------------+-----------------+

In this example, the processed bytes dimension consumes the most LCUs (**4** LCUs). Therefore, the LCU price is calculated based on the number of LCUs consumed by processed bytes.

**A pricing example for an application load balancer**

Assume your application load balancer establishes 1,000 new HTTP/HTTPS connections per second and handles a maximum of 180,000 concurrent connections per minute. A client sends an average of 400 requests per second and the bytes processed by this load balancer is 1,000 KB per second. You have configured 20 forwarding rules for your load balancer to route requests.

.. table:: **Table 7** LCU calculation

   +-------------------------------------------+-----------------------------------------------------------+--------------------------+-----------------+
   | Dimension                                 | Example                                                   | LCUs                     | Rounded Up LCUs |
   +===========================================+===========================================================+==========================+=================+
   | New connections per second                | 1,000                                                     | 1,000 ÷ 25 = **40**      | 40              |
   +-------------------------------------------+-----------------------------------------------------------+--------------------------+-----------------+
   | Maximum concurrent connections per minute | 180,000                                                   | 180,000 ÷ 3,000 = **60** | 60              |
   +-------------------------------------------+-----------------------------------------------------------+--------------------------+-----------------+
   | Processed bytes per hour                  | 1,000 KB/s x 60s x 60 minutes = 3.6 GB                    | 3.6 ÷ 1 = **3.6**        | 4               |
   +-------------------------------------------+-----------------------------------------------------------+--------------------------+-----------------+
   | Rule evaluations per second               | Rule evaluations are calculated as:                       | 4,000 ÷ 1,000 = **4**    | 4               |
   |                                           |                                                           |                          |                 |
   |                                           | Rule evaluations = QPS x (Number of processed rules - 10) |                          |                 |
   |                                           |                                                           |                          |                 |
   |                                           | = 400 x (20 - 10) = 4,000                                 |                          |                 |
   +-------------------------------------------+-----------------------------------------------------------+--------------------------+-----------------+

In this example, the maximum concurrent connection dimension consumes the most LCUs (**60** LCUs). So the LCU price is calculated based on the LCUs consumed by the maximum concurrent connections.

Load Balancer Pricing
---------------------

You are charged for how long each load balancer is retained in your account. If the load balancer is used for less than 1 hour, you will be charged for the actual duration, accurate to seconds. The billing cycle is from the time when the dedicated load balancer is created to the time when it is deleted.

Only load balancers with elastic specifications in pay-per-use billing mode are charged.
