### Building Scalable and Highly Available Applications with AWS Elastic Load Balancers

#### What is an Elastic Load Balancer (ELB)?

An Elastic Load Balancer (ELB) is a managed load balancing service offered by AWS. It automatically distributes incoming application traffic across multiple targets, such as Amazon EC2 instances, in multiple Availability Zones, enhancing the fault tolerance of your applications.

**Key Components:**
- **Load Balancer:** The ELB itself, which accepts incoming traffic and routes it to the registered targets.
- **Target Group:** A logical grouping of targets, such as EC2 instances, and a protocol and port to route traffic to.
- **Target:** Resources, such as EC2 instances or IP addresses, that receive traffic from the load balancer.
- **Listener:** A process that checks for connection requests from clients and forwards them to one or more targets.
- **Availability Zones (AZs):** Data centers with redundant power, networking, and cooling.

**Types of ELBs:**
- **Application Load Balancer (ALB):** Best suited for routing HTTP/HTTPS traffic and provides advanced routing features.
- **Network Load Balancer (NLB):** Ideal for handling TCP/UDP traffic, making it suitable for gaming, IoT, and other high-throughput workloads.
- **Classic Load Balancer (CLB):** The legacy load balancer that can distribute traffic across EC2 instances, but with fewer features compared to ALB and NLB.

###Configuring an ELB

Configure an Elastic Load Balancer (ELB) to distribute traffic to multiple EC2 instances running a web application and monitor the health of the instances.

**Architecture Diagram:**  


**Steps:**

1. **Create EC2 Instances:**
    - Launch at least two EC2 instances with web server software installed (e.g., Apache, Nginx).
    - Ensure they belong to the same security group allowing traffic on the web server’s port (e.g., port 80 for HTTP).

2. **Create a Target Group:**
    - In the AWS Management Console, navigate to the EC2 service.
    - Create a target group, specifying the target type (e.g., instances) and the protocol and port (e.g., HTTP on port 80).

3. **Register EC2 Instances:**
    - Register the EC2 instances you created in the target group.

4. **Create an Application Load Balancer (ALB):**
    - In the AWS Management Console, navigate to the EC2 service.
    - Create an Application Load Balancer (ALB) and configure listeners (e.g., HTTP on port 80).

5. **Configure Listener Rules:**
    - Define listener rules to route incoming traffic to the target group.

6. **Test the ELB:**
    - Access the DNS name of your ALB in a web browser. You should see your web application.
    - Verify that traffic is distributed across EC2 instances.

7. **Health Checks:**
    - Set up health checks in the target group to monitor the health of your EC2 instances.
    - The ELB will automatically route traffic to healthy instances.

8. **Monitoring:**
    - Utilize AWS CloudWatch to monitor the performance and health of your ELB and EC2 instances.
    - Set up CloudWatch alarms for proactive monitoring.

9. **Scaling (Optional):**
    - Implement Auto Scaling to automatically adjust the number of EC2 instances based on traffic patterns.
