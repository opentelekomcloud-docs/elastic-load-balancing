:original_name: elb_ug_hdg_0009.html

.. _elb_ug_hdg_0009:

Enabling Modification Protection
================================

Scenario
--------

You can enable the modification protection for a backend server group to prevent it from being modified or deleted by accident.

Constraints
-----------

If modification protection is enabled for a backend server group, you cannot:

-  Modify its basic information.
-  Configure health checks for it.
-  Add backend servers to it.
-  Delete the backend server group and its associated resources.

Procedure
---------

#. Log in to the management console.
#. In the upper left corner of the page, click |image1| and select the desired region and project.
#. Click |image2| in the upper left corner to display **Service List** and choose **Network** > **Elastic Load Balancing**.
#. In the navigation pane on the left, choose **Elastic Load Balancing** > **Backend Server Groups**.
#. On the **Backend Server Groups** tab page, locate the backend server group and click its name.
#. On the **Summary** tab page, click **Configure** next to **Modification Protection**.
#. In the **Configure Modification Protection** dialog box, enable **Modification Protection**.
#. Click **OK**.

.. note::

   Disable **Modification Protection** if you want to delete a backend server group or modify its settings.

.. |image1| image:: /_static/images/en-us_image_0000001747739624.png
.. |image2| image:: /_static/images/en-us_image_0000001794660485.png
