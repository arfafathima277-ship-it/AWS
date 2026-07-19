# AWS Identity and Access Management (IAM)

## What is IAM?

AWS Identity and Access Management (IAM) is a service that helps you securely manage access to AWS resources.

Using IAM, you can:

- Create users
- Create groups
- Assign permissions
- Create roles
- Enable Multi-Factor Authentication (MFA)
- Manage access securely

IAM helps follow the **Principle of Least Privilege**, meaning users are given only the permissions they need.

---

# Why IAM?

Instead of sharing the AWS Root Account with everyone, AWS recommends creating IAM users and assigning only the required permissions.

Benefits:

- Improved Security
- Controlled Access
- User Management
- Permission Management
- Audit and Monitoring

---

# IAM Components

## 1. Root User

The Root User is created automatically when an AWS account is created.

Characteristics:

- Has complete access to all AWS services
- Cannot be restricted
- Should only be used for account-level tasks
- Enable MFA for the Root User

---

## 2. IAM Users

IAM Users represent individual people or applications that need access to AWS.

Each IAM User has:

- Username
- Password (for AWS Console)
- Access Keys (for CLI/SDK)
- Assigned Permissions

Example:

- Developer
- DevOps Engineer
- Tester

---

## 3. IAM Groups

IAM Groups are collections of IAM Users.

Instead of assigning permissions to every user individually, permissions are assigned to the group.

Example:

### Developers Group

Permissions:

- EC2 Full Access
- S3 Read Only

Users:

- Arfa
- Ahmed
- Rahul

---

## 4. IAM Policies

Policies are JSON documents that define permissions.

A policy specifies:

- Which service can be accessed
- Which actions are allowed
- Which resources can be used

Example:

- AmazonS3ReadOnlyAccess
- AmazonEC2FullAccess
- AdministratorAccess

---

## 5. IAM Roles

IAM Roles provide temporary permissions without requiring long-term credentials.

Common Use Cases:

- EC2 accessing S3
- Lambda accessing DynamoDB
- Cross-account access

Unlike IAM Users, roles do not have passwords or access keys.

---

# Authentication Methods

## Password

Used to log in to the AWS Management Console.

---

## Access Keys

Used for:

- AWS CLI
- AWS SDK
- Automation Scripts

Access Keys consist of:

- Access Key ID
- Secret Access Key

> Never share or commit access keys to GitHub.

---

## Multi-Factor Authentication (MFA)

MFA adds an additional layer of security.

Examples:

- Authenticator App
- Hardware Token

AWS strongly recommends enabling MFA for both Root and IAM Users.

---

# Password Policy

IAM allows administrators to enforce password policies.

Example:

- Minimum password length
- Uppercase letters
- Lowercase letters
- Numbers
- Special characters
- Password expiration

---

# IAM Best Practices

- Never use the Root User for daily work.
- Enable MFA for the Root User.
- Create separate IAM Users for each person.
- Assign permissions using Groups instead of individual users.
- Follow the Principle of Least Privilege.
- Rotate Access Keys regularly.
- Never share AWS credentials.
- Delete unused IAM Users and Access Keys.

---

# Practical Performed

## Practical 1: Created IAM Users

Performed the following steps:

1. Opened AWS Console.
2. Navigated to IAM.
3. Selected **Users**.
4. Clicked **Create User**.
5. Entered a username.
6. Granted console access.
7. Assigned permissions.
8. Created the IAM User.

---

## Practical 2: Created IAM Groups

Steps:

1. Opened IAM.
2. Selected **User Groups**.
3. Created a new group.
4. Attached AWS managed policies.
5. Added IAM Users to the group.

---

## Practical 3: Attached Policies

Attached AWS managed policies such as:

- AdministratorAccess
- AmazonEC2FullAccess
- AmazonS3ReadOnlyAccess

---

## Practical 4: Logged in as IAM User

Verified:

- Console login
- User permissions
- Access based on assigned policies

---

## Practical 5: Created Access Keys

Generated Access Keys for CLI access.

Verified the keys can be used with:

```bash
aws configure
```

---

# Difference Between IAM User and IAM Role

| IAM User | IAM Role |
|----------|----------|
| Represents a person or application | Represents a set of temporary permissions |
| Has password and access keys | No permanent credentials |
| Long-term identity | Temporary identity |
| Used by humans | Used by AWS Services |

---

# Difference Between IAM User and Root User

| Root User | IAM User |
|-----------|----------|
| Full AWS account access | Limited permissions |
| Cannot be restricted | Permissions controlled by policies |
| Created automatically | Created manually |
| One per account | Multiple users allowed |

---

# Interview Questions

## What is IAM?

IAM is an AWS service used to securely manage users, permissions, and access to AWS resources.

---

## Why should we avoid using the Root User?

The Root User has unrestricted access to the AWS account. For security, AWS recommends using IAM Users for everyday tasks.

---

## What is an IAM Policy?

An IAM Policy is a JSON document that defines what actions are allowed or denied on AWS resources.

---

## What is the difference between IAM Users and IAM Groups?

IAM Users are individual identities, while IAM Groups are collections of users that share the same permissions.

---

## What are IAM Roles?

IAM Roles provide temporary permissions to AWS services, users, or applications without using long-term credentials.

---

## What is MFA?

Multi-Factor Authentication adds an additional verification step to improve account security.

---

## What are Access Keys used for?

Access Keys are used to access AWS programmatically through the AWS CLI or SDKs.

---

# Commands Used

```bash
aws configure
aws iam list-users
aws iam list-groups
aws sts get-caller-identity
```

---

# Summary

- Learned AWS IAM fundamentals.
- Created IAM Users.
- Created IAM Groups.
- Attached IAM Policies.
- Logged in using an IAM User.
- Generated Access Keys.
- Configured AWS CLI.
- Understood IAM Roles and security best practices.