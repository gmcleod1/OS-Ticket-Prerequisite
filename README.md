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


<h2>Installation Steps</h2>

<p>

</p>

<p>This tutorial assumes that you know how to set up and log in to an Azure virtual machine and have already logged in. The files used in this yutorial can be found <a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">here</a></p>

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

 Navigate to "php-cgi" in the PHP folder that was created earlier<br>
 </p>
<img src="https://user-images.githubusercontent.com/98138436/226075151-f50565ac-7d2c-42d1-926c-88af98b1e818.jpg"/>
<br>
<p>Download osTicket and extract the files<br>
 copy the "upload" file and navigate to C:->inetpub->wwwroot and paste the file<br>
 Next rename "upload" to "osTicket"</p>
 <img src="https://user-images.githubusercontent.com/98138436/226076266-8c417396-1897-410d-8817-26b7e46ca543.jpg"/><br>
<p>Navigate to C->inetpub->wwwroot-> osTicket-> include and rename "ost-sampleconfig.php" to "ost-confing.php"</p><br>



<p>Go back to the IIS home page and restart IIS <br>
 <img src="https://user-images.githubusercontent.com/98138436/226075727-363ab297-139d-498c-94bf-1ee2828cba37.jpg"/> <br>

 



