<p align="center">
<img src="https://i.imgur.com/50g0PRK.png"/>
</p>

<title>Azure VM and osTicket Installation</title>
</head>
<body>

<!-- Azure VM and osTicket Installation Steps -->

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Item 1
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Azure VM and osTicket Installation Steps</h2>

<h2>Installation Steps</h2>
<ol>
  <li>Create an Azure Virtual Machine Windows 10, 4 vCPUs
    <ul>
      <li>Name: Vm-osticket</li>
      <li>Username: labuser (for example/whatever you chose)</li>
      <li>Password: osTicketPassword1! (for example/whatever you chose)</li>
    </ul>
  </li>

  <li>Open this: <a href="path/to/InstallationFiles">Installation Files</a>
    <p>We will use these files to install osTicket and some of the dependencies. I’m using this offline version to make sure everyone is using the same version of all the files :)</p>
  </li>

  <li>Install/Enable IIS in Windows WITH CGI and Common HTTP Features
    <ul>
      <li>World Wide Web Services -> Application Development Features ->
        <ul>
          <li>[X] CGI</li>
          <li>[X] Common HTTP Features</li>
        </ul>
      </li>
      <li>AND IIS Management Console</li>
      <li>Internet Information Services -> Web Management Tools -> IIS Management Console
        <ul>
          <li>[X] IIS Management Console</li>
        </ul>
      </li>
    </ul>
  </li>

  <li>From the Installation Files, download and install PHP Manager for IIS (<code>PHPManagerForIIS_V1.5.0.msi</code>).</li>

  <li>From the Installation Files, download and install the Rewrite Module (<code>rewrite_amd64_en-US.msi</code>).</li>

  <li>Create the directory <code>C:\PHP</code>.</li>

  <li>From the Installation Files, download PHP 7.3.8 (<code>php-7.3.8-nts-Win32-VC15-x86.zip</code>) and unzip the contents into <code>C:\PHP</code>.
   
<!-- Installation Instructions -->
<h2>osTicket Installation Instructions</h2>

<p>From the Installation Files, download and install <code>VC_redist.x86.exe</code>.</p>

<p>From the Installation Files, download and install MySQL 5.5.62 (<code>mysql-5.5.62-win32.msi</code>)
  <ul>
    <li>Typical Setup</li>
    <li>Launch Configuration Wizard (after install)</li>
    <li>Standard Configuration</li>
    <li>Password1</li>
  </ul>
</p>

<p>Open IIS as an Admin.</p>

<p>Register PHP from within IIS.</p>

<p>Reload IIS (Open IIS, Stop and Start the server).</p>

<p>Install osTicket v1.15.8
  <ul>
    <li>Download osTicket from the Installation Files Folder</li>
    <li>Extract and copy “upload” folder to <code>c:\inetpub\wwwroot</code></li>
    <li>Within <code>c:\inetpub\wwwroot</code>, Rename “upload” to “osTicket”</li>
  </ul>
</p>

<p>Reload IIS (Open IIS, Stop and Start the server).</p>

<p>Go to sites -> Default -> osTicket
  <ul>
    <li>On the right, click “Browse *:80”</li>
  </ul>
</p>

<p>Note that some extensions are not enabled
  <ul>
    <li>Go back to IIS, sites -> Default -> osTicket</li>
    <li>Double-click PHP Manager</li>
    <li>Click “Enable or disable an extension”</li>
    <li>Enable: <code>php_imap.dll</code></li>
    <li>Enable: <code>php_intl.dll</code></li>
    <li>Enable: <code>php_opcache.dll</code></li>
    <li>Refresh the osTicket site in your browse, observe the changes</li>
  </ul>
</p>

<p>Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php</p>

<p>Assign Permissions: ost-config.php
  <ul>
    <li>Disable inheritance -> Remove All</li>
    <li>New Permissions -> Everyone -> All</li>
  </ul>
</p>

<p>Continue Setting up osTicket in the browser (click Continue)
  <ul>
    <li>Name Helpdesk</li>
    <li>Default email (receives email from customers)</li>
  </ul>
</p>

<p>From the Installation Files, download and install HeidiSQL.
  <ul>
    <li>Open Heidi SQL</li>
    <li>Create a new session, root/Password1</li>
    <li>Connect to the session</li>
    <li>Create a database called “osTicket”</li>
  </ul>
</p>

<p>Continue Setting up osTicket in the browser
  <ul>
    <li>MySQL Database: osTicket</li>
    <li>MySQL Username: root</li>
    <li>MySQL Password: Password1</li>
    <li>Click “Install Now!”</li>
  </ul>
</p>

<p>Congratulations, hopefully it is installed with no errors!
  <br>Browse to your help desk login page: <a href="http://localhost/osTicket/scp/login.php">http://localhost/osTicket/scp/login.php</a></p>

<p>End Users osTicket URL:
  <br><a href="http://localhost/osTicket/">http://localhost/osTicket/</a></p>

<p>Clean up
  <ul>
    <li>Delete: C:\inetpub\wwwroot\osTicket\setup</li>
    <li>Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php</li>
  </ul>
</p>

<p>Notes:
  <br>Browse to your help desk login page: <a href="http://localhost/osTicket/scp/login.php">http://localhost/osTicket/scp/login.php</a>
  <br>End Users osTicket URL: <a href="http://localhost/osTicket/">http://localhost/osTicket/</a></p>




  

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
