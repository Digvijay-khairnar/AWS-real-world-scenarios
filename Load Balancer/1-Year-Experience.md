# AWS Load Balancer Scenario-Based Interview Questions (1 Year Experience)

## Introduction

This document contains **15 real-world AWS Load Balancer scenario-based interview questions and answers** designed for candidates with **1 year of AWS/DevOps experience**.

---

# Question 1

## Scenario

Users cannot access your application through the Load Balancer. What will you check first?

## Answer

I would troubleshoot in the following order:

- Check whether the Load Balancer is in the **Active** state.
- Verify that the EC2 instances are running.
- Check the Target Group health status.
- Verify the Security Groups allow HTTP/HTTPS traffic.
- Check the Listener configuration.
- Verify that DNS is pointing to the correct Load Balancer.

### Interview Tip

Always troubleshoot from the Load Balancer to the backend application.

---

# Question 2

## Scenario

Your EC2 instances are running, but the Target Group shows them as **Unhealthy**. What could be the reason?

## Answer

Possible reasons include:

- Incorrect Health Check Path
- Application is not running
- Wrong Health Check Port
- Security Group blocks traffic from the Load Balancer
- Health Check Timeout is too low
- Incorrect Success Code

### Interview Tip

The most common reason is that the application is not responding to the configured health check path.

---

# Question 3

## Scenario

Users receive a **503 Service Unavailable** error from the Load Balancer. What could be the reason?

## Answer

A 503 error usually indicates:

- No healthy targets are available.
- Target Group is empty.
- Health checks are failing.
- Backend application has stopped.
- Incorrect Listener configuration.

### Interview Tip

Always check the Target Group health status first.

---

# Question 4

## Scenario

You launched a new EC2 instance, but it is not receiving any traffic. What will you check?

## Answer

I would verify:

- The instance is registered with the Target Group.
- The instance health status is **Healthy**.
- Security Groups allow traffic from the Load Balancer.
- The application is running.
- Listener rules forward requests to the correct Target Group.

---

# Question 5

## Scenario

How can you verify that traffic is reaching your Load Balancer?

## Answer

I would check:

- CloudWatch Metrics
- Access Logs
- Request Count
- Healthy Host Count
- Browser response
- Target response time

### Interview Tip

CloudWatch Metrics provide valuable insights into traffic and Load Balancer performance.

---

# Question 6

## Scenario

Users report that the website is very slow. How would you investigate the issue?

## Answer

I would check:

- EC2 CPU utilization
- Memory usage
- Network utilization
- Load Balancer latency
- CloudWatch Metrics
- Application logs

### Interview Tip

The issue may be caused by overloaded EC2 instances rather than the Load Balancer itself.

---

# Question 7

## Scenario

One EC2 instance becomes unhealthy. What happens?

## Answer

The Load Balancer automatically stops sending traffic to the unhealthy instance.

It continues routing traffic only to healthy instances until the unhealthy instance passes the health check again.

---

# Question 8

## Scenario

Why are Health Checks configured on a Load Balancer?

## Answer

Health Checks help determine whether backend servers are healthy.

Benefits include:

- Automatic failure detection
- High availability
- Better user experience
- No traffic to failed instances

---

# Question 9

## Scenario

Your application should support HTTPS. What changes are required?

## Answer

I would:

- Request or import an SSL certificate into AWS Certificate Manager (ACM).
- Create an HTTPS Listener on port 443.
- Attach the SSL certificate.
- Redirect HTTP traffic to HTTPS.
- Update Security Groups to allow port 443.

### Interview Tip

HTTPS ensures encrypted communication between users and the Load Balancer.

---

# Question 10

## Scenario

Users are always connected to the same EC2 instance. Why?

## Answer

This usually happens because **Sticky Sessions (Session Affinity)** are enabled.

If the application does not require session persistence, I would disable Stickiness.

---

# Question 11

## Scenario

Why do we deploy EC2 instances in multiple Availability Zones behind a Load Balancer?

## Answer

This provides High Availability.

If one Availability Zone fails, the Load Balancer automatically routes traffic to healthy instances in another Availability Zone.

### Benefits

- High Availability
- Fault Tolerance
- Improved Reliability

---

# Question 12

## Scenario

Which AWS Load Balancer would you choose for a web application?

## Answer

I would use an **Application Load Balancer (ALB)**.

Reasons:

- Supports HTTP and HTTPS
- Host-based Routing
- Path-based Routing
- WebSocket support
- Layer 7 Load Balancer

---

# Question 13

## Scenario

Which Load Balancer is suitable for TCP traffic?

## Answer

I would choose a **Network Load Balancer (NLB)**.

Reasons:

- Supports TCP
- Supports UDP
- Very high performance
- Ultra-low latency
- Layer 4 Load Balancer

---

# Question 14

## Scenario

The Load Balancer is healthy, but the website still doesn't open. What would you check?

## Answer

I would verify:

- Route 53 DNS records
- Security Groups
- Network ACLs
- EC2 application status
- Listener Rules
- Target Group
- Browser cache
- Application logs

### Interview Tip

A healthy Load Balancer does not guarantee that the backend application is functioning correctly.

---

# Question 15

## Scenario

Which logs and monitoring services would you use to troubleshoot Load Balancer issues?

## Answer

I would use:

- CloudWatch Metrics
- ALB Access Logs
- CloudTrail
- EC2 System Logs
- Application Logs
- Target Group Health Status

These tools help identify issues related to traffic, backend application performance, and infrastructure.

---

# Summary

## Topics Covered

- Load Balancer Troubleshooting
- Health Checks
- Target Groups
- Listeners
- Security Groups
- HTTPS Configuration
- SSL Certificates
- Sticky Sessions
- High Availability
- Multi-AZ Architecture
- CloudWatch Monitoring
- Access Logs
- Network Load Balancer (NLB)
- Application Load Balancer (ALB)

---

**Level:** Beginner to Intermediate (1 Year Experience)

**Recommended For:**
- AWS Cloud Engineer Interviews
- DevOps Engineer Interviews
- System Administrator Interviews
- AWS Certification Preparation