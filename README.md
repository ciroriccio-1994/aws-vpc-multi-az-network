# 🧱 AWS VPC Project – Multi-AZ with Public & Private Subnets

This project demonstrates how I designed and built a **custom VPC architecture on AWS**, manually via the AWS Management Console, as part of my **AWS Solutions Architect Associate** preparation.

The goal: show hands-on understanding of **networking fundamentals** (VPC, subnets, routing, NAT, IGW) while keeping the setup simple, cost-controlled, and easy to reproduce.

---

## 🔧 What I Built

- **Custom VPC**: 10.0.0.0/16
- **2 Availability Zones**: eu-central-1a, eu-central-1b
- **4 Subnets**:  
  - Public: `10.0.0.0/20` (AZ a) and `10.0.16.0/20` (AZ b)  
  - Private: `10.0.32.0/20` (AZ a) and `10.0.48.0/20` (AZ b)
- **Internet Gateway (IGW)**: Public subnets route traffic to the Internet.
- **NAT Gateway**: Deployed in a public subnet (with Elastic IP) to allow secure outbound traffic from private subnets.
- **Route Tables**:  
  - Public route table → `0.0.0.0/0 → IGW`
  - Two private route tables (one per AZ) → `0.0.0.0/0 → NAT`

---

## 📐 Architecture Overview

- Public subnets can host internet-facing resources (e.g., load balancers, bastion hosts).  
- Private subnets can host backend resources (databases, app servers) with secure outbound internet access via NAT.  
- Dedicated route tables ensure **isolation and controlled traffic flow**.

---

## 🖼️ Architecture Screenshot

![VPC Architecture](./vpc-project-screenshot.png)

---

## 📚 What I Learned

- How to **plan CIDR blocks** across subnets and AZs.  
- Proper configuration of **route tables for public vs. private subnets**.  
- The difference between **IGW and NAT Gateway**.  
- Why cleanup (deleting NAT/EIP) is critical to **avoid unnecessary AWS costs**.  
- Reinforced practical knowledge for the AWS Solutions Architect Associate exam.

---

## 🚀 Context

This project is part of my **AWS Cloud portfolio**: a series of small, real-world projects built while preparing for the Solutions Architect Associate certification.

I deleted the environment after testing to **avoid extra AWS charges**, keeping the focus on learning and documentation.

Follow my AWS journey on [LinkedIn](https://www.linkedin.com/in/ciro-riccio-a1a933197/).
![VPC Architecture](./vpc-project-screenshot.png)
