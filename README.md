<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create Virtual Machine in Azure that uses Windows 10
- Install and enable Information Internet System (IIS) in Windows
- Install PHP Manager for IIS
- Install reWrite Module
- Download PHP 7.3.8
- Install VC_redist.x86.exe
- Install MySQL 5.5.62
- Register PHP in IIS
- Install osTicket
- Download and install HiediSQL
- Setup osTicket setup in Browser
- Cleanup osTicket file setup

<h2>Installation Steps</h2>

<p>
<h4> 1. Create a virtual machine in Azure </h4>
  
- Make sure to use a Virtual Machine (VM) with at least 4vcpus to ensure a speedy installation process. Once your VM has been deployed connect to it through remote desktop. 
</p>
<p>
<img width="459" alt="VM Creation 2" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/09a34b0e-9f45-47d8-bb99-db4ce9d8e2c0">

</p>

<br />
<h4> 2. On your VM install IIS through the following steps: </h4>

- Navigate to the Control Panel - > Programs - > Turn Windows Features On or Off
- Select Internet Information Services
- Select Web Management tools -> IIS Management Console
- Select World Wide Web Service - > Application Development Features -> CGI
- Select Common HTTP Features
- Press OK

<img width="960" alt="Install IIS" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/3546182c-c12a-4746-ae8f-e6897ff0c3e4">
</p>

- Navigate to Internet explorer and type in 127.0.0.1 to ensure that the IIS has been properly installed. You should arrive at the following image which will indicate success
  
<br />

<img width="400" alt="Success IIS" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/e7c7ee85-1597-4b49-a79b-b7d26e48ee1d">

<br />


<p>

</p>
<h4> 3. Download and Install PHP Manager for IIS and ReWrite Module </h4>

- Download and Install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
- Download and Install Rewrite Module (rewrite_amd64_en-US.msi)
- Create a Folder in the C Drive called PHP
- Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into the PHP folder that was created in the C Drive
  
  <img width="1307" alt="Install PHP rewrite etc" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/23084dd5-3c47-42a6-99d1-d0f327621dfc">
  

<br />

<h4> 4. Download and Install Microsoft Visual C++ and MYSQL 5.5.62 </h4>

- Download and Install Microsoft Visual C++ VC_redist.x86.exe
- Download and Install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
  
   - Typical Setup - >
   - Launch MYSQL Instance Configuration Wizard (after install) - >
   - Standard Configuration - >
   - Password1 
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
