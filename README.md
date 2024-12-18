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

- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8

<h2>Installation Steps</h2>

1.) In Control Panel, go to Programs > Turn Windows features on or off, and check these: World Wide Web Services > Application Development Features > CGI
Common HTTP Features (check all)

<p>
<img src="https://i.imgur.com/JGOybPN.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
2.) You will want to install / enable IIS in Windows with CGI and Common HTTP Features

World Wide Web Services -> Application Development Features -> [X] CGI [X] Common HTTP Features
<p>
<img src="https://i.imgur.com/54JKrcL.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
3.) Download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) and follow the steps.
  
4.) Download and install the Rewrite Module (rewrite_amd64_en-US.msi).
  
5.) Within the Root of your C: drive, create a folder named 'PHP'

6.) Download PHP 7.3.8 and extract it into the C:\PHP folder.

https://github.com/user-attachments/assets/241fa2c7-1b9c-4a04-b15b-b8b4aca4e5b7

7.) Download and run the VC_redist.x86.exe installer.
  
8.) Download and install MySQL 5.5.62. Use the wizard to set up a root password as root.
  
https://github.com/user-attachments/assets/4c933239-d9f4-4ea0-b67c-78a17fe0fa6c

9.) Launch IIS via the Start menu and open it as administrator.
  
<p>
<img src="https://imgur.com/rgdZwmM.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
10.) In IIS, go to PHP Manager > Register New PHP Version. Select php-cgi.exe from C:\PHP and restart IIS.
  
<p>
<img src="https://imgur.com/vvTLNBH.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
<p>
<img src="https://imgur.com/qdbn5zQ.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
<p>
<img src="https://imgur.com/oJZ0gp9.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
<p>
<img src="https://imgur.com/CJ3RUbG.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
11.) Download osTicket v1.15.8, extract the "upload" folder, and copy it to C:\inetpub\wwwroot. Rename "upload" to "osTicket".
  
  Reload IIS again.
  
12.) On IIS go to sites -> Default -> osTicket
  -On the right, click “Browse *:80”
  
<p>
<img src="https://imgur.com/Yw55d5b.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Some extensions are not enabled on the osTicket browser.
  
<p>
<img src="https://imgur.com/eJIsGTn.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
 In IIS, go to Default > osTicket > PHP Manager > Enable or disable an extension.
Enable these extensions:
php_imap.dll
php_intl.dll
php_opcache.dll

  
<p>
<img src="https://imgur.com/vvTLNBH.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/uigyKjb.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  

  
<p>
<img src="https://imgur.com/cOem7Nb.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
13.) Go to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php, rename it to ost-config.php.
Set permissions to Full Control for "Everyone".
  
  
  Disable inheritance for ost-config.php and add new permissions.
  
<p>
<img src="https://imgur.com/VPZvOdo.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
<p>
<img src="https://imgur.com/PoGk34d.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
  
<p>
<img src="https://imgur.com/F4H3ppM.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
<p>
<img src="https://imgur.com/rbbGqwB.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

  Click apply & ok.
  
<p>
<img src="https://imgur.com/saRO3y5.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  In the browser, fill out the osTicket setup page (skip Database Settings for now).
  
  Download HeidiSQL, create a new session, and connect using username root and password root. In HeidiSQL, create a new database called osTicket.
  
<p>
<img src="https://imgur.com/i7a4gWC.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
<p>
<img src="https://imgur.com/g5M1i61.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
<p>
<img src="https://imgur.com/LEAZNOc.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  In the browser setup, set MySQL details: username root, password root, and database osTicket.
  
<p>
<img src="https://imgur.com/0rG1AJm.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
 Delete the setup folder in C:\inetpub\wwwroot\osTicket.
Set permissions for ost-config.php to Read Only.
  
<p>
<img src="https://imgur.com/wFr0pkK.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/jsJOPyn.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
 Open osTicket in the browser and log in.
  
<p>
<img src="https://imgur.com/uHVdDsx.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Congratulations! Your osTicket is set up!
