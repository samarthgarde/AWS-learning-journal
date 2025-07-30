# 🔐 Virtual Private Cloud - VPC

We need to understand the main concepts of the resources of VPC

- [VPC](#vpc)
- [Subnets](#subnets)
- [Internet Gateway](#internet-gateway)
- [NAT Gateway](#nat-gateway)
- [Network ACL (NACL)](#network-acl)
- [Security Groups](#security-groups)
- [VPC Flow Logs](#vpc-flow-logs)
- [VPC Peering](#vpc-peering)
- [VPC Endpoints](#vpc-endpoints)
- [Site to Site VPN](#site-to-site-vpn) (vpn and goes to public internet)
- [Summary](#summary)

## VPC

VPC stands to Virtual Private Cloud and it is a private network to deploy your resources (regional resource). 

## Subnets

Subnets are partition of our network and is associated to an Availability Zone

- **Public Subnet**: Is a subnet accessible for the internet (we can put, for example, an EC2 Instance). It requires an internet gateway.
- **Private Subnet**: Is a subnet not accessible for the internet (we can put, for example, a database). Our private subnet can have access to the internet by using the NAT Gateway.

To define access to the internet and communication between subnets, we use route tables.

## Internet Gateway

Inside each subnet we can have EC2 instances, For this instances be accessible to the internet, we need to use the Internet Gateway. The internet gateway create a way to our Subnet connect to the internet.

The public subnet will have a route to the internet gateway that is communicating with the internet. As soon we have the internet gateway and a route to it, that makes the subnet a **public subnet**. It is defined at VPC Level.

## NAT Gateway

Works with the **Private Subnet**. By default private subnet does not have access to the internet and cannot be accessed through the internet as well. But if we need to access the internet (for updates to softwares, or something similar) we can use the NAT Gateway.

NAT Gateway is a AWS-Managed service to allow private subnet access the internet while remaining private.

The NAT Gateway need to be created inside the Public Subnet and we create a Route from our Private Subnet to this NAT Gateway and it will be able to get internet connectivity.

## Network ACL

When we are inside the Subnet we have a protection called Network ACL (NACL or Network Access Level).

- NACL is a firewall (Subnet Level) which controls traffic from and to subnet.
- NACL can have ALLOW and DENY rules
- NACL is stateless, this means, the return traffic must be explicitly allowed by rules.
- A NACL contains a numbered list of rules and evaluates these rules in the increasing order while deciding whether to allow the traffic.
- Automatically applies to all instances in the subnets that it's associated with
- The rules include only IP Addresses

## Security Groups

Security Groups are Firewall specific firewall that controls traffic to and from an ENI (Elastic Network Interface) and/or EC2 Instances.

- Can have only ALLOW rules
- Operates at the instance level
- Rules include IP Addresses and other security groups
- Security Groups are Stateful, this means the Return traffic is automatically allowed, regardless of any rules.
- Security Groups evaluate all rules before deciding whether to allow traffic.
- Control of inbound network (from outside to inside the instance)
- Control of outbound network (from instance to outside) - by default, all traffic outbound (from our instance to the rest of the world) is allowed.

## NACL vs Security Groups

The main differences are

Security Group: Operates at instance level, support only allow rules, is stateful (return traffic is automatically allowed, regardless any rules)

NACL: Operates at the subnet level, allow and deny rules, is stateless (return traffic must be explicitly allowed by the rules)

for more details [visit amazon page](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Security.html)

## VPC Flow Logs

VPC Flow logs captures all logs from all network interfaces, so we have:

- VPC Flow logs
- Subnet Flow logs
- Elastic Network Interface Flow logs
- It also captures network information from AWS managed interfaces into the services: Load Balancers, ElastiCache, RDS, Aurora, etc.

With this logs we can monitor and troubleshoot connectivity issues such as: Subnet to the internet, subnet to subnet, internet to subnet.

We can export our logs to S3 Bucket and/or CloudWatch Logs as well.

## VPC Peering

With VPC Peering we can connect two VPCs, privately using AWS Network and make them behave as if they are in the same network.

> A VPC peering connection is a networking connection between two VPCs that enables you to route traffic between them privately. Instances in either VPC can communicate with each other as if they are within the same network. You can create a VPC peering connection between your VPCs, with a VPC in another AWS account, or with a VPC in a different AWS Region.

- This must not overlap CIDR (IP ranges)
- VPC peering is not transitive, this means if we have 3 VPCs, A, B and C, Then we create a VPC peering from A to B, And we create another VPC peering from B to C.

## VPC Endpoints

Usually when we connect our services we use the public internet, but we have private subnets, there is no reason to make them communicate between the public internet. For example, an EC2 instance inside a private subnet needs to communicate with S3 or Dynamo. We can use the internal AWS network. For this we need to create an VPC Endpoint.

VPC Endpoints allows us to connect to AWS services using a private network instead of the public. We have two types of Endpoints. This gives you enhanced security and lower latency to access AWS services.

> VPC endpoint enables you to privately connect your VPC to supported AWS services and VPC endpoint services powered by AWS PrivateLink without requiring an internet gateway, NAT device, VPN connection, or AWS Direct Connect connection.

**VPC Endpoint Gateway**: Dynamo and S3

- A gateway endpoint is a gateway that you specify as a target for a route in your route table for traffic destined to a supported AWS service.
  **VPC Endpoint Interface**: All others AWS services
- An interface endpoint is an elastic network interface with a private IP address from the IP address range of your subnet that serves as an entry point for traffic destined to a supported service. Interface endpoints are powered by AWS PrivateLink, a technology that enables you to privately access services by using private IP addresses.

## Site to Site VPN

> AWS Site-to-Site VPN creates a secure connection between your data center or branch office and your AWS cloud resources. This connection goes over the public internet. Site to Site VPN cannot be used to interconnect VPCs.

## Summary

- VPC Structure:
  - VPC: Virtual Private Cloud
  - Subnets: It is tied to an AZ, is a partition of VPC (can be private or public)
- VPC Connectivity:
  - Internet Gateway: at VPC level, allow internet access
  - NAT Gateway: at the public subnet level, to allow access to the internet for the private one.
- VPC Security:
  - Network ACL (NACL): At subnet level, it is a firewall, Stateless, subnet rules for inbound and outbound
  - Security Groups: at instance level, it is a firewall, stateful. subnet rules (only allow rules) for inbound and outbound
  - VPC Flow Logs: Enable logs to all network interfaces of all internet traffic.
- Connect multiple VPCs:
  - VPC Peering: Connect two VPC with non overlapping IP ranges, intransitive
  - VPC Endpoints: For private subnets, Provide private access to AWS Services within VPC (Interface and Gateway [S3 and Dynamo])
- (VPN) Connect VPC with On Premise
  - Site to Site VPN: connect on premises server with our vpc, through VPN using the public internet.
  - Direct Connect: connect on premises server with our vpc, though VPN, using a private connection (needs physical devices)
  - Transit Gateway: Connect thousands of VPCs and on premise servers using a central hub to manage traffic and peering.

[UP](#-virtual-private-cloud---vpc)
