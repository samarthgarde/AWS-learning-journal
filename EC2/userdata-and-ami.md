# Ì∫Ä EC2 User Data Scripts & AMI Notes

## Ì≥Ö Date: 12th July 2025

---

## Ì¥π What is EC2 User Data?

**User Data** is a shell script or cloud-init script provided when launching an EC2 instance. It runs *once at the first boot* and is used for:
- Installing software
- Setting environment variables
- Configuring applications

---

## Ì∑™ Sample EC2 User Data Script (Shell Script)

```bash
#!/bin/bash
sudo apt update -y
sudo apt install -y nginx
systemctl enable nginx
systemctl start nginx

Ì∑ä What is an AMI?
Amazon Machine Image (AMI) is a template to launch pre-configured EC2 instances. It includes:

OS

Application server

Software

User configuration

Ì¥Ñ Create AMI from EC2
Launch and configure an EC2 instance.

Install all required software via SSH or User Data.

Go to EC2 ‚Üí Instances ‚Üí Actions ‚Üí Image ‚Üí Create Image.

Name your image and create it.

Ì¥Å Launch EC2 from Your Custom AMI
Use the AMI ID or select from My AMIs.

Now any new EC2 from this AMI has all pre-installed configurations.


