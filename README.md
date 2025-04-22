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
Name: osticket-vm / ?
Username: labuser / ?
Password: osTicketPassword1! / ?

Log into the VM with Remote Desktop

Within the VM (osticket-vm), download the [osTicket-Installation-Files.zip](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) and unzip it onto your desktop. The folder should be called “osTicket-Installation-Files”
We will use the files in this folder to install osTicket and some of the dependencies.

- Item 5

<h2>Installation Steps</h2>

<p>
  Install / Enable IIS in Windows WITH CGI
World Wide Web Services -> Application Development Features -> [X] CGI

[<img width="945" alt="Pasted Graphic" src="[https://github.com/user-attachments/assets/b71b3561-4da7-4a2a-b4a5-096270d125e9](https://github.com/user-attachments/assets/4ead6c21-459f-4ad1-bb70-9d146915101f)" />](https://github.com/user-attachments/assets/4ead6c21-459f-4ad1-bb70-9d146915101f)

</p>
<p>
From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

Create the directory C:\PHP

From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Username: root
Password: root

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
