<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://youtu.be/LOzmM5ZjKi0?si=zchJ58vGU94uL2qc)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (2H)

<h2>List of Prerequisites</h2>

- Azure Subscription
- Microsoft Remote Desktop (for Mac)/ Remote Desktop Connection (for windows)
- Create an Azure Virtual Machine Windows 10, 4 vCPUs
Name: _______
Username: _______
Password: ____________

Log into the VM with Remote Desktop

Within the VM (osticket-vm), download the [osTicket-Installation-Files.zip](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) and unzip it onto your desktop. The folder should be called “osTicket-Installation-Files”
We will use the files in this folder to install osTicket and some of the dependencies.


<h2>Installation Steps</h2>

<p>
  Install / Enable IIS in Windows WITH CGI
World Wide Web Services -> Application Development Features -> [X] CGI

[<img width="945" alt="Pasted Graphic" src="[https://github.com/user-attachments/assets/b71b3561-4da7-4a2a-b4a5-096270d125e9](https://github.com/user-attachments/assets/4ead6c21-459f-4ad1-bb70-9d146915101f)" />](https://github.com/user-attachments/assets/4ead6c21-459f-4ad1-bb70-9d146915101f)

</p>
<p>
- From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

- From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

- Create the directory C:\PHP

- From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

- From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

- From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)

Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
<p style="color: red; Username: root
Password: root">

</p>
<br />
<img width="604" alt="Image" src="https://github.com/user-attachments/assets/d59f1b0e-26a2-4a7b-800a-63f845629f73" />

- Then create a Root Password (save in notes)
- execute 
</p>
<p>
Open IIS as an Admin

<img width="827" alt="Image" src="https://github.com/user-attachments/assets/4513e333-9943-49e1-8cbf-24427e55eae6" />

Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)

Reload IIS (Open IIS, Stop and Start the server)

https://private-user-images.githubusercontent.com/208532359/436753679-36f266d3-7b6e-4473-ada9-19bd4b539d33.mov?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDU0NDc1NDIsIm5iZiI6MTc0NTQ0NzI0MiwicGF0aCI6Ii8yMDg1MzIzNTkvNDM2NzUzNjc5LTM2ZjI2NmQzLTdiNmUtNDQ3My1hZGE5LTE5YmQ0YjUzOWQzMy5tb3Y_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwNDIzJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDQyM1QyMjI3MjJaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1jODdkOWM1MjNjM2EzNGM1YzAxZDcyMjYxNGI0NGZhNjk5ZjY2OWY0NDIxMmJlMTA3NDRjYzY3ZGMwMTA5MGE0JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.PoGzdRTxFn6cYEDWAUXOBE8M_2L6mcE6WjTyh5tgJsw

Install osTicket v1.15.8
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”

Reload IIS (Open IIS, Stop and Start the server)

Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

Note that some extensions are not enabled
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browser, observe the changes

Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All

Continue Setting up osTicket in the browser (click Continue)
Name Helpdesk
Default email (receives email from customers)

From the “osTicket-Installation-Files” folder, install HeidiSQL.
Open Heidi SQL
Create a new session, root/root
Connect to the session
Create a database called “osTicket”

Continue Setting up osTicket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: root
Click “Install Now!”

Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: http://localhost/osTicket/scp/login.php

End Users osTicket URL:
http://localhost/osTicket/ 

Clean up
Delete: C:\inetpub\wwwroot\osTicket\setup
Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
