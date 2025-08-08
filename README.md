# Scalable Web Application with ALB and Auto Scaling

## Project Overview

This project demonstrates a highly available and scalable web application deployed on AWS using EC2 instances behind an Application Load Balancer (ALB) and managed by an Auto Scaling Group (ASG). The architecture ensures automatic scaling based on demand, distributing incoming traffic efficiently while maintaining fault tolerance. CloudWatch monitoring and SNS alerting are integrated for proactive performance management and operational visibility.

---

## Architecture Diagram

![Solution Architecture Diagram](diagrams/solution-architecture.svg)

*The diagram above illustrates the components and flow of the solution, including user requests routed via the ALB to EC2 instances managed by an ASG, with monitoring and alerting services integrated.*

---

## AWS Services Utilized

- **EC2 (Elastic Compute Cloud):** Hosts the web application on multiple instances across availability zones for fault tolerance.
- **Application Load Balancer (ALB):** Distributes incoming HTTP/HTTPS traffic evenly across EC2 instances, enabling seamless scalability and high availability.
- **Auto Scaling Group (ASG):** Automatically adjusts the number of EC2 instances based on traffic patterns and CPU utilization to optimize cost and performance.
- **CloudWatch:** Monitors system metrics like CPU usage, enabling automated scaling and health checks.
- **SNS (Simple Notification Service):** Sends alerts based on CloudWatch alarms, providing immediate notifications of performance issues or scaling events.
- **IAM (Identity and Access Management):** Provides secure, role-based access control to EC2 instances and AWS resources.

---

## Solution Details

### Scalability & High Availability

- The Auto Scaling Group ensures that the number of EC2 instances dynamically scales out during peak demand and scales in when traffic decreases, maintaining optimal performance and cost efficiency.
- Instances are deployed across multiple Availability Zones to prevent single points of failure.
- The Application Load Balancer evenly distributes incoming traffic and performs health checks, routing requests only to healthy instances.

### Security Best Practices

- EC2 instances operate under IAM roles with least privilege, granting only necessary permissions.
- Security groups restrict traffic to only allow HTTP/HTTPS from the ALB and SSH access (optional, based on use case).
- The ALB is internet-facing, providing a secure entry point without exposing individual EC2 instances.

### Monitoring and Alerts

- CloudWatch collects key performance metrics and health data.
- Alarms monitor CPU utilization and instance health, triggering Auto Scaling actions and sending notifications via SNS to administrators for rapid response.

### Cost Optimization

- Auto Scaling reduces unnecessary costs by terminating instances during low usage periods.
- Using on-demand instances and optimized scaling policies balances performance with budget constraints.

---

## Deployment and Usage

While this project focuses on the architectural design and documentation, a typical deployment involves:

1. Creating an EC2 Launch Template with the desired AMI and User Data scripts to deploy the application.
2. Setting up the Application Load Balancer.
3. Configuring the Auto Scaling Group with scaling policies linked to CloudWatch metrics.
4. Establishing CloudWatch alarms and SNS topics for monitoring and alerting.
5. Applying security groups and IAM roles to secure the environment.

---

## Learning Outcomes

- Setting up secure and scalable EC2-based web applications.
- Implementing high availability using ALB and ASG.
- Optimizing costs and performance using Auto Scaling policies.

---

## Repository Structure

```
scalable-web-app-aws/
├── diagrams
│   └── solution-architecture.png
├── README.md
├── LICENSE
```

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

*For questions or further discussion, feel free to open an issue*

