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

  <title>osTicket Setup Instructions</title>
</head>
<body>

<!-- Setup Instructions -->
<h2>osTicket Setup Instructions</h2>

<p>From the Installation Files, download PHP 7.3.8 (<code>php-7.3.8-nts-Win32-VC15-x86.zip</code>) and unzip the contents into <code>C:\PHP</code>.</p>
<p>!! ATTENTION !! If this appears, choose to “Keep” the file:</p>
<p>[Image of attention prompt]</p>
<p>If you are still having trouble downloading PHP 7.3.8, please try downloading and installing Google Chrome and doing it from within there.</p>

<p>From the Installation Files, download and install <code>VC_redist.x86.exe</code>.</p>

<p>From the Installation Files, download and install MySQL 5.5.62 (<code>mysql-5.5.62-win32.msi</code>).
Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration -> Password1</p>

<p>Open IIS as an Admin.</p>

<p>Register PHP from within IIS.</p>

<p>Reload IIS (Open IIS, Stop and Start the server).</p>

<p>Install osTicket v1.15.8.
<p>Download osTicket from the Installation Files Folder.</p>
<p>Extract and copy “upload” folder to <code>c:\inetpub\wwwroot</code>.</p>
<p>Within <code>c:\inetpub\wwwroot</code>, Rename “upload” to “osTicket”.</p>

<p>Reload IIS (Open IIS, Stop and Start the server).</p>

<p>Go to sites -> Default -> osTicket.
<p>On the right, click “Browse *:80”.</p>

<p>Note that some extensions are not enabled.
<p>Go back to IIS, sites -> Default -> osTicket.</p>
<p>Double-click PHP Manager.</p>
<p>Click “Enable or disable an extension”.</p>
<p>Enable: <code>php_imap.dll</code>.</p>
<p>Enable: <code>php_intl.dll</code>.</p>
<p>Enable: <code>php_opcache.dll</code>.</p>
<p>Refresh the osTicket site in your browse, observe the changes.</p>

<p>Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php</p>

<p>Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All</p>

<p>Continue Setting up osTicket in the browser (click Continue)
Name Helpdesk
Default email (receives email from customers)</p>

<p>From the Installation Files, download and install HeidiSQL.
<p>Open Heidi SQL</p>
<p>Create a new session, root/Password1</p>
<p>Connect to the session</p>
<p>Create a database called “osTicket”</p>

<p>Continue Setting up osTicket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: Password1
Click “Install Now!”</p>

<p>Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: <a href="http://localhost/osTicket/scp/login.php">http://localhost/osTicket/scp/login.php</a></p>

<p>End Users osTicket URL:
<a href="http://localhost/osTicket/">http://localhost/osTicket/</a></p>

<p>Clean up
Delete: C:\inetpub\wwwroot\osTicket\setup
Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php</p>

<p>Notes:
Browse to your help desk login page: <a href="http://localhost/osTicket/scp/login.php">http://localhost/osTicket/scp/login.php</a>
End Users osTicket URL: <a href="http://localhost/osTicket/">http://localhost/osTicket/</a></p>

</body>
</html>

  <!-- Other steps... -->




  

</ol>

</body>
</html>

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

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
