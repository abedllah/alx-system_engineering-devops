Web Infrastructure Design:
Server 1 (Web Server):

Nginx is configured as the web server, serving static content and handling HTTPS requests.
Server 2 (Application Server):

This server runs the application code, processes dynamic content requests, and communicates securely with the database server.
Server 3 (Database Server - Primary):

MySQL is used as the primary database server, handling write operations securely.
Firewalls:

Three firewalls are placed strategically to control and filter incoming and outgoing traffic. They help protect the servers from unauthorized access and potential security threats.
SSL Certificate:

An SSL certificate is installed on the Nginx server to enable HTTPS. This ensures that the communication between users and the website is encrypted, providing data security during transmission.
Monitoring Clients (Sumo Logic):

Three monitoring clients (data collectors for Sumo Logic) are deployed on each server to gather and analyze performance and security-related data.
Monitoring tools provide insights into the health, performance, and security of the infrastructure.
Specifics:
Why Additional Elements:

Firewalls are added to enhance security by controlling and monitoring incoming and outgoing traffic.
SSL certificate is added to encrypt traffic, preventing data interception or tampering during transmission.
Monitoring clients are added to collect and analyze data for performance, security, and troubleshooting purposes.
Firewalls:

Firewalls are implemented to control and filter network traffic based on predefined security rules. They act as a barrier between the servers and potential threats, providing an additional layer of protection.
HTTPS:

Traffic is served over HTTPS to encrypt data during transmission, ensuring confidentiality and integrity. This is crucial for protecting sensitive information such as user credentials and personal data.
Monitoring:

Monitoring is used to track the performance, availability, and security of the infrastructure in real-time. It helps identify issues, anomalies, and potential security threats promptly.
Data Collection by Monitoring Tool:

Monitoring tools collect data by deploying agents or clients on each server. These agents gather information about resource utilization, system logs, and other relevant metrics.
Monitoring Web Server QPS:

To monitor the web server's Queries Per Second (QPS), you can set up custom metrics in the monitoring tool to track the incoming HTTP requests. This can include monitoring Nginx logs or using built-in metrics provided by Nginx.
Issues:
Terminating SSL at the Load Balancer Level:

Terminating SSL at the load balancer level can be an issue because it exposes the traffic in an unencrypted form within the internal network. It's recommended to use end-to-end encryption to ensure secure communication between all components.
Single MySQL Server Capable of Accepting Writes:

Having only one MySQL server capable of accepting writes poses a single point of failure (SPOF). Consider implementing database clustering or replication for better reliability and availability.
Servers with All the Same Components:

Having identical components on all servers might be a problem for scalability and fault tolerance. Consider diversifying server roles, such as having dedicated servers for specific tasks like handling static content, dynamic content, or acting as a database replica.
