
# AWS IAM (Identity and Access Management)

## 1. Overview
IAM stands for Identity and Access Management. In simple words, IAM controls who can access your AWS account and what they are allowed to do.

Example in AWS

Suppose you have an AWS account with:
- EC2 (your server)
- S3 (file storage)
- RDS (database)

You have three people:

Person	Permission
You (Owner)	Full access
Developer	Access to EC2 only
Accountant	View billing only


IAM permission:

![Permissions](./images/permissions.png)


## 2. Core Concepts
- IAM Users: Who is accessing AWS?
- IAM Groups: Which team does the user belong to?
- IAM Roles: What can they do?
- IAM Policies: What temporary permissions can an identity assume?

Let's understand some of them:
Role	Purpose
AccountFullAccessRole	Provides full account access to a trusted entity
AWSManagedAccountManagementAccessRole	Supports AWS account management
AWSServiceRoleFor...	Allows specific AWS services to perform their required operations

The roles starting with AWSServiceRoleFor are generally service-linked roles. AWS creates these to allow its services to operate on your behalf.

A policy is like a permission document attached to an identity.

For example:
EC2ReadOnlyPolicy
       |
       | Allows
       |
View EC2 instances
View instance details
View security groups
       |
       X
Cannot create or delete instances