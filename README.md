# CBSE-website-load-balancing
CBSE website load balancing using Nginx, Docker and Node.js

Problem
During peak result times, the CBSE website faces high traffic, causing slow responses and server crashes. Single-server setups fail to handle this load efficiently, and lack of monitoring makes it hard to detect issues.

Solution:
A load-balanced, containerized architecture was implemented to ensure high availability and performance:
--> 5 Web Servers: Identical Node.js/Express instances serving the result site.
--> Nginx Load Balancer: Distributes traffic evenly to prevent overload.
--> Docker Containers: Simplifies deployment and ensures consistency across environments.

Technology Stack
•	Programming Language:
o	Node.js (for web servers)
•	Data Store & Messaging:
o	Redis (for request counting and log message handling)
•	Deployment Tools:
o	Docker (for creating isolated, portable services)
o	Docker Compose (for managing multiple containers)
•	Load Balancing:
o	Nginx (for distributing traffic across multiple web servers)
•	Testing Tools:
o	JMeter & Command-Line Tools (for load testing and performance benchmarking)

Architecture

![image](https://github.com/user-attachments/assets/776551f3-66bd-443d-96c6-affacb09e2d5)

Testing
Load Testing and Performance Analysis
Used JMeter and command-line testing to simulate concurrent user requests. A sample test run included:
artillery quick --count 10 --num 50 http://localhost:8080/
This test generated significant traffic, revealing an error rate of 20% under high load. The findings indicated that while the system efficiently handled 80% of requests, optimizations such as horizontal scaling and caching could further enhance performance.

![image](https://github.com/user-attachments/assets/c9124f41-f4f1-40d9-b7cd-93733bc14900)
![image](https://github.com/user-attachments/assets/24016d0e-e8ef-45b9-809b-7556237614d9)

Apache JMeter: 

![image](https://github.com/user-attachments/assets/48073ab1-861a-4b4a-8136-2a163fc1cba5)
![image](https://github.com/user-attachments/assets/2749474d-30d1-4dc1-b51d-0d8e285dc33b)
![image](https://github.com/user-attachments/assets/ac3408cc-9d1b-4bf1-9ecb-40b1f52c7ae3)

Error:

![image](https://github.com/user-attachments/assets/f91e79f3-9855-4599-82c6-374077b97c5e)

This project successfully implements a distributed CBSE result website that addresses the common challenges of scalability, reliability, and monitoring. By leveraging Nginx for load balancing and Redis for state management, the system ensures high availability and resilience under heavy loads. 
