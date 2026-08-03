# AWS Infrastructure Deployment Lab

## Project Overview

The **AWS Infrastructure Deployment Lab** demonstrates the design and deployment of a secure cloud infrastructure using Amazon Web Services (AWS). The project involved building a custom Virtual Private Cloud (VPC), configuring networking components, deploying an Amazon EC2 web server, implementing network security, and monitoring the environment with Amazon CloudWatch.

The objective was to simulate a small production environment while applying AWS best practices for networking, compute, security, and monitoring.

---

## Business Problem

Organizations moving workloads to the cloud require infrastructure that is secure, scalable, and cost-effective. Traditional on-premises deployments require purchasing hardware, configuring physical networking, and maintaining servers throughout their lifecycle.

Cloud infrastructure allows organizations to provision resources in minutes while reducing operational overhead and improving scalability.

This project demonstrates how core AWS networking, compute, and monitoring services work together to build a secure cloud environment suitable for hosting production workloads.

---

## Technical Solution

### Networking

A custom Amazon VPC was created using the **10.0.0.0/16** CIDR block.

The network was divided into:

- Public Subnet (`10.0.1.0/24`)
- Private Subnet (`10.0.2.0/24`)

An Internet Gateway was attached to the VPC to provide Internet connectivity for resources located in the public subnet.

Separate public and private route tables were configured to properly route traffic while isolating private resources from direct Internet access.

---

### Security

A custom Security Group was created for the EC2 web server.

Inbound rules included:

- SSH (TCP 22) from my public IP
- HTTP (TCP 80)
- HTTPS (TCP 443)
- ICMP (optional for testing)

Outbound traffic remained unrestricted using AWS default outbound rules.

---

### Compute

An Amazon EC2 instance running **Amazon Linux 2023** was deployed within the public subnet.

After deployment, I:

- Connected using EC2 Instance Connect
- Updated the operating system
- Installed Apache HTTP Server
- Enabled and started the Apache service
- Created a test webpage
- Verified the web server using its public IP address

---

### Monitoring

Amazon CloudWatch was configured to monitor the deployed infrastructure.

This included:

- Installing the CloudWatch Agent
- Creating a CloudWatch Dashboard
- Monitoring CPU utilization
- Monitoring Network In/Out
- Monitoring Disk Read/Write operations
- Creating a CloudWatch Alarm for CPU utilization above 70%
- Testing the alarm using the Linux `stress` utility

---

## Technologies Used

### Cloud Platform

- Amazon Web Services (AWS)

### Networking

- Amazon VPC
- Public Subnets
- Private Subnets
- Internet Gateway
- Route Tables

### Compute

- Amazon EC2
- Amazon Linux 2023

### Security

- Security Groups
- SSH
- HTTP
- HTTPS

### Monitoring

- Amazon CloudWatch
- CloudWatch Agent
- CloudWatch Dashboard
- CloudWatch Alarms

### Web Server

- Apache HTTP Server (httpd)

### Operating System

- Linux

---

## Skills Demonstrated

- AWS networking design
- Virtual Private Cloud (VPC) configuration
- Public and private subnet deployment
- Route table configuration
- Internet Gateway configuration
- Security Group implementation
- Amazon EC2 deployment
- Linux administration
- Apache web server installation
- CloudWatch monitoring
- CloudWatch alarms
- Infrastructure troubleshooting

---

## Project Architecture
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/d567bf02-457a-4d68-bf8f-9849abc207db" />



---

### Infrastructure

VPC Overview
<img width="1249" height="575" alt="VPC Overview" src="https://github.com/user-attachments/assets/d96095ff-592c-4adc-ba2b-0dc434bbba5d" />

Internet Gateway attached to the VPC
<img width="1228" height="230" alt="Internet Gateway attached to the VPC" src="https://github.com/user-attachments/assets/340a1a4d-3cd7-4253-b2da-caa0825016d4" />

Public Subnet
<img width="1225" height="563" alt="Public Subnet" src="https://github.com/user-attachments/assets/818f57fa-b5cb-4418-acee-ea7ed450345a" />

Private Subnet
<img width="1228" height="556" alt="Private Subnet" src="https://github.com/user-attachments/assets/ae482923-ac34-4e98-b35b-fa0f3332b4be" />

Public Route Table
<img width="1226" height="349" alt="Public Route Table" src="https://github.com/user-attachments/assets/c4e5f942-6bb8-4614-9ad5-0661f073391e" />

Private Route Table
<img width="1222" height="326" alt="Private Route Table" src="https://github.com/user-attachments/assets/d42de0ef-2ecd-4d01-aa11-424f78a16d06" />


### Security

Security Group configuration with Inbound Rules
<img width="1228" height="414" alt="Security Group with Inbound Rules" src="https://github.com/user-attachments/assets/a6416913-9902-4b78-85dd-ecbd54adec93" />


### Compute

EC2 Instance details with Networking Configuration
<img width="1219" height="791" alt="EC2 Instance Details" src="https://github.com/user-attachments/assets/5c892bb4-2554-4221-92c5-b5efffda30d6" />

EC2 Instance Connect session
n/
<img width="476" height="194" alt="SSH Session Connected to EC2 Instance" src="https://github.com/user-attachments/assets/9a9bd67d-81b1-48e1-9e88-5de69db6dfdb" />

### Web Server
Browser displaying the deployed website confirming Apache Service running
<img width="1901" height="684" alt="Apache Test Webpage in a Browser" src="https://github.com/user-attachments/assets/32256101-7c34-4b20-8477-fd957bcbc65f" />

### Monitoring

CloudWatch Dashboard
<img width="1897" height="504" alt="CloudWatch Dashboard" src="https://github.com/user-attachments/assets/deb69545-c2ae-4386-8d16-9b4a254754d0" />

CloudWatch CPU Alarm showing alarm was triggered
<img width="1699" height="828" alt="CloudWatch Alarm" src="https://github.com/user-attachments/assets/7e0c2ecc-d587-4b5d-ab05-204c4bfea367" />

---

## Lessons Learned

This project strengthened my understanding of AWS networking, security, compute, and monitoring.

### Key Takeaways

- Designing isolated cloud networks using Amazon VPC
- Separating public and private resources
- Configuring Internet Gateways and Route Tables
- Implementing Security Groups using least-privilege principles
- Deploying Linux servers on Amazon EC2
- Installing and managing Apache web services
- Monitoring infrastructure health with CloudWatch
- Creating dashboards and automated alerts
- Troubleshooting cloud infrastructure

---

## Future Improvements

Potential enhancements include:

- Deploying multiple EC2 instances behind an Application Load Balancer
- Implementing Auto Scaling Groups
- Adding a NAT Gateway for private subnet Internet access
- Managing infrastructure with Terraform or AWS CloudFormation
- Integrating IAM Roles for EC2
- Configuring AWS Systems Manager Session Manager
- Deploying Amazon RDS for a multi-tier architecture
- Adding AWS WAF and AWS Shield
- Implementing CI/CD using GitHub Actions and AWS CodePipeline

---

## Project Outcome

This project demonstrates practical experience designing and deploying AWS infrastructure using core AWS services. By building a secure VPC, deploying an EC2-hosted web server, implementing network security, and configuring CloudWatch monitoring and alerting, I gained hands-on experience with technologies commonly used in production cloud environments.

The completed lab showcases skills in:

- Cloud Networking
- Linux Administration
- Infrastructure Deployment
- AWS Security
- Monitoring and Alerting
- Cloud Operations
