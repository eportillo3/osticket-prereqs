<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This is a walkthrough/tutorial that outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. At the end of this walkthrough, we will have an admin/analyst login page and an end users osTicket URL.<br />


<h2>Environments Used</h2>

- Microsoft Azure
- macOS (Host Machine)
- Windows 10 (Virtual Machine)
- Windows App (Remote Desktop)
- Internet Information Services (IIS)

<h2>Technology/Applications/Services </h2>

- osTicket
- Azure Virtual Machines
- MySQL
- HeidiSQL
- PHP Manager for IIS



<h2>Walkthrough</h2>



Go to the azure portal and go to the Virtual Machine to Create a new virtual machine.
  
<img width="2524" height="1366" alt="image" src="https://github.com/user-attachments/assets/5447b1c9-890c-48a9-a23d-7b528622a940" />
</p>
<br />
<p>
Create a new virtual machine -  Windows 10, 2 vCPUs
  


<img width="2124" height="1296" alt="image" src="https://github.com/user-attachments/assets/dc7fdaa1-9f10-4abc-b66d-a02be0913906" />

</p>
<br />
<p>
Use Windows App(Remote Desktop) to log in to the new VM we created
</p>



<img width="2314" height="1418" alt="image" src="https://github.com/user-attachments/assets/1da0c5ba-4bbc-4995-93d2-a88a4fe0daa3" />
</p>
<br />
<p>
Download the following: osTicket-Installation-Files.zip -> (https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- It contains all the necessary files to install osTicket and some of its dependencies
</p>



<img width="1708" height="1028" alt="image" src="https://github.com/user-attachments/assets/7f97fbbc-ebba-4262-b547-73db3bb9b433" />
</p>
<br />
<p>
Extract/Unzip to access the files on our desktop
</p>



<img width="2078" height="1572" alt="image" src="https://github.com/user-attachments/assets/c0e21e28-c869-4ad8-88b2-2bb2e1936525" />
</p>
<br />
<p>
Need to Install/Enable IIS in Windows<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- Click on Windows start menu -> Control Panel -> Programs -> Turn Windows features on or off -> Check Internet Information services
</p>



<img width="1152" height="604" alt="image" src="https://github.com/user-attachments/assets/cc8c09ba-eb4f-4599-a3f4-c7f8118b7db1" />
</p>
<br />
<p>
Install CGI<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- Expand Internet Information Services -> Worldwide Web Services - Application Development Features -> CGI
</p>



<img width="852" height="598" alt="image" src="https://github.com/user-attachments/assets/da540ec5-8c47-471e-a035-f93f33f1173b" />
<br />
  *Computer is technically a Web server after this step.
</p>
<br />
<p>
From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
</p>



<img width="532" height="266" alt="image" src="https://github.com/user-attachments/assets/2b4fb274-5562-44c0-ab89-31809e85eab3" />
</p>
<br />
<p>
From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

</p>



<img width="532" height="254" alt="image" src="https://github.com/user-attachments/assets/e9fffb10-1190-4ae9-bf21-38f60f965c6d" />
</p>
<br />
<p>
Create the new directory C:\PHP
  
</p>



<img width="438" height="416" alt="image" src="https://github.com/user-attachments/assets/4dfd238f-3885-4134-8e72-00e8518181fc" />
</p>
<br />
<p>
From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder
</p>



<img width="778" height="388" alt="image" src="https://github.com/user-attachments/assets/21059e5b-9792-4c35-b757-3b8515bee393" />
</p>
<br />
<p>
From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.
</p>



<img width="740" height="238" alt="image" src="https://github.com/user-attachments/assets/71269b31-38e2-4f9e-9bb5-62f823157c71" />
</p>
<br />
<p>
From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
- Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration ->

</p>



<img width="1084" height="582" alt="image" src="https://github.com/user-attachments/assets/338e1dab-da9f-4b7e-b3d4-855115590e65" />
</p>
<br />
<p>
Username: root | Password: root

</p>



<img width="710" height="264" alt="image" src="https://github.com/user-attachments/assets/edb9f80f-c4ff-4d68-9aac-8f0c73f6c1e5" />
</p>
<br />
<p>
Open IIS as an Admin
</p>



<img width="1240" height="962" alt="image" src="https://github.com/user-attachments/assets/c5535f9e-7ade-4ba9-a87f-738ab8ce7f37" />
</p>
<br />
<p>
Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)
</p>



<img width="608" height="706" alt="image" src="https://github.com/user-attachments/assets/92d45b75-4dd7-4a37-9a25-fdbfe405ecab" />
</p>
<br />
<p>
Reload IIS (Open IIS, Stop and Start the server)
</p>



<img width="608" height="388" alt="image" src="https://github.com/user-attachments/assets/bc25b614-ecfc-4a92-8bb9-f6aff51834d9" />
</p>
<br />
<p>
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”

</p>


<img width="594" height="692" alt="image" src="https://github.com/user-attachments/assets/5500d5b1-d695-42db-b9e5-b86ddb82822d" />
</p>
<br />
<p>
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
</p>



<img width="946" height="896" alt="image" src="https://github.com/user-attachments/assets/51cf85a9-5b9d-4d5d-9679-e5f65b6d41be" />
</p>
<br />
<p>
Reload IIS (Open IIS, Stop and Start the server)
</p>



<img width="594" height="494" alt="image" src="https://github.com/user-attachments/assets/3da6de48-d28d-4d43-94af-9b80661b9bb5" />
</p>
<br />
<p>
Go to sites -> Default -> osTicket -> On the right, click “Browse *:80”
</p>



<img width="608" height="356" alt="image" src="https://github.com/user-attachments/assets/e5d61971-4bdb-4e12-aa91-8c63c6ef50e5" />
</p>
<br />
<p>
Some important extensions are not enabled:<br />
Go back to IIS, sites -> Default -> osTicket -> Double-click PHP Manager<br />
Click “Enable or disable an extension”<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- Enable: php_imap.dll<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- Enable: php_intl.dll<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- Enable: php_opcache.dll<br />

</p>



<img width="602" height="596" alt="image" src="https://github.com/user-attachments/assets/372b13db-a080-448e-9561-531e88cfdaea" />
</p>
<br />
<p>
Refresh the osTicket site in your browser, observe the changes
</p>



<img width="592" height="588" alt="image" src="https://github.com/user-attachments/assets/a902c294-339d-45f6-985a-f202120f2f48" />
</p>
<br />
<p>
Rename: ost-config.php:<br />
-From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php<br />
-To: C:\inetpub\wwwroot\osTicket\include\ost-config.php<br />

</p>



<img width="446" height="410" alt="image" src="https://github.com/user-attachments/assets/128b8b71-7d20-4bf5-881f-3306f5f4236f" />
</p>
<br />
<p>
Right click “ost-config.php” -> Properties -> Security -> Advanced -> Disable inheritance -> Remove All
</p>



<img width="686" height="436" alt="image" src="https://github.com/user-attachments/assets/3d4eb1fd-8af8-46fa-8a1f-44a800fea605" />
</p>
<br />
<p>
“Add” New Permissions -> Principal -> Enter the object name to select “Everyone” 
-> Check All

</p>



<img width="774" height="436" alt="image" src="https://github.com/user-attachments/assets/23073b77-85bc-45ce-96f9-2b953c08b0e8" />
</p>
<br />
<p>
Continue Setting up osTicket in the browser (click Continue)<br />
- Name Helpdesk<br />
- Default email (receives email from customers)<br />
- Fill out Admin User<br />

</p>



<img width="536" height="606" alt="image" src="https://github.com/user-attachments/assets/66e35f01-415e-4790-b66b-337fd56bf977" />
</p>
<br />
<p>
From the “osTicket-Installation-Files” folder, install HeidiSQL.
</p>


<img width="656" height="308" alt="image" src="https://github.com/user-attachments/assets/dec687c0-da15-4eeb-9aa4-6e9df3893111" />
</p>
<br />
<p>
 - Open Heidi SQL<br />
 - Create a new session, root/root<br />
 - Connect to the session<br />
</p>



<img width="450" height="306" alt="image" src="https://github.com/user-attachments/assets/c10592ba-ee9e-4b19-acee-6b02c1cdc73e" />
</p>
<br />
<p>
Create a database called “osTicket”
</p>



<img width="594" height="410" alt="image" src="https://github.com/user-attachments/assets/22bda40f-d858-4e1b-a7a9-06841c5786b1" />
</p>
<br />
<p>
Continue Setting up osTicket in the browser<br />
 - MySQL Database: osTicket<br />
 - MySQL Username: root<br />
 - MySQL Password: root<br />
 - Click “Install Now!”<br />

</p>



<img width="558" height="374" alt="image" src="https://github.com/user-attachments/assets/4f2977d6-9e57-45a6-aba4-8300bb275de5" />
</p>
<br />
<p>
osTicket is successfully installed

</p>



![image alt](https://github.com/GursimarJ/osticket-prereqs/blob/3aa63ace8696e2ae2179e4b207b4a90a6cf0f978/assets/Part1Pic32.png)
