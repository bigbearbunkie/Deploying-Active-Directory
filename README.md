<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>

This tutorial outlines the installation and deployment of on-premises Active Directory within Azure Virtual Machines, as well as the creation of Organizational Units and Users. NOTE: This is a continuation of [Preparing-AD-Infrastructure-in-Azure](https://github.com/bigbearbunkie/Preparing-AD-Infrastructure-in-Azure)

<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2> Installation and Deployment Steps</h2>

<h3> Step 1: Installing Active Directory</h3>

<p> - First, we need to log into the Domain Controller (DC-1). Once the VM loads, launch Server Manager if it hasn't already done so, and then click "Add Roles and Features". Skip to the "Server Roles" tab and select the box that says "Active Directory Domain Services". Click "Add Features". Skip to the "Confirmation" tab, check the "restart if required" box, and click "Install" and wait for it to finish. Now we need to promote it as a Domain Controller and create a new forest. So go back to Server Manager and look for a notification with a caution sign. Click it and then click "Promote this server to a Domain Controller". In the new window, select "add a new forest" and enter "mydomain.com" as the Root domain name. Click Next. Now you need to create a password. It can be anything, just make sure you remember it in case you need to use it later. Click Next. Deselect the box that says "Create DNS delegation" and click Next. Skip to the "Prerequisites Check" tab, wait for it to finish reviewing, and after it passes the prerequisites check, click Install and wait for it to finish. If it doesn't auto-restart, do it yourself and then log back in as user: mydomain.com\labuser.</p>

<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%201.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%201b.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%201c.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%201d.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%201e.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%201f.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%201g.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%201h.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%201i.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3>Step 2: Create a Domain Admin user within the domain</h3>


- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

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
