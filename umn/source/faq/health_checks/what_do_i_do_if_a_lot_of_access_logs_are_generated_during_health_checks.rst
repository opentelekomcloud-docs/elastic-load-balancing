:original_name: elb_faq_0070.html

.. _elb_faq_0070:

What Do I Do If a Lot of Access Logs Are Generated During Health Checks?
========================================================================

#. You can increase the health check interval by referring to :ref:`Modifying Health Check Settings <en-us_topic_0000001747380572>`.

   Risk: After the health check interval is prolonged, the time for the load balancer to detect unhealthy servers will increase.

#. You can disable the health check by referring to :ref:`Modifying Health Check Settings <en-us_topic_0000001747380572>`.

   Risk: After health checks are disabled, the load balancer will not check the backend servers. If a backend server becomes faulty, the load balancer will still route requests to this server.
