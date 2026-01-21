# ☁️ AWS Cloud Deployment: Resume-in-a-Box

This project focuses on the end-to-end deployment of a web application on **Amazon Web Services (AWS)**. [cite_start]It demonstrates infrastructure provisioning, Linux server administration, and cloud-native hosting practices[cite: 14, 15].

## 🏗️ Infrastructure Architecture
* [cite_start]**Cloud Provider:** Amazon Web Services (AWS)[cite: 16].
* [cite_start]**Service:** Elastic Compute Cloud (EC2)[cite: 21, 89].
* [cite_start]**Instance Type:** t3.micro[cite: 132].
* [cite_start]**Operating System:** Amazon Linux 2023[cite: 148].
* [cite_start]**Web Server:** Apache HTTP Server (httpd)[cite: 25, 92].
* [cite_start]**Public IPv4:** [http://100.53.20.251/index.html](http://100.53.20.251/index.html)[cite: 191, 192].

---

## 🚀 Deployment & Configuration Workflow

### 1. EC2 Instance Provisioning
[cite_start]The instance was launched within the AWS console, selecting the Amazon Linux AMI and a t3.micro instance type[cite: 91, 132]. 
* [cite_start]**Security Groups:** Configured to allow **Port 80 (HTTP)** for public web traffic and **Port 22 (SSH)** for administrative access[cite: 95, 168].

### 2. Server Bootstrapping (Linux/Apache)
[cite_start]Once connected via SSH[cite: 142], the following commands were executed to turn the instance into a functional web server:

```bash
# Install Apache HTTP Server
sudo yum install httpd -y

# Start and enable the service to persist through reboots
sudo systemctl start httpd
sudo systemctl enable httpd


### 3. Production Deployment via SCP
* [cite_start] **The index.html file was transferred from the local development environment to the Apache production directory (/var/www/html/) using the Secure Copy Protocol:**

```bash
scp -i CloudeLabKey.pem index.html ec2-user@100.53.20.251:/var/www/html/

```

## 🔍 Validation
[cite_start] Public Accessibility: Verified successful site loading via the Public IPv4 address.


Service Verification: Confirmed httpd.service is active and listening on Port 80.