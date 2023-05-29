<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
In this tutorial, I will guide you through the process of setting up osTicket on a Azure VM(virtual machine). This tutorial assumes you have a VM set up with at least 2 virtual CPUs and logged into with remote desktop so please create a VM before continuing. This VM will be utilized as our server where ticket requests come through. Here are the necessary <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">installation files</a> needed. (Note: For some reason edge is preventing you from installing certain files so please use chrome to download these files) <br />

</p>
<img src="https://i.imgur.com/rdRhPQQ.png" height="80%" width="80%"/>
</p>



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- MySQL

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)


<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/4lljPqX.png" height="80%" width="80%"/>
</p>
<p>
First we are going to enable IIS (internet information services). To do that go to Control Panel > Programs > Turn Windows Features On or Off > Click and Expand Internet Information Services > cliack and expand Web and Managment Tools > Check IIS Managment Console > Click and expand World Wide Web Services > Click and expand Applicaction Developement Features > Check CGI > Click Ok.
</p>
<br />

<p>
<img src="https://i.imgur.com/6pToNtB.png" height="80%" width="80%"/>
</p>
<p>
Download/install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) from the <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">installation files</a>.
</p>
<br />

<p>
<img src="https://i.imgur.com/5VVPcJO.png" height="80%" width="80%"/>
</p>
<p>
Create the directory C:\PHP on the root of the (C:) Drive. To do this open File Explorer > This PC > Windows (C:) Drive > Right Click to add a new folder > rename it to "PHP".
</p>
<br />

<p>
<img src="https://i.imgur.com/UD916BS.png" height="80%" width="80%"/>
</p>
<p>
Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) then unzip into C:PHP (the new folder you just created)
</p>
<br />

<p>
<img src="https://i.imgur.com/nKOjKNb.png" height="80%" width="80%"/>
</p>
<p>
Download/install VC_redist.x86.exe.
</p>
<br />

<p>
<img src="https://i.imgur.com/70lv1s0.png" height="80%" width="80%"/>
</p>
<p>
<img src="https://i.imgur.com/asNlqbU.png" height="80%" width="80%"/>
</p>
<p>
<img src="https://i.imgur.com/ztnjCF7.png" height="80%" width="80%"/>
</p>
<p>
Download/Install MySQL 5.5.62 (mysql-5.5.62-win32.msi) Double click > Click I "agree" > select TYPICAL > INSTALL Launch configuration Wizard (after install). Select STANDARD CONFIGURATION > Select INSTALL AS WINDOWS SERVICE (make sure "Launch my sql server..." is checked) > "Root" is the default username, create any password ex: "Password1".
</p>
<br />

<p>
<img src="https://i.imgur.com/YCw16Dc.png" height="80%" width="80%"/>
</p>
<p>
<img src="https://i.imgur.com/qkCppgS.png" height="80%" width="80%"/>
</p>
<p>
<img src="https://i.imgur.com/K0s5eyn.png" height="80%" width="80%"/>
</p>
<p>
<img src="https://i.imgur.com/oJOQaDh.png" height="80%" width="80%"/>
</p>
<p>
<img src="https://i.imgur.com/Ylevyd9.png" height="80%" width="80%"/>
</p>
<p>
Open IIS as an Admin, register PHP, restart the server. Tpe IIS in start menu > Click on RUN AS ADMINISTRATOR > Select PHP MANAGER > Select Register new PHP Version > Click BROWSE(three dots) > Select PHP CGI in the PHP folder located in the (C:) Drive (make sure php is exectuable). > OK > Click RESTART.
</p>
<br />

<p>
<img src="https://i.imgur.com/AGrXGi5.png" height="80%" width="80%"/>
</p>
<p>
<img src="https://i.imgur.com/muyLsUs.png" height="80%" width="80%"/>
</p>
<p>
Install osTicket v1.15.8 and drag the "UPLOAD" folder into wwwroot folder and rename the "UPLOAD" folder to "osTicket"
</p>
<br />

<p>
<img src="https://i.imgur.com/Y9l4sMb.png" height="80%" width="80%"/>
</p>
<p>
<img src="https://i.imgur.com/cIFOPcH.png" height="80%" width="80%"/>
</p>
<p>
Open IIS > Click RESTART > Sites > Default > osTicket (double-click) > Browse 80*
</p>
<br />

<p>
<img src="https://i.imgur.com/MyBqXGG.png" height="80%" width="80%"/>
</p>
<p>
<img src="https://i.imgur.com/hyVyaK0.png" height="80%" width="80%"/>
</p>
<p>
<img src="https://i.imgur.com/JiC2NYZ.png" height="80%" width="80%"/>
</p>
<p>
If everything was done correctly you should have ended up ast the osTicket webpage. NOTE: PHP extensions are disbaled to enable PHP extensions, go back to IIS > Sites > Default Web Site > osTicket > php manager > Click on enable or disable PHP extensions. Scroll down the list to find: Php_imap.dil, Php_intl.dil, Php_opache.dil. Click enable exstensions and restart the server. Notice when you go back to the osTicket site there are 2 new green check marks and only 2 red X's left.
</p>
<br />

<p>
<img src="https://i.imgur.com/riCIv1E.png" height="80%" width="80%"/>
</p>
<p>
Before continuing on osTicket, go back and download/install HeidiSQL.
</p>
<br />
