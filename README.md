# Project Titan: Multi-Tier AWS Cloud & Network Infrastructure

A hands-on cloud engineering project focused on designing, provisioning, and securing a production-ready multi-tier architecture on Amazon Web Services (AWS). This repository documents the infrastructure setup, network segmentation, compute deployment, database integration, and serverless API implementation.

---

## 🏗️ Architecture Overview

The project simulates a secure 3-tier web application architecture deployed within a dedicated Virtual Private Cloud (VPC), ensuring strict isolation between public-facing components and backend resources.

[ Internet ]
│
▼
[ Internet Gateway (IGW) ]
│
▼
[ Public Subnet: Custom VPC (titan-vpc) ]
│
├──> [ EC2 Linux Web Server (titan-web-server) ]
│
└──> [ API Gateway & AWS Lambda (titan-api-function) ]
│
▼
[ Private/Isolated Tier ]
└──> [ Amazon RDS MySQL Database (titan-db) ]


---

## 🛠️ Components & Implementation Details

### 1. Networking (`titan-vpc`)
* **Custom VPC:** Created an isolated virtual network with a clean CIDR block layout.
* **Internet Gateway (IGW):** Attached to the VPC to enable controlled inbound and outbound internet traffic.
* **Route Tables & Subnets:** Configured custom route tables to direct traffic between public subnets and the internet gateway, establishing the core networking foundation.

### 2. Compute Tier (`titan-web-server`)
* **Amazon EC2:** Launched a Linux-based virtual machine instance to serve as the application/web layer.
* **Security Groups:** Applied strict firewall rules allowing inbound SSH (Port 22) for management and HTTP (Port 80) for web traffic.

### 3. Database Tier (`titan-db`)
* **Amazon RDS (MySQL):** Provisioned a managed relational database instance configured for secure data storage.
* **Connectivity & Security:** Restricted database access to internal VPC components via dedicated DB security groups to protect sensitive data layers.

### 4. Serverless API Integration (`titan-api-function`)
* **AWS Lambda:** Developed a lightweight serverless function to handle dynamic backend requests.
* **Amazon API Gateway:** Configured an HTTP endpoint trigger mapped directly to the Lambda function, allowing external clients to query the service and receive live JSON/text responses (`"Hello from Project Titan Lambda & API Gateway!"`).

---

## 📸 Architecture & Verification Screenshots

*(Place your 8 collected screenshots inside an `/assets` folder in this repository and reference them below)*

1. **VPC Configuration:** `assets/1-vpc-setup.png`
2. **Subnet & Route Tables:** `assets/2-subnets-routes.png`
3. **EC2 Instance Status:** `assets/3-ec2-running.png`
4. **RDS Database Status:** `assets/4-rds-available.png`
5. **Security Groups:** `assets/5-security-groups.png`
6. **Lambda Function Code:** `assets/6-lambda-function.png`
7. **API Gateway Trigger:** `assets/7-api-gateway.png`
8. **Live API Output:** `assets/8-api-response.png`

---

## 🚀 Key Takeaways & Skills Demonstrated
* **Cloud Infrastructure as Code / Manual Provisioning:** Deep understanding of core AWS networking and compute primitives.
* **Security Best Practices:** Implementing least-privilege security groups and subnet isolation.
* **Serverless Architecture:** Building cost-effective APIs using Lambda and API Gateway without managing underlying servers.
