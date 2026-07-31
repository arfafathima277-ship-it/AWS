# AWS CLI (Command Line Interface)

## What is AWS CLI?

AWS CLI (Command Line Interface) is a tool that allows users to manage AWS services directly from the terminal instead of using the AWS Management Console.

It helps automate cloud tasks and is widely used by Cloud Engineers and DevOps Engineers.

---

## Advantages

- Manage AWS services from the command line
- Automate repetitive tasks
- Create scripts for cloud operations
- Faster than using the AWS Console
- Supports multiple AWS services

---

## Install AWS CLI

### Windows

Download and install the AWS CLI installer from the AWS website.

### Linux

```bash
sudo apt update
sudo apt install awscli
```

---

## Verify Installation

```bash
aws --version
```

Example:

```text
aws-cli/2.x.x Python/3.x
```

---

## Configure AWS CLI

```bash
aws configure
```

You'll be asked to enter:

- AWS Access Key ID
- AWS Secret Access Key
- Default Region
- Output Format

---

## Common AWS CLI Commands

Check version

```bash
aws --version
```

List S3 Buckets

```bash
aws s3 ls
```

Copy file to S3

```bash
aws s3 cp file.txt s3://bucket-name/
```

Sync local folder with S3

```bash
aws s3 sync . s3://bucket-name
```

List EC2 Instances

```bash
aws ec2 describe-instances
```

---

## Benefits of AWS CLI

- Easy automation
- Faster cloud management
- Supports scripting
- Ideal for CI/CD pipelines
- Used extensively in DevOps

---

# Interview Questions

1. What is AWS CLI?
2. Why is AWS CLI used?
3. How do you configure AWS CLI?
4. Which command checks the AWS CLI version?
5. What is the difference between AWS CLI and the AWS Management Console?
