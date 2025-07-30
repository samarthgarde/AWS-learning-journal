# 📝EC2 - Elastic Cloud Compute
EC2 stands to Elastic Compute Cloud and is a service where you can rent virtual servers from AWS. This Cloud Computing is from Infrastructure as a Service (IaaS) type.

## Amazon Machine Image
AMIs stands to Amazon Machine Image and are a customization of an EC2 Instance.

## EC2 Instance Types
**AWS has the following naming convention**: m5.2xlarge

- m: instance class
- 5: generation of the instance (AWS improve them over time)
- 2xlarge: the size of the instance. (Memory, CPU, etc... )

**There are a few instance types:**
- General Purpose
- Compute Optimized
- Memory Optimized
- Storage Optimized

## EC2 Security Groups
- They are fundamental of network security in AWS. They control how traffic is allowed into our EC2 instances. It is the Firewall of the instance.
- They contain only Allow rules
- Reference by IP or by other Security Group

- Common Ports that we need to know:
```
22 - SSH (Secure Shell) - log into EC2 Linux instance
22 - SFTP - (Secure File Transport Protocol) - upload file using SSH
21 - FTP (File Transfer Protocol) - upload files into a file share
80 - HTTP - access unsecured websites
443 - HTTPS - access secured websites
3389 - RDP (Remote Desktop Protocol) - Log into a windows instance
```
## EC2 SSH and Instance Connect
- SSH is one of the most important function. It allows you to control a remote machine, uptade, and lots of configurations, all using the command line.
- Mac, Linux and Win 10+ = SSH and Windows <10 = Putty
```
check permissions on .pem file (must be chmod 0400)
 and then log using ssh:

ssh -i permissionsFile.pem ec2-user@ec2-public-ip
```
- Remember to Allow port 22 in Security Group.

## Difference between Dedicated Hosts and EC2 Dedicated Instances
- Both allow you to use dedicated server, but in the EC2 Dedicated Hosts you pay for each Host and can have more access to the hardware it is much more flexible and is recommended when you have server bound licenses, while in EC2 Dedicated Instances you pay for each instance and cannot have access to hardware.

## EC2 Shared Responsibility Model

**AWS Responsibility**
- Infrastructure (global network security)
- Isolation of physical hosts

**User Responsibility**
- Security Groups rules
- Operating System patches and updates

**Shared Responsibility**
