#  EC2 User Data Scripts & AMI Notes

#S# Date: 12th July 2025

# What is EC2 User Data?

**User Data** is a shell script or cloud-init script provided when launching an EC2 instance. It runs *once at the first boot* and is used for:
- Installing software
- Setting environment variables
- Configuring applications

# Sample EC2 User Data Script (Shell Script)

```
bash
#!/bin/bash
sudo apt update -y
sudo apt install -y nginx
systemctl enable nginx
systemctl start nginx

```

# What is an AMI?
- Amazon Machine Image (AMI) is a template to launch pre-configured EC2 instances. It includes:

# Operating System

- Application server
- Software
- User configuration

# Create AMI from EC2
- Launch and configure an EC2 instance.
- Install all required software via SSH or User Data.
- Go to EC2 → Instances → Actions → Image → Create Image.
- Name your image and create it.

# Launch EC2 from Your Custom AMI
- Use the AMI ID or select from My AMIs.
- Now any new EC2 from this AMI has all pre-installed configurations.


