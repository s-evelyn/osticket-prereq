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
<img width="459" alt="VM Creation 2" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/09a34b0e-9f45-47d8-bb99-db4ce9d8e2c0">

</p>
<p>
Create a virtual machine in Azure under your subscription, make sure to use a Virtual Machine (VM) with at least 4vcpus to ensure a speedy installation process. Once your VM has been deployed connect to it through remote desktop. 
</p>
<br />

<p>
<img width="960" alt="Install IIS" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/3546182c-c12a-4746-ae8f-e6897ff0c3e4">
</p>

<h5> On your VM install IIS through the following steps: </h5>

- Navigate to the Control Panel - > Programs - > Turn Windows Features On or Off
- Select Internet Information Services
- Select Web Management tools -> IIS Management Console
- Select World Wide Web Service - > Application Development Features -> CGI
- Select Common HTTP Features
- Press OK

- Navigate to Internet explorer and type in 127.0.0.1 to ensure that the IIS has been properly installed. You should arrive at the following image which will indicate success






<p>
Select 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
