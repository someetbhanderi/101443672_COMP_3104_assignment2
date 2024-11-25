COMP3104 Assignment 2 - VM1 Setup
Overview
This document outlines the setup process for Virtual Machine 1 (VM1) as part of COMP3104 Assignment 2. The VM is configured with the following tools:

Java
Jenkins
Docker
Git
Steps Performed
1. Java Installation
Java was installed using the following commands:
sudo apt update
sudo apt install openjdk-17-jdk -y
java -version
openjdk version "17.0.x"
2. Jenkins Installation
Jenkins was installed and started using the following steps:
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt update
sudo apt install jenkins -y
sudo systemctl start jenkins
sudo systemctl enable jenkins
The Jenkins dashboard is accessible via the public IP address on port 8080.

3. Docker Installation
Docker was installed using the following commands:
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
docker --version
Docker version 20.x
4. Git Installation and Configuration
Git was installed and configured using the following commands:
sudo apt install git -y
git config --global user.name "Someet Bhanderi"
git config --global user.email "101443672@georgebrown.ca"
Screenshots
Screenshots have been taken to verify:
Jenkins dashboard access.
Java, Docker, and Git version outputs.




# COMP3104 Assignment 2 - Virtual Machine 2

## Virtual Machine Details:
- **Name:** A2VM2
- **OS:** Ubuntu 22.04 LTS
- **Purpose:** Host PostgreSQL database serve

---

## Steps Performed:

### 1. VM Creation:
- **Created an Ubuntu 22.04 LTS Virtual Machine** in Azure.
- Configured the necessary inbound port rules for SSH (22).

---

### 2. PostgreSQL Installation:
- **Commands executed:**
  ```bash
  sudo apt update
  sudo apt install postgresql postgresql-contrib -y
Verify PostgreSQL Service:
sudo systemctl status postgresql
PostgreSQL is active and running.

3. PostgreSQL Database Setup:
Logged in as the postgres user:
sudo -i -u postgres
psql
Created a new database for SonarQube:
CREATE DATABASE sonar;
Granted privileges to the sonar database:
CREATE USER sonar WITH ENCRYPTED PASSWORD 'sonar';
GRANT ALL PRIVILEGES ON DATABASE sonar TO sonar;

Verified Database Creation:
\l
Screenshots Captured:
VM creation completion.
SSH connection to VM2.
PostgreSQL installation and service status.
Database creation and configuration in PostgreSQL.