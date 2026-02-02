# AWS EC2 Basics

## Types of EC2 Instances

Amazon EC2 provides different instance families optimized for specific workloads:

### 1. General Purpose
- Balanced CPU, memory, and networking
- Suitable for web servers, small databases, and development/testing
- Examples: `t3`, `t4g`, `m5`

### 2. Compute Optimized
- High-performance processors
- Used for CPU-intensive workloads like batch processing and gaming servers
- Examples: `c5`, `c6g`

### 3. Memory Optimized
- Designed for memory-intensive applications
- Best for in-memory databases and real-time analytics
- Examples: `r5`, `x1`, `z1d`

### 4. Storage Optimized
- High disk throughput and low latency
- Used for data warehousing, log processing, and NoSQL databases
- Examples: `i3`, `d2`

### 5. Accelerated Computing
- Uses hardware accelerators such as GPU or FPGA
- Ideal for machine learning, AI, graphics rendering, and scientific workloads
- Examples: `p3`, `g4`, `inf1`

---

## Login to EC2 Instance via Terminal

Use the following command to connect to an Ubuntu EC2 instance:

```bash
ssh -i aws.pem ubuntu@12.3.4.5

aws.pem → Private key file

ubuntu → Default username for Ubuntu AMI

12.3.4.5 → Public IP address of the EC2 instance

Permission Denied Issue (Private Key)

If you see an error like:

Permissions are too open


This occurs because the private key file has excessive permissions.

Fix the Permission
chmod 600 aws.pem

What this does:

Owner: read and write permission

Group: no permission

Others: no permission

SSH requires strict permissions on private key files for security reasons.

✅ After updating permissions, retry the SSH command and the connection should succeed.

