:original_name: elb_faq_210608.html

.. _elb_faq_210608:

What Status Codes Will Be Returned If Backend Servers Are Identified as Healthy?
================================================================================

.. table:: **Table 1** Health check status codes

   +--------------------------+-----------------------+-----------------------+
   | Load Balancer Type       | Health Check Protocol | Status Code           |
   +==========================+=======================+=======================+
   | Dedicated load balancers | HTTP                  | 200                   |
   +--------------------------+-----------------------+-----------------------+
   |                          | HTTPS                 | 200                   |
   +--------------------------+-----------------------+-----------------------+
   | Shared load balancers    | HTTP                  | -  200                |
   |                          |                       | -  202                |
   |                          |                       | -  401                |
   +--------------------------+-----------------------+-----------------------+
