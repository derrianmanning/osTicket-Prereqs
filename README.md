<div align="center">
        <h1 style="font-weight: bold;">Azure VM and osTicket Installation</h1>
        <img src="https://i.imgur.com/50g0PRK.png" alt="Image Description"/>
    </div>

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

- Active Azure acccount & subscription
- Resource Group for Virtual Network
- Microsoft Remote Desktop.app (Mac Users)

<h2>Azure VM and osTicket Installation Steps</h2>

<h2>Installation Steps</h2>
<div style="text-align: center;">
<img src="https://i.imgur.com/S1MHooT.png" width="50%" alt="Reduced Size Image"/>
<img src="https://i.imgur.com/JEgZAaq.png" width="50%" alt="Reduced Size Image"/>
</div>
<ol>
  <li>Create an Azure Virtual Machine Windows 10, 2 or 4 vCPUs
    <ul>
      <li>Click "Create" or "Search" for Virtual Machine</li>
      <li>Name: xxxx (e.g. osTicket-Lab)</li>
      <li>Username: xxxx (e.g. admin_user)</li>
      <li>Password: xxxx (e.g. Password1234!)<li>Confirm Licensing
      <li>(Optional) Set-up auto-shutdown>Management
      <li>Review & Create
    </ul>
  </li>

<div style="text-align: center;">
    <img src="https://i.imgur.com/11cUJij.png" width="50%" alt="Image 1">
    <img src="https://i.imgur.com/VxQM2rv.png" width="50%" alt="Image 2">
    <p>Windows & Mac Remote Desktop Connection Portals</p>
</div>
<li>Log On to VM</li>
  <ul>
    <li>Copy public IP Address (Resource group > "Virtual Machine")</li>
    <li>Access Remote Desktop & connect using the IP</li>
    <li>Login with created credentials</li>
  </ul>
  <div style="text-align: center;">
    <img src="https://i.imgur.com/NGVMM0U.png" width="50%" alt="Image 2">
</div>
<li>Install/Enable IIS in Windows VM with CGI and Common HTTP Features
  <ul>
    <li>Control Panel -> Programs -> Turn Windows Features on/off</li>
    <li>Internet Information Services -> World Wide Web Services -> Application Development Features ->
      <ul>
        <li>[X] CGI</li>
        <li>[X] Common HTTP Features</li>
      </ul>
    </li>
  </ul>
</li>
<li>Install/Enable IIS Management Console
      <ul>
        <li>Internet Information Services -> Web Management Tools -> IIS Management Console
          <ul>
            <li>[X] IIS Management Console</li>
          </ul>
        </li>
      </ul>
    </li>
  </ul>
  <div style="text-align: center;">
    <img src="https://i.imgur.com/VUSKHrh.png" width="50%" alt="Image 2">
</div>
</li>Verify configuration. Open browser and visit 127.0.0.1
 <li>From the Installation Files, download and install PHP Manager for IIS (<code>PHPManagerForIIS_V1.5.0.msi</code>).</li>

  <li>From the Installation Files, download and install the Rewrite Module (<code>rewrite_amd64_en-US.msi</code>).</li>
<div style="text-align: center;">
    <img src="https://i.imgur.com/hB20dE5.png" width="50%" alt="Image 2">
</div>
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
    <li>Server Name: osTicket SQL</li>
    <li>Password1234!</li>
  </ul>
</p>

<p>Open IIS as an Admin.</p>
<div style="text-align: center;">
    <img src="https://i.imgur.com/yTnqZwi.png" width="50%" alt="Image 2">
</div>
<p>Register PHP from within IIS.
  <ul>
    <li>PHP Manager </li>
    <li>Register new PHP version </li>
    <li>C: -> PHP -> php-cgi
  </ul>
</p>
<p>Reload IIS (Open IIS, Stop and Start the server).
  <ul>
      <li>Go to osTicket Home
      <li>Click restart on right side
  </ul>    
</p>

<p>Install osTicket v1.15.8
  <ul>
    <li>Download osTicket from the Installation Files Folder</li>
    <li>Extract and copy “upload” folder to <code>c:\inetpub\wwwroot</code></li>
    <li>Within <code>c:\inetpub\wwwroot</code>, Rename “upload” to “osTicket”</li>
  </ul>
</p>

<p>Restart IIS (or Stop and Start the server).</p>

<p>With/in IIS go to sites -> Default -> osTicket
  <ul>
    <li>On the right, click “Browse *:80”</li>
  </ul>
</p>
<div style="text-align: center;">
    <img src="https://i.imgur.com/KAAkMPo.png" width="50%" alt="Image 2">
</div>
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
  <ul>
    <li>From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
    <li>To: C:\inetpub\wwwroot\osTicket\include\ost-config.php</p>
  </ul> 
  <div style="text-align: center;">
    <img src="https://i.imgur.com/wfqZlj6.png" width="50%" alt="Image 2">
</div>
<p>Assign Permissions: ost-config.php
  <ul>
    <li>Disable inheritance - Right click -> Properties -> Security -> Advanced -> Disable inheritance</li>
    <li>New Permissions - Add -> Select a principal -> "everyone" -> OK -> Full Control -> OK & Apply</li>

  </ul>
</p>

<p>Continue Setting up osTicket in the browser (click Continue)
  <ul>
    <li>Name Helpdesk (e.g. HelpdeskCO)</li>
    <li>Default email (receives email from customers)</li>
    <li>Complete Admin User
    <li>STOP - Proceed to next step
  </ul>
</p>
 <div style="text-align: center;">
    <img src="https://i.imgur.com/uSPKDXi.png" width="50%" alt="Image 2">
</div>
<p>From the Installation Files, download and install HeidiSQL.
  <ul>
    <li>Open Heidi SQL</li>
    <li>Create a new session, root/Password1234!</li>
    <li>Connect to the session (selecting OK)</li>
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
<div style="text-align: center;">
    <img src="https://i.imgur.com/k1eZVl2.png" width="50%" alt="Image 2">
<div>

  <br>Browse to your help desk login page: 
    <br><a href="http://localhost/osTicket/scp/login.php">http://localhost/osTicket/scp/login.php</a></p>

<p>End Users osTicket URL:
  <br><a href="http://localhost/osTicket/">http://localhost/osTicket/</a></p>
<div>
  </ul>
</li>
<ul>Clean up
    <li>Delete: C:\inetpub\wwwroot\osTicket\setup</li>
    <li>Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
    <ul> Right Click -> Proterties-> Security -> Advanced -> Edit "Everyone" -> Read/Read & Execute-> OK/Apply
