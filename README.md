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
<p>Before we install anything, we need enable Internt information Services. This allows the virtual machine to fuction as a websever.
Open control panel and navigate to "Programs" -> "Turn Windows Features on or off"
 <img src="https://user-images.githubusercontent.com/98138436/226057548-e5c9a6f5-a02a-44b5-a167-bec2863400d1.jpg"/>


