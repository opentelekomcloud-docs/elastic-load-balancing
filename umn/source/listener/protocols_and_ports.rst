:original_name: elb_ug_jt_0002.html

.. _elb_ug_jt_0002:

Protocols and Ports
===================

Frontend Protocols and Ports
----------------------------

Frontend protocols and ports are used by load balancers to receive requests from clients. Load balancers use TCP or UDP at Layer 4, and HTTP or HTTPS at Layer 7. Select a protocol and a port that best suit your requirements.

.. note::

   The selected frontend protocols and entered ports cannot be changed. If you want to change them, create another listener.

.. table:: **Table 1** Frontend protocols and ports

   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Protocol                          | Port                                                                                                                                                                                                                                                                                                                                                                                         |
   +===================================+==============================================================================================================================================================================================================================================================================================================================================================================================+
   | -  TCP                            | There are some restrictions when you select the protocols and port numbers.                                                                                                                                                                                                                                                                                                                  |
   | -  UDP                            |                                                                                                                                                                                                                                                                                                                                                                                              |
   | -  HTTP                           | -  For each load balancer, UDP can use the same ports as other protocols, but these other protocols must have unique ports. For example, if you have a UDP listener that uses port 88, you can add a TCP, HTTP, or HTTPS listener that also uses port 88. However, if you already have an HTTP listener that uses port 443, you cannot add an HTTPS or TCP listener that uses the same port. |
   | -  HTTPS                          | -  The port numbers of the same protocol must be unique. For example, if you have a TCP listener that uses port 80, you cannot add another TCP listener that uses the same port.                                                                                                                                                                                                             |
   |                                   |                                                                                                                                                                                                                                                                                                                                                                                              |
   |                                   | The port number ranges from 1 to 65535.                                                                                                                                                                                                                                                                                                                                                      |
   |                                   |                                                                                                                                                                                                                                                                                                                                                                                              |
   |                                   | The following are some commonly-used protocols and port numbers:                                                                                                                                                                                                                                                                                                                             |
   |                                   |                                                                                                                                                                                                                                                                                                                                                                                              |
   |                                   | TCP/80                                                                                                                                                                                                                                                                                                                                                                                       |
   |                                   |                                                                                                                                                                                                                                                                                                                                                                                              |
   |                                   | HTTPS/443                                                                                                                                                                                                                                                                                                                                                                                    |
   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Backend Protocols and Ports
---------------------------

Backend protocols and ports are used by backend servers to receive requests from load balancers. If Windows servers have Internet Information Services (IIS) installed, the default backend protocol and port are HTTP and 80.

.. table:: **Table 2** Backend protocols and ports

   +-----------------------------------+---------------------------------------------------------------------------------+
   | Protocol                          | Port                                                                            |
   +===================================+=================================================================================+
   | TCP                               | Backend servers can use the same ports. The port number ranges from 1 to 65535. |
   |                                   |                                                                                 |
   |                                   | The following are some commonly-used protocols and port numbers:                |
   |                                   |                                                                                 |
   |                                   | TCP/80                                                                          |
   |                                   |                                                                                 |
   |                                   | HTTP/80                                                                         |
   |                                   |                                                                                 |
   |                                   | HTTPS/443                                                                       |
   +-----------------------------------+---------------------------------------------------------------------------------+
   | UDP                               |                                                                                 |
   +-----------------------------------+---------------------------------------------------------------------------------+
   | QUIC                              |                                                                                 |
   +-----------------------------------+---------------------------------------------------------------------------------+
   | HTTP                              |                                                                                 |
   +-----------------------------------+---------------------------------------------------------------------------------+
   | HTTPS                             |                                                                                 |
   +-----------------------------------+---------------------------------------------------------------------------------+

.. note::

   QUIC is supported only by dedicated load balancers.
