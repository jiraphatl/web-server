# Web Server Setup on AWS EC2 for DTI241

This project demonstrates the steps to create and configure a web server on an AWS EC2 instance for the DTI241 study subject. It includes the setup of the server environment, configuration of the web server, and deployment of a simple website or application.

## Table of Contents

- [Overview](#overview)
- [Setup Instructions](#setup-instructions)
  - [Step 1: Launch EC2 Instance](#step-1-launch-ec2-instance)
  - [Step 2: Install Required Software](#step-2-install-required-software)
  - [Step 3: Configure the Web Server](#step-3-configure-the-web-server)
  - [Step 4: Deploy Application](#step-4-deploy-application)
- [Testing the Web Server](#testing-the-web-server)

## Overview

This project is part of the DTI241 course, which focuses on the setup and configuration of a web server in a cloud environment. Using AWS EC2, the goal is to provide students with hands-on experience in deploying and managing a web server, essential for cloud computing and web development skills.

## Setup Instructions

### Step 1: Launch EC2 Instance

1. Log into your [AWS Management Console](https://aws.amazon.com/console/).
2. Navigate to **EC2** and click **Launch Instance**.
3. Choose an appropriate Amazon Machine Image (AMI), such as **Ubuntu** 
4. Select the instance type
5. Configure the instance details and ensure it has a public IP.
6. Under **Security Groups**, open the necessary ports (e.g., HTTP 80, SSH 22).
7. Launch the instance and download your SSH key pair.

### Step 2: Install Required Software

Once your EC2 instance is running:

1. SSH into your instance using the following command:
   ```bash
   ssh -i "your-key.pem" ubuntu@your-ec2-ip
   ```
2. Update the system:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
3. Install the web server (e.g., Apache or Nginx):
   ```bash
   sudo apt install apache2 -y
   ```

### Step 3: Configure the Web Server

1. Start the Apache service:
   ```bash
   sudo systemctl start apache2
   ```
2. Enable Apache to start on boot:
   ```bash
   sudo systemctl enable apache2
   ```
3. Verify that the web server is running by accessing the EC2 public IP in your browser.

### Step 4: Deploy Application

1. Navigate to the default web server directory:
   ```bash
   cd /var/www/html
   ```
2. Upload your application files (HTML, CSS, JS) to this directory.
3. Ensure the files have the correct permissions:
   ```bash
   sudo chmod -R 755 /var/www/html
   ```

## Testing the Web Server

Once files are uploaded and the server is running, open your browser and navigate to the public IP of EC2 instance. 
