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
<h3> 1. Create a virtual machine in Azure </h3>
  
- Make sure to use a Virtual Machine (VM) with at least 4vcpus to ensure a speedy installation process. Once your VM has been deployed connect to it through remote desktop. 
</p>
<p>
<img width="459" alt="VM Creation 2" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/09a34b0e-9f45-47d8-bb99-db4ce9d8e2c0">

</p>


------------------------------------------------------------------------------------------------------------------------------------------------


<h3> 2. On your VM install IIS through the following steps: </h3>

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

------------------------------------------------------------------------------------------------------------------------------------------------

<p>

</p>
<h3> 3. Download and Install PHP Manager for IIS and ReWrite Module </h3>

- Download and Install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
- Download and Install Rewrite Module (rewrite_amd64_en-US.msi)
- Create a Folder in the C Drive called PHP
- Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into the PHP folder that was created in the C Drive
  
  <img width="700" alt="Install PHP rewrite etc" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/23084dd5-3c47-42a6-99d1-d0f327621dfc">
  

<br />

<h3> 4. Download and Install Microsoft Visual C++ and MYSQL 5.5.62 </h3>

- Download and Install Microsoft Visual C++ VC_redist.x86.exe
- Download and Install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
  
   - Typical Setup - >
   - Launch MYSQL Instance Configuration Wizard (after install) - >
 
  <img width="500" alt="MYSQL installation" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/f6054a9a-dfac-4503-a304-46cc1b006566">

  <br />
  
   - Standard Configuration - >
   - Password1

  <img width="500" alt="MYSQL configuration" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/5d21e59f-dab0-40e5-aafc-96a0d594aa4e">

<br />

------------------------------------------------------------------------------------------------------------------------------------------------

<h3> 5. Register PHP within IIS </h3>
<p>
  
- Navigate to Internet Information Sevices Manager, and run as administrator
- Click on PHP Manager
- Click on Register New PHP version
- Navigate to the PHP folder in the C drive and click on the php cgi executable
- Restart osTicket Server
- Minimize IIS Manager


<img width="1375" alt="PHP manager set up in IIS" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/d8f94b3d-2e33-437d-928d-5ee1e735dc20">
<img width="500" alt="Restart Server" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/a7840ef0-8883-4a74-b23a-1ee6f2d9e342">


</p>
<br />

------------------------------------------------------------------------------------------------------------------------------------------------
<h3> 6. Install osTicket v1.15.8 </h3>

- Install and Download osTicket  v1.15.8
- Extract and copy “upload” folder to c:\inetpub\wwwroot
- Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”
- Reload osTicket Server in IIS Manager

<img width="1140" alt="Install osTicket" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/dee0ce6a-5fc9-47ee-8443-53663c4f299a">

<br />

------------------------------------------------------------------------------------------------------------------------------------------------

<h3> 7. Navigate to osTicket Browser and enable necessary extensions </h3>

- In IIS Manager navigate Sites -> Default Website -> Click on “Browse *:80”
- Note that not all the extensions are not activated
- Go back to IIS, sites -> Default -> osTicket
- Double-click PHP Manager
    - Enable the following extensions:
    - php_imap.dll
    - php_intl.dll
    - php_opcache.dll
- Refresh the osTicket site in your browse, observe the changes




