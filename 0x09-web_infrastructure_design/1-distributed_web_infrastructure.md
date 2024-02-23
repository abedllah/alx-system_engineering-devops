Web Infrastructure Design:
Server 1 (Web Server):

Nginx is configured as the web server, handling incoming HTTP requests and serving static content.
It communicates with the application server and Load Balancer.
Server 2 (Application Server):

This server runs the application code and processes dynamic content requests.
It communicates with the database server and serves as one of the application server instances.
Server 3 (Database Server - Primary):

MySQL is used as the primary database server, handling write operations.
Load Balancer (HAproxy):

HAproxy distributes incoming traffic among multiple application server instances, improving scalability and reliability.
It is configured with a distribution algorithm (e.g., round-robin) to balance the load across application servers.
Application Files (Code Base):

The application files contain the code that defines the website's functionality.
These files are hosted on both application servers.

