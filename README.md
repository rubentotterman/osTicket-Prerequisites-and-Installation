<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

osTicket Deployment on Azure VM
Deploying and configuring the open-source help desk ticketing system osTicket v1.15.8 on a Windows 10 Azure Virtual Machine.

Overview
This project focuses on the end-to-end installation of osTicket, including setting up the web server (IIS), configuring PHP and MySQL, and preparing the ticketing system for use. It simulates a real-world IT support environment deployment.

Skills and Technologies Used
Microsoft Azure (VM provisioning)

Windows 10 (Server configuration)

IIS Web Server

PHP 7.3

MySQL 5.5

HeidiSQL

osTicket v1.15.8

Basic Networking (Remote Desktop Protocol)

Prerequisites
Azure account with VM provisioning access

Software installed on the VM:

HeidiSQL

MySQL 5.5

PHP 7.3

PHP Manager for IIS

IIS Rewrite Module

Visual C++ Redistributable (VC_redist)

Setup and Installation
1. Virtual Machine Setup
Create a Windows 10 VM in Azure:

OS: Windows 10

vCPUs: 4

VM Name: osticket-vm

Connect to the VM using Remote Desktop (RDP).

2. File Preparation
Download osTicket-Installation-Files.zip onto the VM desktop.

Unzip all contents.

3. IIS & PHP Configuration
Enable IIS with CGI support:

Windows Features > World Wide Web Services > Application Development Features

Enable CGI.

Install Required Software:

PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

IIS Rewrite Module (rewrite_amd64_en-US.msi)

Visual C++ Redistributable (VC_redist.x86.exe)

Setup PHP:

Create directory: C:\PHP

Unzip php-7.3.8-nts-Win32-VC15-x86.zip into C:\PHP.

Register PHP in IIS via PHP Manager:

Path: C:\PHP\php-cgi.exe

Restart IIS (Stop and Start).

4. Install MySQL
Install using mysql-5.5.62-win32.msi

Setup type: Typical

Credentials:

Username: root

Password: root

5. osTicket Installation
Unzip osTicket-v1.15.8.zip.

Copy the upload folder into C:\inetpub\wwwroot.

Rename upload to osTicket.

Reload IIS:

Navigate: Sites → Default → osTicket

Browse to site (:80 port).

6. Enable PHP Extensions
In IIS:

Sites → Default → osTicket → PHP Manager

Enable the following extensions:

php_imap.dll

php_intl.dll

php_opcache.dll

Refresh the browser to load changes.

7. Configure osTicket
Rename Config File:

Rename: ost-sampleconfig.php → ost-config.php

Set Permissions:

Disable inheritance

Remove all existing permissions

Add Everyone with Full Control access

In the browser:

Set up Helpdesk Name

Set Default Email

8. Database Setup
Install HeidiSQL:

Create a new session:

User: root

Password: root

Create Database:

Database Name: osTicket

Finalize Setup in Browser:

MySQL Database: osTicket

MySQL User: root

MySQL Password: root

Click "Install Now".

Access URLs
Admin Panel: http://localhost/osTicket/scp/login.php

User Portal: http://localhost/osTicket/

What I Learned
Setting up a basic IIS web server environment.

Managing PHP extensions and IIS modules.

Integrating multiple components (IIS, PHP, MySQL, osTicket) into a working help desk platform.

Practical experience in cloud VM setup, remote management, and troubleshooting server configurations.

Future Improvements
Migrate deployment to Linux server environment (Apache + MySQL + PHP stack).

Secure osTicket installation with HTTPS.

Set up email piping and auto-responses for ticket notifications.



## 📸 Screenshots



![Step 1 - IIS config](screenshots/Capture.PNG)
![Step 2 - osTicket extensions](screenshots/sdasdasdasd.PNG)
![Step 3 - extensions](screenshots/sgsdfsdfsd.PNG)
![Step 3 - database setup](screenshots/CaptureASDADAD.PNG)
![Step 4 - osTicket installed](screenshots/DFSFSDF.PNG)
![Step 5 - osTicket adminPanel](screenshots/asdadadsad.PNG)


</p>
<br />
