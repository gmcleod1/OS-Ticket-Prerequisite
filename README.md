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

<h2>Part 1: Prerequisites</h2>

- Enablinging IIS with CGI in windows
- Installing PHP manager for IIS
- Installing Rewrite Muule
- Installing vcredist_x86.exe
- Intalling MySQL
- Setting up osTicket
- Installing HeidiSQL
- Finising Touches


<h2>Video Explination</h2>
 <a href="https://www.youtube.com/watch?v=TDIyxhJxF_U"> Watch on youtube</a>


<h2>Installation Steps</h2>


<p>This tutorial assumes that you know how to set up and log into an Azure virtual machine and have already logged in. The files used in this tutorial can be found <a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">here</a></p>

<hr>
<p>Before we install anything, we need enable Internet information Services. This allows the virtual machine to fuction as a websever.
Open control panel and navigate to "Programs" -> "Turn Windows Features on or off"</p>

 <img src="https://user-images.githubusercontent.com/98138436/226057548-e5c9a6f5-a02a-44b5-a167-bec2863400d1.jpg"/>
 <br>
 
 <p>Navigate to and select Internet Information Services. The expand IIS->World Wide Web Services->Application Development Features-> and select cgi</p>
 

 <div class="row">
  <div class="column">
    <img src="https://user-images.githubusercontent.com/98138436/226058675-3cc30656-6d49-449e-a71c-46d097a57faf.jpg" alt="WWWsettings" style="width:50%">
  </div>
  <div class="column">
    <img src="https://user-images.githubusercontent.com/98138436/226059011-bee98b15-02b4-40c1-a310-40b84527219e.jpg" alt="CGI" style="width:50%">
  </div>
</div> 
<br>
<hr>
<p>Next Install php manager for IIS (PHPManagerForIIS_V1.5.0) and rewrite module (rewrite_amd64_en-US.msi) from the dowload link.</p>
<br>
<hr>
<br>
<p>Next create a PHP directory on the C drive.
 <br>
 Navigate to C: and create a new file called "PHP"</p>
 
 <img src="https://user-images.githubusercontent.com/98138436/226067200-c60c3d1f-cc86-4fc0-8d4d-f758d31c9593.jpg" style="width:80%"/>

<br>
<p>Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and "Extract all" to unzip the contents into C:\PHP</p>
 <img src="https://user-images.githubusercontent.com/98138436/226068342-b7069bbc-7e56-44ce-a987-b356ac4df9c1.jpg">

<p>From the Installation Files, download and install VC_redist.x86.exe</p>
<img src="https://user-images.githubusercontent.com/98138436/226070047-05d739b3-d31d-488d-bf55-e3a026a48eac.jpg"/>


<p>Then download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) use a typical install and remember the password you selected</p>
<img src="https://user-images.githubusercontent.com/98138436/226072507-462beddb-8cb7-4a50-8735-6b99cd224949.jpg"/>
<img src="https://user-images.githubusercontent.com/98138436/226072552-3161beba-c125-4d87-8373-6615970240bf.jpg"/>
<br> 
<p> Run IIS as an admin <br>
 Click on "PHP manager" then "Register new PHP version"<br>
 <img src="https://user-images.githubusercontent.com/98138436/226075009-8a9b50f5-9126-4ce1-9a0c-f36301b957a7.jpg"/>
<br>
 <img src="https://user-images.githubusercontent.com/98138436/231800355-7d677338-36e6-4f76-8fb8-ae68caa4c90a.jpg"/>

 Navigate to "php-cgi" in the PHP folder that was created earlier<br>
 </p>
<img src="https://user-images.githubusercontent.com/98138436/226075151-f50565ac-7d2c-42d1-926c-88af98b1e818.jpg"/>
<br>
<p>Download osTicket and extract the files<br>
 copy the "upload" file and navigate to C:->inetpub->wwwroot and paste the file<br>
 Next rename "upload" to "osTicket"</p>
 <img src="https://user-images.githubusercontent.com/98138436/226076266-8c417396-1897-410d-8817-26b7e46ca543.jpg"/><br>
 
 <p>Enable some extentions that we need for osTicket<br>
 Go back to IIS and navigate to sites-> deault-> osTicket, and double click "PHP Manager" and the finally "enable or Disable extention<br>
 
 <img src="https://user-images.githubusercontent.com/98138436/227389216-6b55ea20-35c7-4e61-851f-105ea4efa8c7.jpg"/><br>
 
 The extention we want to enable are: php_imap.dll, php_intl.dll, php_opcache.dl. Right click and select Enable to enable them<br>
 
 <img src="https://user-images.githubusercontent.com/98138436/227389741-0a21f9c1-5cfa-411f-b75a-4c33ac11188a.jpg"/><br>

 


<p>Navigate to C->inetpub->wwwroot-> osTicket-> include and rename "ost-sampleconfig.php" to "ost-confing.php"</p><br>
<img src="https://user-images.githubusercontent.com/98138436/227389809-79cf2c32-25b8-4590-934f-021f257bf30c.jpg"/><bbr>
 
 <p>Next we have to change permissions on ost-config.php by right clicking the file and navigate to-> properties-> Security tab-> advanced-> disable inheritance </p><br>
 
  <img src="https://user-images.githubusercontent.com/98138436/227443660-f1857936-3ef7-49a7-88e5-16f8256c5a40.jpg"/>
 
 Next click add then "Select a Principal" type everyone in the user box then select full control
 
 <img src="https://user-images.githubusercontent.com/98138436/227450131-cb5202b1-d0dc-4912-8043-ae1a279a3b6e.jpg"/>

<p>Go back to the IIS home page and restart IIS <br>
 
 <img src="https://user-images.githubusercontent.com/98138436/226075727-363ab297-139d-498c-94bf-1ee2828cba37.jpg"/> <br></p>
 
 <p>In IIS right click the osTicket folder in the navigation menu and then mouse down to manage folder then browse</p><br>
 <img src="https://user-images.githubusercontent.com/98138436/227454029-c025a094-3906-413e-abc3-d31d540073d9.jpg"/><br>
 


Continue Setting up osTicket in the browser (click Continue)

Fill out the information on this page. The email addresses do not have to be real, but you do need to remember the admin user name and password for when you log in<img src="https://user-images.githubusercontent.com/98138436/231706735-ed1d5a3c-c582-4332-a5e5-f869ef3d315c.jpg"/>

Next we have to connect to the sql database that we set up earlier, download Heidi sql from the installation files.
Open Heidi SQL and connect a new session. Rename the session"osTicket" 
User is root and the password is the password you used during the mysql set-up

Finish setting up osTicket by filling out the MySQL settings in the browser 
<img src="https://user-images.githubusercontent.com/98138436/231729633-1bba91ed-5c8f-4d4d-b523-40c625af66c9.jpg"/>



Hit "Install Now" and hopefully it is installed with no errors!
Browse to your help desk login page: http://localhost/osTicket/scp/login.php

End Users osTicket URL:
http://localhost/osTicket/ 

Clean up
Delete: C:->inetpub->wwwroot->osTicket->setup
Set Permissions to “Read” only: C:->inetpub->wwwroot->osTicket->include->ost-config.php




