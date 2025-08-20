# What is IAM?
IAM is an AWS security service that controls who can access AWS resources and what they can do.

## IAM: Users vs Roles vs Groups vs Policy

##  Definition
- IAM users represent people/services in your AWS account.
- IAM roles are temporary credentials assigned to AWS services or external users.
- IAM Groups are Buckets of users with the same permissions.
- IAM Policy are JSON document that defines permission.

## Use Case
- Users: Permanent access for developers/admins
- Roles: Temporary access for EC2, Lambda, federated identities
- Groups: Manage many users together.
- Policy: Attached to Users, Groups, Roles.

## CLI Commands

Create User:
aws iam create-user --user-name DevUser

Create Role:
aws iam create-role --role-name MyRole --assume-rol

