# Step-by-Step WordPress Deployment on AWS EC2 instance.

## Introduction

This project is a step-by-step guide to setting up and running a WordPress website on a server. It uses Apache as the web server and MariaDB as the database. The guide covers everything from preparing the server, installing the needed software, setting up WordPress, and finally making the website live on the internet. By following it, you can create a secure, reliable, and ready-to-use WordPress site.

## Requirements

Before deploying the WordPress website, ensure the following are installed and configured:

Linux Server – Amazon Linux.

Web Server – Apache installed and running.

PHP – Along with required PHP extensions.

Database – MariaDB for storing WordPress data.

## Steps for Deployment

### Step 1: Launch EC2 instance and Establishing a secure connection to your EC2 instance

1. Launch instance 

![w1](./images/w1.png)


2. Copy the SSH command

![w2](./images/w2.png)

3. Paste command in Git bash 

![w3](./images/w3.png)

### Step 2: Automating LAMP Stack Setup on AWS EC2

1. Create a LAMP.sh file

    sudo vim LAMP.sh

![w4](./images/w4.png)

2. Insert the code for installing apache, mysql and php

    sudo yum update

    sudo yum install httpd mariadb105-server php -y

    sudo systemctl start httpd mariadb php-fpm

    sudo systemctl enable httpd mariadb php-fpm

![w5](./images/w5.png)

3. Run the file 

![w6](./images/w6.png)

### Step 3: Download and Configure WordPress

#Download WordPress

sudo wget https://wordpress.org/latest.tar.gz

#Extract the archive

sudo tar -xvzf latest.tar.gz

![w7](./images/w7.png)

### Step 4: Remove latest.tar.gz

sudo rm -rf latest.tar.gz

ls

![w8](./images/w8.png)
### Step 5: Go to the wordpress folder

cd wordpress/

![w9](./images/w9.png)

### Step 6: Create WordPress Database

1. Generate the username and password.

     sudo mysql

     alter user root@localhost identified by 'root';

![w10](./images/w10.png)


2. Login to Mysql (mariadb105-server)

     sudo mysql -u root -p

![w11](./images/w11.png)

3. Create Database

     #Create Database

     create database wordpressdb;

     #Show Database

     show databases;

![w12](./images/w12.png)

### Step 7: Install Connector

sudo yum install php8.4-mysqlnd.x86_64

![w13](./images/w13.png)

### Step 8: Change ownership of the files

![w14](./images/w14.png)

### Step 9: Paste the Public IP and Paste it in any browser.

1. Click on Continue 

![w16](./images/w16.png)

2. Click on Let,s go 

![w17](./images/w17.png)

3. Fill the information and click on Submit 

![w18](./images/w18.png)

4. Run the Installation 

![w19](./images/w19.png)

5. Fill the information and click on Install Wordpress 

![w20](./images/w20.png)

6. Login to Wordpress 

![w21](./images/w21.png)

7. Deployed Wordpress successfully

![w22](./images/w22.png)

8. Table automatically added to Database

![w23](./images/w23.png)

# Summary

This project is a complete guide to setting up a WordPress website on a Linux server. It uses Apache as the web server and MariaDB as the database. The guide explains how to download and install WordPress, set the right file permissions, create and connect the database, and configure the web server for live use. By following it, you’ll get a secure, reliable, and fully working WordPress site that’s ready for people to visit.






