# AWS 3-Tier Architecture Project

This project shows how to set up a *Three-Tier Architecture* on *Amazon Web Services (AWS). It involves creating a **Web Tier, **Application Tier, and **Database Tier*, using services like EC2, RDS, Load Balancers, Auto Scaling, and VPC components.

## Project Structure

The architecture is divided into three tiers:

- *Web Tier:* This hosts the user interface and handles incoming requests. It uses public EC2 instances behind a load balancer.
- *Application Tier:* This contains the application logic. It uses private EC2 instances in private subnets.
- *Database Tier:* This stores and manages data using Amazon RDS.

## Steps to Deploy

### 1. Networking Setup
- Create a VPC (CIDR: 192.0.0.0/18)
- Set up 6 subnets (2 public, 4 private)
- Configure:
  - Internet Gateway
  - 2 NAT Gateways
  - Public and Private Route Tables

### 2. EC2 Instances
- Launch a public EC2 instance (Ubuntu, t2.micro)
- Create private EC2 instances for the application layer

### 3. Target Groups & Load Balancer
- Create 2 Target Groups (public and private)
- Create an Application Load Balancer for the Web Tier

### 4. Image & Launch Template
- Create an AMI from the public EC2 instance
- Set up Launch Templates using the AMI

### 5. Auto Scaling
- Configure Auto Scaling Groups for both public and private instances

### 6. Database Setup
- Create an RDS instance with multi-AZ deployment
- Enable public access and set up the VPC and subnet group

### 7. Connection Setup
- SSH into the public EC2 instance
- Install MySQL server and test the database connection

## Tools & Technologies

- *Amazon EC2*
- *Amazon VPC*
- *Amazon RDS*
- *Application Load Balancer*
- *Auto Scaling*
- *NAT Gateway*
- *Security Groups & Route Tables*
