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

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8

<h2>Installation Steps</h2>

<p>
1. Create a <a href="https://github.com/NathanSuguitan/Azure-ResourceGroups">Resource Group</a> <br>
&nbsp A. Create a Virtual Machine in Azure within that resource group <br>
&nbsp B. Create a Windows 10 Pro Virtual Machine with at least 2-4 Virtual CPUs <br>
&nbsp &nbsp i. Create a name, username, and password (remember the username and password) <br>
&nbsp &nbsp  &nbsp ii. This will create a new Virtual Network (Vnet)
<p>
  
![Screenshot 2023-08-19 132701](https://github.com/NathanSuguitan/osticket-prereqs/assets/138082246/87117311-30d8-4ddd-a7c9-a94f67dc94cc)


</p>
<br />

<p>
2. Open the <a href="https://drive.google.com/drive/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">Installation Files</a> in the VM <br>
 &nbsp A. Righ click start menu -> Run -> Type "control" -> Programs -> Turn Windows Features On or Off <br>
<p> 
&nbsp B. Install / Enable IIS in Windows WITH:
CGI and Common HTTP Features
World Wide Web Services -> <br> Application Development Features -> <br>
[X] CGI <br>
[X] Common HTTP Features
</p>
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/c87c2862-4a15-46e5-b246-f9a4b407c812" height="60%" width="60%" alt="Setup ISS"/>
</p>
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/fcb01f44-78c7-4bab-a7b0-328269bcc17e" height="60%" width="60%" alt="Setup ISS"/>
</p>
<p>
 Internet Information Services -> Web Management Tools -> IIS Management Console <br>
	[X] IIS Management Console -> Ok
</p>
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/2b132258-c893-405d-8d05-4f38dcd63c83" height="60%" width="60%" alt="Setup ISS"/>
</p>
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/98279b81-1b8e-4b8c-b6b6-9410db315dbd" height="60%" width="60%" alt="Setup ISS"/>
</p>

C. Check if it's working by typing the following IP address into the browser: 127.0.0.1
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/417dfb31-1f1d-43d8-b0dc-4eb4ee08d4f7" height="60%" width="60%" alt="Setup ISS"/>
</p>
</p>
<br />

<p>
3. From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) <br>
&nbsp A. From the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi) <br>
&nbsp &nbsp i. Create the directory C:\PHP in your files: 
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/b5204e78-0fbd-4e38-a399-1da51463f517" height="60%" width="60%" alt="Download Files"/>
</p>
<p>
B. From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP <br>
!!! Attention!!! If you get a caution sign from the download, click on it -> Keep -> Keep anyway <br>

<p>
C. From the Installation Files, download and install VC_redist.x86.exe. <br>

D. From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) <br>
&nbsp i. Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration -> (make a password and remember it) -> Execute -> Finish
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/3a4e2053-0604-40bb-8dbe-5bd07a25f58a" height="60%" width="60%" alt="Download Files"/>
</p>
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/d6674cc3-5c7d-495e-8dce-d9ae533d36b3" height="60%" width="60%" alt="Download Files"/>
</p>
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/6569d389-b4dc-4dde-96cf-f60c0421ab7c" height="60%" width="60%" alt="Download Files"/>
</p>
</ br>

<p>
4. Open IIS as an Admin <br>
&nbsp A. Register PHP from within IIS: PHP Manager -> Register New PHP Version -> C:\PHP\php-cgi.exe <br>
&nbsp &nbsp i. Reload IIS (Open IIS, Stop and Start the server)
</p>
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/7bb2faa2-afa8-4cf0-bb4e-d04b2e3556ef" height="60%" width="60%" alt="Register PHP"/>
</p>
<br />

<p>
5. Install osTicket v1.15.8 <br>
&nbsp A. Download osTicket from the Installation Files Folder <br>
&nbsp &nbsp i. Extract and copy “upload” folder to c:\inetpub\wwwroot <br>
&nbsp &nbsp &nbsp ii. Within c:\inetpub\wwwroot, Rename “upload” to “osTicket” <br>
&nbsp &nbsp &nbsp &nbsp iii. Reload IIS (Open IIS, Stop and Start the server)
</p>
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/8f336a80-29aa-4c4f-809f-907b2a2db62c" height="60%" width="60%" alt="Install osTicket"/>
<br />

<p>
6. Go to sites -> Default -> osTicket <br>
&nbsp A. On the right, click “Browse *:80”
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/a15d8f6f-8e71-4048-bd3f-5ca1cc1e2b3b" height="60%" width="60%" alt="osTicket"/>
</p>
B. Some extensions are not enabled
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/0f4f976c-4175-4867-a24c-6b27cf1ba397" height="60%" width="60%" alt="osTicket"/>
</p>
C. Go back to IIS, sites -> Default -> osTicket -> Double-click PHP Manager -> Click “Enable or disable an extension” <br>
&nbsp i. Enable: php_imap.dll <br>
&nbsp &nbsp ii. Enable: php_intl.dll <br>
&nbsp &nbsp &nbsp iii. Enable: php_opcache.dll
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/e31cb337-49d3-47e9-9c3c-9bc2f60cdc33" height="60%" width="60%" alt="osTicket"/>
</p>
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/3530d812-9568-4df5-aba0-ed8bfcb44da4" height="50%" width="50%" alt="osTicket"/>
</p>
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/2f52385f-9e7b-4185-a4cc-3a9d194ca3a8 " height="50%" width="50%" alt="osTicket"/>
</p>
iv. Refresh the osTicket site in your browse, observe the changes
</p>
<br />

<p>
7. Rename: ost-config.php <br>
&nbsp A. From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php <br>
&nbsp &nbsp i. To: C:\inetpub\wwwroot\osTicket\include\ost-config.php <br>
<p>
&nbsp B. Assign Permissions: ost-config.php <br>
&nbsp &nbsp i. Properties -> Security -> Advanced -> Disable inheritance -> Remove All <br>
&nbsp &nbsp &nbsp ii. New Permissions -> Select a Principal -> Everyone -> All
</p>
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/b952bedd-b0d0-4096-af23-dae5e70c909e" height="60%" width="60%" alt="Assign Permissions"/>
</p>
<br />

<p>
8. Continue Setting up osTicket in the browser (click Continue) <br>
&nbsp A. Name Helpdesk <br>
&nbsp &nbsp i. Default email (receives email from customers)
</p>
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/ee007ffc-d4ed-473d-95c4-78ff356624a5" height="60%" width="60%" alt="osTicket Setup"/>
</p>
<br />

<p>
9. From the Installation Files, download and install HeidiSQL.
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/9aa2f60a-034d-439d-9970-23906957b7dd" height="60%" width="60%" alt="Heidi SQL Setup"/>
</p>
A. Open Heidi SQL <br>
&nbsp i. Create a new session, root/Password1 <br>
&nbsp &nbsp ii. Connect to the session <br>
&nbsp &nbsp &nbsp iii. Create a database called “osTicket”
</p>
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/e2e5c43a-312b-4a4e-85f8-5d9af1908a8b" height="60%" width="60%" alt="Heidi SQL Setup"/>
</p>
<br />

<p>
10. Continue Setting up osticket in the browser <br>
&nbsp A. MySQL Database: osTicket <br>
&nbsp &nbsp i. MySQL Username: root <br>
&nbsp &nbsp &nbsp ii. MySQL Password: Password1 <br>
&nbsp &nbsp &nbsp &nbsp iii. Click “Install Now!”
</p>
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/55f7d893-a42a-48a0-b9b1-c9ce1dc96ab3" height="60%" width="60%" alt="osTicket Setup"/>
</p>
<br />

<p>
Congratulations, osTicket is now installed <br>
Browse to your help desk login page: http://localhost/osTicket/scp/login.php

End Users osTicket URL: http://localhost/osTicket/
</p>
<p>
<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/2d3ccbbc-46d9-4b1b-90e9-a5c1288c2d1a" height="60%" width="60%" alt="osTicket"/>
</p>
<br />

<p>
Clean up <br>
Delete: C:\inetpub\wwwroot\osTicket\setup <br>
!!! Important !!! ONLY DELETE THE SETUP FOLDER <br>
Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
</p>
<br />
