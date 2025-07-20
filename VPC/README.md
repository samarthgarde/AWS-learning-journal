# 🛠️   AWS Project Documentation: VPC Peering with Nginx EC2 Instances

🎯Objective:
To configure VPC Peering between two VPCs, launch EC2 instances with Nginx web servers, and verify communication using private IPs via the VPC Peering route.

### Infrastructure Setup Overview
✅ Resources Created:
| Resource               | Count | Description                               |
| ---------------------- | ----- | ----------------------------------------- |
| VPC                    | 2     | VPC-A and VPC-B                           |
| Subnets                | 2     | One subnet per VPC                        |
| Internet Gateways      | 2     | One attached to each VPC                  |
| Route Tables           | 2     | One per VPC, associated with their subnet |
| VPC Peering Connection | 1     | Between VPC-A and VPC-B                   |
| EC2 Instances          | 2     | One in each VPC with Nginx installed      |
| Security Groups        | 2     | Allow HTTP (port 80)                   

1️⃣ Create Two VPCs

VPC-A CIDR: 10.0.0.0/16

VPC-B CIDR: 10.1.0.0/16

2️⃣ Create Subnets

Subnet-A: 10.0.1.0/24 (in VPC-A)

Subnet-B: 10.1.1.0/24 (in VPC-B)

3️⃣ Create Internet Gateways

Create and attach an Internet Gateway to each VPC.

4️⃣ Create and Modify Route Tables
Create a route table for each VPC and associate it with the respective subnet.

Initially, add a route to 0.0.0.0/0 pointing to the Internet Gateway for internet access.

5️⃣ Create VPC Peering Connection

Go to VPC > Peering Connections

Click Create Peering Connection

Requester VPC: VPC-A

Accepter VPC: VPC-B

After creation, Accept the Peering Request

6️⃣ Update Route Tables for Peering

VPC-A Route Table:

Add route: 10.1.0.0/16 → Peering Connection

VPC-B Route Table:

Add route: 10.0.0.0/16 → Peering Connection

#🚀 EC2 Instance Setup

7️⃣ Launch EC2 Instances

Instance-A

AMI: Ubuntu or Amazon Linux

VPC: VPC-A

Subnet: Subnet-A

Auto-assign Public IP: Enabled

Security Group:

Allow HTTP (port 80)

Allow SSH (port 22)

User Data Script: (Installs Nginx)

#!/bin/bash

sudo apt update -y

sudo apt install nginx -y

sudo systemctl start nginx

Instance-B

Same configuration in VPC-B/Subnet-B

8️⃣ Connect to EC2 and Test

From Instance-A, use the private IP of Instance-B to test:

curl http://<Instance-B-Private-IP>

From Instance-B, test:

curl http://<Instance-A-Private-IP>

If both commands return the default Nginx page, the setup is working.
