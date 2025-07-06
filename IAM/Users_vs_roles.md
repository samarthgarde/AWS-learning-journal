## IAM: Users vs Roles

##  Definition
IAM users represent people/services in your AWS account.
IAM roles are temporary credentials assigned to AWS services or external users.

## Use Case
- Users: Permanent access for developers/admins
- Roles: Temporary access for EC2, Lambda, federated identities

## CLI Commands

Create User:
aws iam create-user --user-name DevUser

Create Role:
aws iam create-role --role-name MyRole --assume-rol
