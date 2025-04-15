:original_name: en-us_topic_0015479966.html

.. _en-us_topic_0015479966:

What Is ELB?
============

Elastic Load Balancing (ELB) automatically distributes incoming traffic across multiple backend servers based on the listening rules you configure. ELB expands the service capabilities of your applications and improves their availability by eliminating single points of failure (SPOFs).

As shown in the example in the following figure, ELB distributes incoming traffic to three application servers, and each server processes one third of the requests. ELB also provides health checks, which can detect unhealthy servers. Traffic is distributed only to servers that are running normally, improving the availability of applications.


.. figure:: /_static/images/en-us_image_0000001747381220.png
   :alt: **Figure 1** Using a load balancer

   **Figure 1** Using a load balancer

.. _en-us_topic_0015479966__section031725010213:

ELB Components
--------------

ELB consists of the following components:

-  A load balancer distributes incoming traffic across multiple backend servers in one or more AZs.

-  A listener uses the protocol and port you specify to check requests from clients and route the requests to associated backend servers based on the routing policies and forwarding policies you configure. You can add one or more listeners to a load balancer.

-  A backend server group uses the protocol and port you specify to receive the requests from the load balancer and route them to one or more backend servers. You need to add at least one backend server to a backend server group.

   You can set a weight for each backend server based on their performance.

   You can also configure health checks for a backend server group to check the health of each backend server. When a backend server is unhealthy, the load balancer stops routing new requests to it.


.. figure:: /_static/images/en-us_image_0000001794820049.png
   :alt: **Figure 2** ELB components

   **Figure 2** ELB components

Load Balancer Types
-------------------

ELB provides dedicated load balancers and shared load balancers.


.. figure:: /_static/images/en-us_image_0000001794660965.png
   :alt: **Figure 3** Load balancer types

   **Figure 3** Load balancer types

-  Dedicated load balancers have exclusive use of underlying resources, so that the performance of a dedicated load balancer is not affected by other load balancers. In addition, there are a wide range of specifications available for selection.

.. note::

   -  In the eu-de region, you can create both dedicated and shared load balancers, and you can create either type of load balancers on the management console or by calling APIs.
   -  In the eu-nl region, you can only create dedicated load balancers, either on the console or by calling APIs.

-  Shared load balancers are deployed in clusters. They share underlying resources, so the performance of a load balancer is affected by other load balancers. Shared load balancers were previously named enhanced load balancers.

For details about the differences between dedicated and shared load balancers, see :ref:`Differences Between Dedicated and Shared Load Balancers <elb_pro_0004>`.

.. _en-us_topic_0015479966__section17818164132517:

Accessing ELB
-------------

You can use either of the following methods to access ELB:

-  Management console

   Log in to the management console and choose **Elastic Load Balance (ELB)**.

-  APIs

   You can call APIs to access ELB. For details, see the *Elastic Load Balancing API Reference*.

   .. note::

      In the eu-de region, you can create both dedicated and shared load balancers, and you can create either type of load balancers on the management console or by calling APIs.

      In the eu-nl region, you can only create dedicated load balancers, either on the console or by calling APIs.
