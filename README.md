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

- Information Internet System (IIS) 
- PHP Manager
- ReWrite Module
- VC Redist
- MySQL 
- osTicket
- HiediSQL
- [Link to Installation Files](https://drive.google.com/drive/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) 

<h2>Installation Steps</h2>


<p>

  <h3> 1. Create a virtual machine in Azure </h3>
  
- Go to azure.portal.com and create a new virtual machine (VM). 
- Select Windows 10 22H2 as your image and a VM size of at least 4vcpus to ensure speedy processing.

   <img height = "30%" width="30%" alt="VM Creation 2" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/7f796c42-237f-4775-9390-de4da8777a00">

<br />

- Once your VM has been deployed copy its Public IP address.
  
    <img align = "top" height = "30%" width="30%" alt="Get Public IP Address" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/37adf0cc-fddc-4935-b017-b4d466313858">
  </p>
      

-  Connect to the VM through remote desktop.
  
      <img align = "top" height = "30%" width="30%" alt="remote desktop" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/e530e1fc-50aa-4747-8859-261eaef0741f">

</p>


------------------------------------------------------------------------------------------------------------------------------------------------


<h3> 2. On the VM install IIS</h3>

- Navigate to the Control Panel - > Programs - > Turn Windows Features On or Off.
- Select Internet Information Services.
- Select Web Management tools -> IIS Management Console.
- Select World Wide Web Service - > Application Development Features -> CGI.
- Select Common HTTP Features.
- Click OK.
  
  <img height = "40%" width="40%" alt="Install IIS" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/54ce7efe-5f1a-40a9-b4d5-bdf5a4a8c6c2">


- Navigate to Micrsoft Edge and type in 127.0.0.1 (loopback address)to ensure that the IIS has been properly installed. You should arrive at the following image which will indicate success.
  
  <img height = "40%" width="40%" alt="Success IIS" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/e7c7ee85-1597-4b49-a79b-b7d26e48ee1d">

<br />

------------------------------------------------------------------------------------------------------------------------------------------------

<p>

</p>
<h3> 3. Download and Install PHP Manager for IIS and ReWrite Module </h3>

- Download and Install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
- Download and Install Rewrite Module (rewrite_amd64_en-US.msi)
- Create a Folder in the C Drive labeled PHP
  
    <img height = "40%" width="40%" alt="php folder" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/349f6214-90d3-4af7-a185-81a721bc34b8">
    
- Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into the PHP folder that was created in the C Drive
  
    <img align= "top" height = "40%" width="40%" alt="php folder extracted" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/36479e30-491f-41cf-ba0b-bde4c8f9d34f">

<br />

<h3> 4. Download and Install Microsoft Visual C++ and MYSQL 5.5.62 </h3>

- Download and Install Microsoft Visual C++ VC_redist.x86.exe.
- Download and Install MySQL 5.5.62 (mysql-5.5.62-win32.msi).
- During the setup of MySQL select the following.
   - Typical Setup 
   - Launch MYSQL Instance Configuration Wizard (after install) 
 
      <img height = "40%" width="40%" alt="MYSQL Install 1" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/a550f17a-a0fc-4959-97da-d7afb31cfb6e">
      <img height = "40%" width="40%" alt="mysql install 2" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/67706642-0cd2-491b-adb1-54f9f138686f">


  <br />
  
   - Standard Configuration - >
   - Install as Window Service
   - Type in Password1

      <img height = "40%" width="40%" alt="MYSQL configuration" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/d1a781df-224c-40a5-ac83-d613974d4897">
      <img height = "40%" width="40%"  alt="mysql config 2" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/4fb72746-c1d0-4ed5-9462-c074c81b3be8">
      <img height = "40%" width="40%"  alt="mysql config 3" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/419b492e-f67c-4f44-96af-ad75252222bc">



<br />

------------------------------------------------------------------------------------------------------------------------------------------------

<h3> 5. Register PHP within IIS </h3>
<p>
  
- Navigate to Internet Information Sevices Manager, and run as administrator.

    <img height = "40%" width="40%" alt="PHP manager set up in IIS" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/33aff5c3-9432-4cf3-9281-1b7abb691dbb">
    
- Click on PHP Manager.
  
    <img align= "top" height = "40%" width="40%" alt="find php 1" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/c5fbb2fa-59d2-4125-a14b-72da511a8f00">

    

- Click on Register New PHP version.

    <img height = "40%" width="40%" alt="PHP register" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/bec6661d-3404-434b-b0f3-063bcb760379">
    
- Navigate to the PHP folder in the C drive and click on the php cgi executable.
      
     <img align= "top" height = "40%" width="40%" alt="php install cgi" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/fb153957-55a3-4c98-bad3-79a13e199efb">

    
- Restart osTicket Server.
  
     <img height = "40%" width="40%" alt="Restart Server" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/a7840ef0-8883-4a74-b23a-1ee6f2d9e342">
     
  


</p>
<br />

------------------------------------------------------------------------------------------------------------------------------------------------
<h3> 6. Install osTicket v1.15.8 </h3>

- Install and Download osTicket  v1.15.8.
- Extract and copy “upload” folder to c:\inetpub\wwwroot.
  
   <img height = "40%" width="40%" alt="Install osTicket" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/5b9baacb-7f5e-4f1e-b5cb-474bcaca8d25">
   
- Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”.
  
    <img height = "40%" width="40%" alt="install osTicket2" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/9674e681-24e8-47fe-be94-af9221b626e7">
    
- Reload osTicket Server in IIS Manager.

    <img height = "40%" width="40%" alt="refresh osTicket" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/d472c6f5-2e7b-4175-93fd-327837433023">



<br />

------------------------------------------------------------------------------------------------------------------------------------------------

<h3> 7. Navigate to osTicket Browser and enable necessary extensions </h3>

- In IIS Manager navigate to Sites -> Default Website -> Click on “Browse *:80”.
  
    <img height = "40%" width="40%" alt="osTicket Browser" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/82f2f6f1-f8bf-4c97-b28b-a09a6ff0f6cc">
       
- Note that not all the extensions are activated.
    
    <img height = "40%" width="40%" alt="osticket browser 2" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/b3e6113c-1613-4252-8524-cc041ee3d4d7">
    


- Go back to IIS, Sites -> Default -> osTicket
  
    <img height = "40%" width="40%" alt="Extension enable 1" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/413fae07-de4d-46c5-bc2c-6e9e0a0459d1">
    
- Double-click PHP Manager
    - Enable the following extensions:
    - php_imap.dll
    - php_intl.dll
    - php_opcache.dll
      
        <img height = "40%" width="40%" alt="extension enable 2" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/e67db73e-7ed6-420e-b8a6-4d9f3e908cf0">
        
        <img height = "40%" width="40%" alt="extension enable 3" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/f169414e-4440-491c-b67d-812898602e68">
        
- Refresh the osTicket site in your browser, and observe the changes

    <img height = "40%" width="40%" alt="refresh browser" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/9c79cf7e-2fb6-4368-8000-30a07f2909d4">

<br />

------------------------------------------------------------------------------------------------------------------------------------------------

<h3> 8. Rename ost-config and assign permissions </h3>

- Rename ost-config
    - From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
    - To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

        <img height = "30%" width="30%" alt="rename sample ost-config" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/28a4d3b6-a8bf-47ed-9a3d-34b2d4657837">
        
- Assign Permissions to ost-config
    - Right click on ost-config -> Properties -> Security -> Advanced   
        - Disable inheritance -> Remove All
          
          <img height = "30%" width="30%" alt="disable inheritances ost-config" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/68cae2d1-e71e-4336-99d3-da5531f79df5">
        
    - Assign new permissions to Everyone
        - Click Add -> Select Principal
          -  Type in Everyone -> Select Full Control -> Ok 

              <img height = "30%" width="30%"  alt="Properties" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/b5a3a698-55ae-4a7c-8b00-3d9f19a07adb">


 <br />

 ------------------------------------------------------------------------------------------------------------------------------------------------

<h3> 9. Setup osTicket in Browser </h3>

- Continue Setting up osTicket in the browser
- Fill in the Helpdesk username and Admin User information
  
<img height = "40%" width="40%" alt="Basic Info fill in osTicket" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/2bf44fa6-2205-412d-adee-96000a42786e">

- Download and Install Heidi SQL.
- Open Heidi SQL.
- Create a New Session, with the user as root, and the password as Password1.

    <img height = "30%" width="30%" alt="new session in heidi sql" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/b2c2b607-813b-4cd2-9adc-dc4388a193f2">
    
- Create a new database, called osTicket.

    <img height = "40%" width="40%" alt="create new database" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/9353f296-e9ed-45f9-a073-eb918a169688">

    <img height = "40%" width="40%" alt="HeidiSQL Database setup" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/08dc0327-1138-4143-947f-0db397097d74">



- Go back to the osTicket browser and enter the following:
    - MySQL Database: osTicket
    - MySQL Username: root
    - MySQL Password: Password1
- Click “Install Now!”

  <img height = "30%" width="30%" alt="osTicket Congratulations" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/74a65ea9-83f4-4d3e-8b4a-fb218a79bf17">

 <br />
 
- Browse to your help desk login page: http://localhost/osTicket/scp/login.php
- Login with your Admin users information

    <img height = "30%" width="30%" alt="Login at local host success" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/75f9b60c-5d7e-4f69-bdd9-26ef54d9f43d">

<br />

------------------------------------------------------------------------------------------------------------------------------------------------

<h3>10. Clean Up</h3>

- Delete: C:\inetpub\wwwroot\osTicket\setup

    <img height = "40%" width="40%" alt="Delete set up clean up" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/149290e6-f32d-4f0e-9062-b5c83be3670e">

  <br />
  
- Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php

    <img height = "40%" width="40%" alt="Permissions os-config read only" src="https://github.com/s-evelyn/osticket-prereq/assets/53543374/9d74bfcb-4907-4a1d-be4e-8e574aa2d538">

<br />

Congratulations you have successfully installed osTicket on your Virtual Machine, Continue to the [osTicket: Post-Installation Configuration Tutorial](https://github.com/s-evelyn/osTicket-PostInstallConfig) 


