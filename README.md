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

- Windows 10</b> (22H2)

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
  
- Go to azure.portal.com and create a new virtual machine (VM). 
- Select Windows 10 22H2 as your image and a VM size of at least 4vcpus to ensure a speedy processing.

   <img width="250" alt="VM Creation 2" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/7f796c42-237f-4775-9390-de4da8777a00">


<br />

- Once your VM has been deployed get a copy of its Public IP address and connect to it through remote desktop.
  </p>
  <img align = "top" width="600" alt="Get Public IP Address" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/37adf0cc-fddc-4935-b017-b4d466313858">


  <img align = "top" width="288" alt="remote desktop" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/e530e1fc-50aa-4747-8859-261eaef0741f">

</p>


------------------------------------------------------------------------------------------------------------------------------------------------


<h3> 2. On your VM install IIS through the following steps: </h3>

- Navigate to the Control Panel - > Programs - > Turn Windows Features On or Off
- Select Internet Information Services
- Select Web Management tools -> IIS Management Console
- Select World Wide Web Service - > Application Development Features -> CGI
- Select Common HTTP Features
- Press OK
  
  <img width="500" alt="Install IIS" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/54ce7efe-5f1a-40a9-b4d5-bdf5a4a8c6c2">


- Navigate to Micrsoft Edge and type in 127.0.0.1 (loopback address)to ensure that the IIS has been properly installed. You should arrive at the following image which will indicate success
  
  <img width="500" alt="Success IIS" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/e7c7ee85-1597-4b49-a79b-b7d26e48ee1d">

<br />

------------------------------------------------------------------------------------------------------------------------------------------------

<p>

</p>
<h3> 3. Download and Install PHP Manager for IIS and ReWrite Module </h3>

- Download and Install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
- Download and Install Rewrite Module (rewrite_amd64_en-US.msi)
- Create a Folder in the C Drive called PHP
- Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into the PHP folder that was created in the C Drive
  
  <img width="700" alt="php folder" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/9fcb6bb4-0079-48fe-a375-2e62c2ac143e">

  

<br />

<h3> 4. Download and Install Microsoft Visual C++ and MYSQL 5.5.62 </h3>

- Download and Install Microsoft Visual C++ VC_redist.x86.exe
- Download and Install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
  
   - Typical Setup - >
   - Launch MYSQL Instance Configuration Wizard (after install) - >
 
      <img width="500" alt="MYSQL Install 1" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/082a560a-a40e-4c90-ae6c-906c61744ece">


  <br />
  
   - Standard Configuration - >
   - Password1

      <img width="700" alt="MYSQL configuration" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/258ed77c-4b41-4773-9dd5-68dbef5f4f8c">


<br />

------------------------------------------------------------------------------------------------------------------------------------------------

<h3> 5. Register PHP within IIS </h3>
<p>
  
- Navigate to Internet Information Sevices Manager, and run as administrator
- Click on PHP Manager

    <img width="600" alt="PHP manager set up in IIS" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/4970063c-1fa0-47c2-a211-5ebbbfd14599">

- Click on Register New PHP version
- Navigate to the PHP folder in the C drive and click on the php cgi executable
  
    <img width="600" alt="PHP register" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/0f3b3555-9f06-49cd-9db8-803ed84447b0">

    
- Restart osTicket Server
- Minimize IIS Manager

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

<img width="1742" alt="Necessary extensions" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/131dda5d-8342-440e-95a0-de1471530563">

<img width="500" alt="refresh browser" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/9c79cf7e-2fb6-4368-8000-30a07f2909d4">

<br />

------------------------------------------------------------------------------------------------------------------------------------------------

<h3> 8. Rename ost-config and assign permissions </h3>

- Rename ost-config
    - From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
    - To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
- Assign Permissions to ost-config
    - Disable inheritance -> Remove All
    - New Permissions -> Everyone -> All


 <img width="1082" alt="Disable inheritances" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/2e8c3fcd-36ab-4aa7-a226-a336a41c0676">

 <br />
 
<img width="270" alt="Properties" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/e8090d74-5182-4599-a14c-4d7b4f21a6cc">

 <br />

 ------------------------------------------------------------------------------------------------------------------------------------------------

<h3> 9. Setup osTicket in Browser </h3>

- Continue Setting up osTicket in the browser
- Fill in the Helpdesk username and Admin User information
  
<img width="692" alt="Basic Info fill in osTicket" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/2bf44fa6-2205-412d-adee-96000a42786e">

- Download and Install Heidi SQL
<img width="899" alt="Heidi SQL Download and Install" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/1c09f2ca-353e-4302-8f43-e6925f40fdd2">

<br />

- Create a New Session, with the user as root, and the password as Password 1
- Create a new database, called osTicket
  
<img width="888" alt="HeidiSQL Database setup" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/d9c75b3c-a6d1-42b3-a5cc-0241e88bb29e">

<br />

- Toggle back to the osTicket browser and enter the following
    - MySQL Database: osTicket
    - MySQL Username: root
    - MySQL Password: Password1
    - Click “Install Now!”

<img width="300" alt="osTicket Congratulations" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/74a65ea9-83f4-4d3e-8b4a-fb218a79bf17">

 <br />
 
- Browse to your help desk login page: http://localhost/osTicket/scp/login.php
- Login with your Admin users information

<img width="500" alt="Login at local host success" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/75f9b60c-5d7e-4f69-bdd9-26ef54d9f43d">

<br />

------------------------------------------------------------------------------------------------------------------------------------------------

<h3>10. Clean Up</h3>

- Delete: C:\inetpub\wwwroot\osTicket\setup

  <img width="597" alt="Delete set up clean up" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/149290e6-f32d-4f0e-9062-b5c83be3670e">

  <br />
  
- Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php

<img width="272" alt="Permissions os-config read only" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/9d74bfcb-4907-4a1d-be4e-8e574aa2d538">

<br />

<h3>Congratulations you have successfully installed osTicket in your Virtual Machine, Find the link to the Post Intallation Tutorial below </h3>


