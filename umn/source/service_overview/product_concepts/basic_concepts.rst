Basic Concepts
==============



.. _elb_pro_0001__table17643195014453:

.. table:: **Table 1** Some concepts about ELB

   +-----------------------+---------------------------------------------------------------------------------------------+
   | Term                  | Definition                                                                                  |
   +=======================+=============================================================================================+
   | Load balancer         | A load balancer distributes incoming traffic across backend servers.                        |
   +-----------------------+---------------------------------------------------------------------------------------------+
   | Listener              | A listener listens on requests from clients and routes the requests to backend servers      |
   |                       | based on the settings that you configure when you add the listener.                         |
   +-----------------------+---------------------------------------------------------------------------------------------+
   | Backend server        | A backend server is a cloud server added to a backend server group associated with a load   |
   |                       | balancer. When you add a listener to a load balancer, you can create or select a backend    |
   |                       | server group to receive requests from the load balancer by using the port and protocol you  |
   |                       | specify for the backend server group and the load balancing algorithm you select.           |
   +-----------------------+---------------------------------------------------------------------------------------------+
   | Backend server group  | A backend server group is a collection of cloud servers that have same features. When you   |
   |                       | add a listener, you select a load balancing algorithm and create or select a backend server |
   |                       | group. Incoming traffic is routed to the corresponding backend server group based on the    |
   |                       | listener's configuration.                                                                   |
   +-----------------------+---------------------------------------------------------------------------------------------+
   | Health check          | ELB periodically sends requests to backend servers to check whether they can process        |
   |                       | requests. If a backend server is detected as unhealthy, the load balancer stops routing     |
   |                       | requests to it. After the backend server recovers, the load balancer will resume routing    |
   |                       | requests to it.                                                                             |
   +-----------------------+---------------------------------------------------------------------------------------------+
   | Redirect              | HTTPS is an extension of HTTP. HTTPS encrypts data between a web server and a browser.      |
   +-----------------------+---------------------------------------------------------------------------------------------+
   | Sticky session        | Sticky sessions ensure that requests from a client always get routed to the same backend    |
   |                       | server before a session elapses.                                                            |
   +-----------------------+---------------------------------------------------------------------------------------------+
   | WebSocket             | WebSocket is a new HTML5 protocol that provides full-duplex communication between the       |
   |                       | browser and the server. WebSocket saves server resources and bandwidth, and enables         |
   |                       | real-time communication. Both WebSocket and HTTP depend on TCP to transmit data. A          |
   |                       | handshake connection is required between the browser and server, so that they can           |
   |                       | communicate with each other only after the connection is established. However, as a         |
   |                       | bidirectional communication protocol, WebSocket is different from HTTP. After the handshake |
   |                       | succeeds, both the server and browser (or client agent) can actively send data to or        |
   |                       | receive data from each other.                                                               |
   +-----------------------+---------------------------------------------------------------------------------------------+
   | SNI                   | SNI is an extension to TLS and enables a server to present multiple certificates on the     |
   |                       | same IP address and TCP port number. This allows multiple secure (HTTPS) websites (or any   |
   |                       | other service over TLS) to be served by the same IP address without requiring all websites  |
   |                       | to use the same certificate. SNI allows the client to submit the domain name information    |
   |                       | while sending an SSL handshake request. Once the load balancer receives the request, it     |
   |                       | queries the right certificate based on the domain name and returns the corresponding        |
   |                       | certificate to the client. If no certificate is found, the load balancer will return a      |
   |                       | default certificate.                                                                        |
   +-----------------------+---------------------------------------------------------------------------------------------+
   | Persistent connection | A persistent connection allows multiple data packets to be sent continuously over a TCP     |
   |                       | connection. If no data packet is sent during the connection, the client and server send     |
   |                       | link detection packets to each other to maintain the connection.                            |
   +-----------------------+---------------------------------------------------------------------------------------------+
   | Short connection      | A short connection is a connection established when data is exchanged between the client    |
   |                       | and server and immediately closed after the data is sent.                                   |
   +-----------------------+---------------------------------------------------------------------------------------------+
   | Concurrent connection | Concurrent connections are total number of TCP connections initiated by clients and routed  |
   |                       | to backend servers by a load balancer per second.                                           |
   +-----------------------+---------------------------------------------------------------------------------------------+
