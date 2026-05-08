# aws-saa-notes
 My AWS learning journey
# 1. LINUX FUNDAMENTALS

## Chapter 1 — Introduction to Linux

### What is Linux?

Linux is an open-source operating system used heavily in servers, cloud computing, and DevOps.

### Why Linux is Important?

* Most cloud servers run Linux
* Lightweight and fast
* Powerful terminal
* Automation friendly
* Essential for DevOps

### Linux Distributions

* Ubuntu
* CentOS
* Debian
* RedHat
* Kali Linux

---

## Chapter 2 — Linux File System

### Important Directories

| Directory | Purpose                |
| --------- | ---------------------- |
| /         | Root directory         |
| /home     | User files             |
| /etc      | Configuration files    |
| /var      | Logs and variable data |
| /bin      | Essential commands     |
| /tmp      | Temporary files        |
| /root     | Root user home         |

---

## Chapter 3 — Basic Linux Commands

### Navigation Commands

```bash
pwd
ls
ls -la
cd
```

### File Commands

```bash
touch
mkdir
rm
cp
mv
cat
nano
vim
```

### Search Commands

```bash
grep
find
locate
```

### System Commands

```bash
ps aux
top
htop
systemctl
journalctl
```

---

## Chapter 4 — File Permissions

### Permission Types

* Read (r)
* Write (w)
* Execute (x)

### Important Commands

```bash
chmod
chown
sudo
```

### Example

```bash
chmod 755 file.sh
```

---

## Chapter 5 — Users & Groups

### Commands

```bash
whoami
adduser
passwd
groups
id
```

---

## Chapter 6 — SSH

### What is SSH?

Secure way to connect remote servers.

### SSH Command

```bash
ssh -i key.pem ubuntu@public-ip
```

### Common SSH Problems

* Permission denied
* Wrong key
* Security group blocked

---

## Chapter 7 — Linux Package Management

### Ubuntu Commands

```bash
sudo apt update
sudo apt upgrade
sudo apt install nginx
```

---

# 2. NETWORKING BASICS

## IP Address

* Public IP
* Private IP

## CIDR

Example:

```text
192.168.1.0/24
```

## DNS

Converts domain names into IP addresses.

## HTTP vs HTTPS

| Protocol | Port |
| -------- | ---- |
| HTTP     | 80   |
| HTTPS    | 443  |

## Important Ports

| Service | Port |
| ------- | ---- |
| SSH     | 22   |
| HTTP    | 80   |
| HTTPS   | 443  |
| RDP     | 3389 |

## TCP vs UDP

### TCP

Reliable communication.

### UDP

Faster but less reliable.

---

# 3. AWS CLOUD FUNDAMENTALS

## Chapter 1 — Introduction to AWS

### What is AWS?

Amazon Web Services is a cloud computing platform.

### Benefits

* Scalability
* Pay as you go
* High availability
* Security

---

## Chapter 2 — AWS Global Infrastructure

### Regions

Physical geographical areas.

### Availability Zones

Separate data centers inside regions.

### Edge Locations

Used for CloudFront/CDN.

---

## Chapter 3 — IAM

### IAM Components

* Users
* Groups
* Roles
* Policies

### Best Practices

* Enable MFA
* Avoid root account usage
* Use least privilege principle

---

## Chapter 4 — EC2

### What is EC2?

Elastic Compute Cloud provides virtual servers.

### Important EC2 Concepts

* AMI
* Instance Types
* Security Groups
* Key Pairs
* EBS

### EC2 Launch Steps

1. Choose AMI
2. Choose instance type
3. Configure network
4. Add storage
5. Configure security group
6. Launch instance

### Connect EC2

```bash
ssh -i key.pem ubuntu@public-ip
```

---

## Chapter 5 — Security Groups

### Purpose

Acts like firewall for EC2.

### Common Rules

| Type  | Port |
| ----- | ---- |
| SSH   | 22   |
| HTTP  | 80   |
| HTTPS | 443  |

---

## Chapter 6 — S3

### What is S3?

Object storage service.

### Features

* Versioning
* Lifecycle rules
* Static website hosting
* Storage classes

### S3 Storage Classes

* Standard
* IA
* Glacier

---

## Chapter 7 — VPC

### Components

* VPC
* Subnet
* Route Table
* Internet Gateway
* NAT Gateway

### Public vs Private Subnet

| Public               | Private            |
| -------------------- | ------------------ |
| Has internet access  | No direct internet |
| Used for web servers | Used for databases |

---

## Chapter 8 — RDS

### What is RDS?

Managed relational database service.

### Supported Databases

* MySQL
* PostgreSQL
* MariaDB

---

## Chapter 9 — Load Balancer

### Purpose

Distributes traffic across servers.

---

## Chapter 10 — Auto Scaling

### Purpose

Automatically adds/removes EC2 instances based on traffic.

---

## Chapter 11 — CloudWatch

### Purpose

Monitoring and logging service.

---

# 4. GIT & GITHUB

## What is Git?

Version control system.

## What is GitHub?

Platform to host Git repositories.

---

## Important Commands

```bash
git init
git clone
git add .
git commit -m "message"
git push
git pull
git branch
```

---

## Git Workflow

1. Create repo
2. Add files
3. Commit changes
4. Push to GitHub

---

# 5. DOCKER BASICS

## What is Docker?

Containerization platform.

## Containers vs Virtual Machines

| Containers      | VMs         |
| --------------- | ----------- |
| Lightweight     | Heavy       |
| Faster          | Slower      |
| Share OS kernel | Separate OS |

---

## Docker Important Commands

```bash
docker ps
docker images
docker run
docker exec
docker stop
docker rm
```

---

## Dockerfile Example

```dockerfile
FROM ubuntu
RUN apt update
CMD ["echo", "Hello Docker"]
```

---

# 6. PROJECTS & LABS

## Project 1 — EC2 Linux Server Setup

### Goal

Deploy Linux EC2 instance and connect via SSH.

### Services Used

* EC2
* Security Groups
* SSH

### Commands

```bash
sudo apt update
sudo apt install nginx
systemctl status nginx
```

### Problems Faced

* SSH connection issue
* Port blocked

### Solutions

* Allowed port 22 in security group
* Fixed key permissions

---

## Project 2 — S3 Static Website Hosting

### Goal

Host static website using S3.

### Services Used

* S3
* Bucket Policy

---

## Project 3 — Docker Container Lab

### Goal

Run Docker container locally.

### Commands

```bash
docker run ubuntu
```

---

# 7. COMMANDS CHEAT SHEET

## Linux

```bash
pwd
ls -la
cd
chmod
chown
grep
find
systemctl
```

## AWS CLI

```bash
aws configure
aws s3 ls
aws ec2 describe-instances
```

## Git

```bash
git status
git add .
git commit -m "update"
```

## Docker

```bash
docker ps
docker images
```

---

# 8. REVISION PAGES

## Important AWS Services

* IAM
* EC2
* S3
* VPC
* RDS
* CloudWatch

## Important Linux Topics

* Permissions
* SSH
* Processes
* File system

## Important Networking Topics

* IP Address
* DNS
* Ports
* HTTP/HTTPS

---

# GITHUB STRUCTURE RECOMMENDATION

Create these repositories:

## Recommended Repositories

1. linux-notes
2. aws-saa-notes
3. networking-basics
4. docker-learning
5. cloud-projects
6. git-github-notes

---

# README FORMAT FOR GITHUB

## Example README

```markdown
# AWS SAA Notes

These are my handwritten + practical AWS notes while preparing for AWS Certified Solutions Architect Associate.

## Topics Covered
- IAM
- EC2
- S3
- VPC
- RDS
- CloudWatch

## Goal
Building practical cloud engineering skills.
```

---

# IMPORTANT IMPROVEMENTS NEEDED FROM YOUR CURRENT NOTES

## Things You Did Well

* Good effort
* Concept mapping
* AWS architecture understanding
* EC2 notes
* Service comparisons
* Diagrams

## Things To Improve

* Cleaner headings
* Separate Linux from AWS
* Commands in separate boxes
* Better spacing
* Consistent structure
* Add practical examples
* Add troubleshooting section

---

# FINAL STUDY PRIORITY

## Highest Priority

1. Linux
2. IAM
3. EC2
4. SSH
5. Networking Basics
6. GitHub

## Medium Priority

* S3
* Docker
* AWS CLI

## Later

* Terraform
* CI/CD
* Kubernetes

---

    