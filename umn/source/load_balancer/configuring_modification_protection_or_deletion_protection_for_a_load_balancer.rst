:original_name: elb_ug_fz_0007.html

.. _elb_ug_fz_0007:

Configuring Modification Protection or Deletion Protection for a Load Balancer
==============================================================================

You can enable modification protection or deletion protection for load balancers to prevent them from being modified or deleted by accident.

-  Deletion protection: prevents your load balancers from being deleted by accident. Disable **Deletion Protection** If you want to delete a load balancer.
-  Modification protection: prevents your load balancers from being modified by accident. Disable **Modification Protection** if you want to modify or delete a load balancer.

.. _elb_ug_fz_0007__en-us_topic_0000001910425601_section2036320242512:

Enabling or Disabling Deletion Protection
-----------------------------------------

#. Log in to the management console.
#. Click |image1| in the upper left corner of the console and select a desired region and project.
#. Click |image2| in the upper left corner to display **Service List** and choose **Network** > **Elastic Load Balancing**.
#. On the displayed page, locate the load balancer and click its name.
#. Switch to the **Summary** tab of the load balancer and enable or disable **Deletion Protection**.

   .. important::

      If your load balancer is managed by CCE, deleting the load balancer will affect the running of the CCE cluster.

#. After deletion protection is enabled, the load balancer cannot be deleted.

.. _elb_ug_fz_0007__en-us_topic_0000001910425601_section395152674212:

Enabling or Disabling Modification Protection
---------------------------------------------

After modification protection is enabled for a load balancer, you cannot modify or delete the load balancer. But you can perform operations on its listeners, forwarding policies, backend server groups, access control, and access logs.

After modification protection is enabled, the following operations are not allowed: changing the load balancer name, description, backend subnet, or IP address; enabling IP as a backend; binding or unbinding an EIP to or from the load balancer, configuring deletion protection, or changing specifications.

#. Log in to the management console.

#. Click |image3| in the upper left corner of the console and select a desired region and project.

#. Click |image4| in the upper left corner to display **Service List** and choose **Network** > **Elastic Load Balancing**.

#. On the displayed page, locate the load balancer and click its name.

#. Switch to the **Summary** tab and click **Configure** next to **Modification Protection**.

#. In the **Configure Modification Protection** dialog box, enable or disable **Modification Protection**.

   Fill in the reason if needed.

   .. important::

      If your load balancer is managed by CCE, modifying the load balancer will affect the running of the CCE cluster.

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001961843941.png
.. |image2| image:: /_static/images/en-us_image_0000001934685298.png
.. |image3| image:: /_static/images/en-us_image_0000001961843941.png
.. |image4| image:: /_static/images/en-us_image_0000001934685298.png
