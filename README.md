<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>


<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.

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


1. Create a <a href="https://github.com/NathanSuguitan/Azure-ResourceGroups">Resource Group</a> <br>
&nbsp; A. Create a <a href="https://github.com/NathanSuguitan/Azure-VM">Virtual Machine</a> in Azure within the resource group <br>
&nbsp; B. Create a Windows 10 Pro Virtual Machine with at least 2-4 Virtual CPUs <br>
&nbsp;&nbsp; i. Create a name, username, and password (remember the username and password) <br>
&nbsp;&nbsp; ii. This will create a new Virtual Network (Vnet) <br>
&nbsp; C. Connect to Virtual Machine

![Screenshot 2023-08-19 132701](https://github.com/NathanSuguitan/osticket-prereqs/assets/138082246/87117311-30d8-4ddd-a7c9-a94f67dc94cc)

2. Install / Enable IIS in Windows <br>
 &nbsp; A. Right click start menu -> Run -> Type "control" -> Programs -> Turn Windows Features On or Off <br>
 &nbsp; B. Check [X] and expand [+] Internet Information Services -> <br>
 &nbsp;&nbsp; [+] World Wide Web Services -> <br>
 &nbsp;&nbsp; [+] Application Development Features -> <br>
 &nbsp;&nbsp; Check [X] CGI <br>

![255341795-c87c2862-4a15-46e5-b246-f9a4b407c812](https://github.com/NathanSuguitan/osticket-prereqs/assets/138082246/2128af9d-55f8-4fdb-9aa0-50f17a2ddfb9) <br>

&nbsp;&nbsp;&nbsp;&nbsp; C. Collapse [-] Application Development Features <br>
&nbsp;&nbsp;&nbsp;&nbsp; D. Expand [+] Common HTTP Features and check [X] HTTP Redirection and [X] WebDAV Publishing <br>

![255342164-fcb01f44-78c7-4bab-a7b0-328269bcc17e](https://github.com/NathanSuguitan/osticket-prereqs/assets/138082246/33970810-5acd-42a4-a9ec-3a4d441e1e2b)

&nbsp;&nbsp;&nbsp;&nbsp; E. Click **ok** to apply changes <br>
&nbsp;&nbsp;&nbsp;&nbsp; F. Check if it's working by typing the following IP address into the browser: 127.0.0.1 <br>

3. Download and install <a href="https://www.iis.net/downloads/community/2018/05/php-manager-150-for-iis-10">PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)</a><br>
&nbsp; A. download and install the <a href="https://www.iis.net/downloads/microsoft/url-rewrite#:~:text=Download%20URL%20Rewrite%20Module%202.1">Rewrite Module (rewrite_amd64_en-US.msi)</a><br>
&nbsp; &nbsp; i. Create the directory in the C: Drive with the name "**PHP**". 

![255373171-b5204e78-0fbd-4e38-a399-1da51463f517](https://github.com/NathanSuguitan/osticket-prereqs/assets/138082246/d072893c-6d05-41e9-aacf-a3b91f45cd49)

B. Download and install <a href="https://www.iis.net/downloads/community/2018/05/php-manager-150-for-iis-10">PHP Manager (php-7.3.8-nts-Win32-VC15-x86.zip)</a> and unzip the contents into C:\PHP <br>

C. Download and install <a href="https://www.microsoft.com/en-US/download/details.aspx?id=48145">VC_redist.x86.exe.</a><br>

D. Download and install <a href="https://www.npackd.org/p/com.mysql.MySQLCommunityServer/5.5.62">MySQL 5.5.62 (mysql-5.5.62-win32.msi)</a><br>
&nbsp; i. Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration -> (make a password and remember it) -> Execute -> Finish

<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/3a4e2053-0604-40bb-8dbe-5bd07a25f58a" height="60%" width="60%" alt="Download Files"/>


<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/d6674cc3-5c7d-495e-8dce-d9ae533d36b3" height="60%" width="60%" alt="Download Files"/>


<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/6569d389-b4dc-4dde-96cf-f60c0421ab7c" height="60%" width="60%" alt="Download Files"/>


4. Open IIS as an Admin <br>
&nbsp; A. Register PHP from within IIS: PHP Manager -> Register New PHP Version -> C:\PHP\php-cgi.exe <br>
&nbsp; &nbsp; i. Reload IIS (Open IIS, Stop and Start the server)


<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/7bb2faa2-afa8-4cf0-bb4e-d04b2e3556ef" height="60%" width="60%" alt="Register PHP"/>




5. Install osTicket v1.15.8 <br>
&nbsp; A. Download osTicket from the Installation Files Folder <br>
&nbsp; &nbsp; i. Extract and copy “upload” folder to c:\inetpub\wwwroot <br>
&nbsp; &nbsp; &nbsp; ii. Within c:\inetpub\wwwroot, Rename “upload” to “osTicket” <br>
&nbsp; &nbsp; &nbsp; &nbsp; iii. Reload IIS (Open IIS, Stop and Start the server)


<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/8f336a80-29aa-4c4f-809f-907b2a2db62c" height="60%" width="60%" alt="Install osTicket"/>



6. Go to sites -> Default -> osTicket <br>
&nbsp; A. On the right, click “Browse *:80”

<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/a15d8f6f-8e71-4048-bd3f-5ca1cc1e2b3b" height="60%" width="60%" alt="osTicket"/>

B. Some extensions are not enabled

<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/0f4f976c-4175-4867-a24c-6b27cf1ba397" height="60%" width="60%" alt="osTicket"/>

C. Go back to IIS, sites -> Default -> osTicket -> Double-click PHP Manager -> Click “Enable or disable an extension” <br>
&nbsp; i. Enable: php_imap.dll <br>
&nbsp; &nbsp; ii. Enable: php_intl.dll <br>
&nbsp; &nbsp; &nbsp; iii. Enable: php_opcache.dll

<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/e31cb337-49d3-47e9-9c3c-9bc2f60cdc33" height="60%" width="60%" alt="osTicket"/>


<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/3530d812-9568-4df5-aba0-ed8bfcb44da4" height="50%" width="50%" alt="osTicket"/>


<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/2f52385f-9e7b-4185-a4cc-3a9d194ca3a8 " height="50%" width="50%" alt="osTicket"/>

iv. Refresh the osTicket site in your browse, observe the changes




7. Rename: ost-config.php <br>
&nbsp; A. From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php <br>
&nbsp; &nbsp; i. To: C:\inetpub\wwwroot\osTicket\include\ost-config.php <br>

&nbsp; B. Assign Permissions: ost-config.php <br>
&nbsp; &nbsp; i. Properties -> Security -> Advanced -> Disable inheritance -> Remove All <br>
&nbsp; &nbsp; &nbsp; ii. New Permissions -> Select a Principal -> Everyone -> All


<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/b952bedd-b0d0-4096-af23-dae5e70c909e" height="60%" width="60%" alt="Assign Permissions"/>




8. Continue Setting up osTicket in the browser (click Continue) <br>
&nbsp; A. Name Helpdesk <br>
&nbsp; &nbsp; i. Default email (receives email from customers)


![image](https://github.com/NathanSuguitan/osticket-prereqs/assets/138082246/0f2df8f3-7579-438e-a896-e9c1cd0cc0c5)


9. From the Installation Files, download and install <a href="https://www.heidisql.com/installers/HeidiSQL_12.3.0.6589_Setup.exe">HeidiSQL</a>.

<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/9aa2f60a-034d-439d-9970-23906957b7dd" height="60%" width="60%" alt="Heidi SQL Setup"/>

A. Open Heidi SQL <br>
&nbsp; i. Create a new session, root/Password1 <br>
&nbsp; &nbsp; ii. Connect to the session <br>
&nbsp; &nbsp; &nbsp; iii. Create a database called “osTicket”


<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/e2e5c43a-312b-4a4e-85f8-5d9af1908a8b" height="60%" width="60%" alt="Heidi SQL Setup"/>




10. Continue Setting up osticket in the browser <br>
&nbsp; A. MySQL Database: osTicket <br>
&nbsp; &nbsp; i. MySQL Username: root <br>
&nbsp; &nbsp; &nbsp; ii. MySQL Password: Password1 <br>
&nbsp; &nbsp; &nbsp; &nbsp; iii. Click “Install Now!”


<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/55f7d893-a42a-48a0-b9b1-c9ce1dc96ab3" height="60%" width="60%" alt="osTicket Setup"/>




Congratulations, osTicket is now installed <br>
Browse to your help desk login page: http://localhost/osTicket/scp/login.php

End Users osTicket URL: http://localhost/osTicket/


<img src="https://github.com/M-Bethea/osticket-prereqs/assets/139162550/2d3ccbbc-46d9-4b1b-90e9-a5c1288c2d1a" height="60%" width="60%" alt="osTicket"/>




Clean up <br>
Delete: C:\inetpub\wwwroot\osTicket\setup <br>
!!! Important !!! ONLY DELETE THE SETUP FOLDER <br>
Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php


