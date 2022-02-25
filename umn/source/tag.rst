Tag
===

Scenarios
---------

If you have a large number of cloud resources, you can assign different tags to the resources to quickly identify them and use these tags to easily manage your resources.

Adding a Tag to a Load Balancer
-------------------------------

You can add a tag to a load balancer in either of the following scenarios:

-  Add a tag when you create a load balancer.

   For detailed operations, see `Creating a Shared Load Balancer <en-us_topic_0015479967.html#en-us_topic_0015479967__section19343262431>`__.

-  Add a tag to an existing load balancer.

   #. Log in to the management console.
   #. In the upper left corner of the page, click |image1| and select the desired region and project.
   #. Hover on |image2| in the upper left corner to display **Service List** and choose **Network** > **Elastic Load Balancing**.
   #. Locate the load balancer and click its name.
   #. Under **Tags**, click **Add Tag**.
   #. In the **Add Tag** dialog box, enter a tag key and value and click **OK**.\ |image3|

      -  A maximum of 20 tags can be added to a load balancer.
      -  Each tag is a key-value pair, and the tag key is unique.

Adding a Tag to a Listener
--------------------------

You can add tags when you add listeners.

To add a tag to an existing listener, perform the following steps:

#. Log in to the management console.
#. In the upper left corner of the page, click |image4| and select the desired region and project.
#. Hover on |image5| in the upper left corner to display **Service List** and choose **Network** > **Elastic Load Balancing**.
#. Locate the load balancer and click its name.
#. Click **Listeners**, locate the listener, and click its name.
#. Under **Tags**, click **Add Tag**.
#. In the **Add Tag** dialog box, enter a tag key and value and click **OK**.\ |image6|

   -  A maximum of 20 tags can be added to a listener.
   -  Each tag is a key-value pair, and the tag key is unique.

Modifying a Tag
---------------

#. Log in to the management console.

#. In the upper left corner of the page, click |image7| and select the desired region and project.

#. Hover on |image8| in the upper left corner to display **Service List** and choose **Network** > **Elastic Load Balancing**.

#. Locate the load balancer and click its name.

#. Click **Tags**, select the tag to be edited, and click **Edit** in the **Operation** column. In the **Edit Tag** dialog box, change the tag value.\ |image9|

   The tag key cannot be changed.

#. Click **OK**.

The operations for modifying a listener tag are not detailed here. Refer to the operations of modifying a load balancer tag.

Deleting a Tag
--------------

#. Log in to the management console.
#. In the upper left corner of the page, click |image10| and select the desired region and project.
#. Hover on |image11| in the upper left corner to display **Service List** and choose **Network** > **Elastic Load Balancing**.
#. Locate the load balancer and click its name.
#. Click **Tags**, select the tag to be deleted, and click **Delete** in the **Operation** column.
#. In the **Delete Tag** dialog box, click **Yes**.

The operations for deleting a listener tag are not detailed here. Refer to the operations of deleting a load balancer tag.

.. |image1| image:: /images/en-us_image_0241356603.png

.. |image2| image:: /images/en-us_image_0000001120894978.png

.. |image3| image:: /images/note_3.0-en-us.png
.. |image4| image:: /images/en-us_image_0241356603.png

.. |image5| image:: /images/en-us_image_0000001120894978.png

.. |image6| image:: /images/note_3.0-en-us.png
.. |image7| image:: /images/en-us_image_0241356603.png

.. |image8| image:: /images/en-us_image_0000001120894978.png

.. |image9| image:: /images/note_3.0-en-us.png
.. |image10| image:: /images/en-us_image_0241356603.png

.. |image11| image:: /images/en-us_image_0000001120894978.png

