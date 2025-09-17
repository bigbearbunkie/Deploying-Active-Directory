<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>

This tutorial outlines the installation and deployment of on-premises Active Directory within Azure Virtual Machines, as well as the creation of Organizational Units and Users. Be sure to write down any login information created. NOTE: This is a continuation of [Preparing-AD-Infrastructure-in-Azure](https://github.com/bigbearbunkie/Preparing-AD-Infrastructure-in-Azure)

<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services

<h2>Operating Systems Used </h2>

- Windows Server 2022 (DC-1)
- Windows 10 Pro (Client-1)

<h2> Installation and Deployment Steps</h2>

<h3> Step 1: Installing Active Directory</h3>

<p> - First, we need to log into the Domain Controller (DC-1). Once the VM loads, launch Server Manager if it hasn't already done so, and then click "Add Roles and Features". Skip to the "Server Roles" tab and select the box that says "Active Directory Domain Services". Click "Add Features". Skip to the "Confirmation" tab, check the "restart if required" box, and click "Install" and wait for it to finish. Now we need to promote it as a Domain Controller and create a new forest. So go back to Server Manager and look for a notification with a caution sign. Click it and then click "Promote this server to a Domain Controller". In the new window, select "add a new forest" and enter "mydomain.com" as the Root domain name. Click Next. Now you need to create a password. It can be anything, just make sure you remember it in case you need to use it later. Click Next. Deselect the box that says "Create DNS delegation" and click Next. Skip to the "Prerequisites Check" tab, wait for it to complete the review, and then, after it passes the prerequisites check, click "Install" and wait for the process to finish. If it doesn't auto-restart, do it yourself and then log back in as user: mydomain.com\labuser.</p>

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

<h3>Step 2: Create a Domain Admin User within the Domain</h3>

<p> - Now we need to create a user that can log into Client-1 to manage the domain. First, open the Start menu and 
then run Active Directory Users and Computers. Before we create a new User, let's make a couple of Organizational
Units. Right-click the tab that says "mydomain.com" -> New -> Organizational Unit. Name it "_EMPLOYEES" and click 
"Ok". Now, create another Organizational Unit called "_ADMINS" the same way. When we create a user, we can place them in one or both of these Units. So now we will create an Admin User in the "_ADMINS" unit. Right-click "_ADMINS" -> New -> User. Name them "Jane Doe" and for the user logon name: "jane_admin". Click Next. Create a password for the user and select your settings. For this lab, I recommend deselecting "User must change password at next login" and selecting "Password never expires" just for the sake of simplicity. Click Next and Finish. When you open the "_ADMINS" folder, Jane Doe will be there. Now we need to add Jane Doe to the "Domain Admins" Security Group. In "_ADMINS", right-click Jane Doe -> Properties. Go to the "Member of" tab and click "Add...". Enter "domain admins", click "Check Names", and click OK. On the next page, click "Apply", then OK. Now we will log out and close the connection to DC-1 and log back in as the admin account "mydomain.com\jane_admin". We will log in to DC-1 as this user from hereout.  </p>

<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%202.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%202b.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%202c.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%202d.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%202e.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%202f.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%202g.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%202h.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<h3> Step 3: Join Client-1 to Your Domain (mydomain.com) </h3>

<p> - Login to Client-1 as the original local admin (labuser). Go to your system settings, scroll down, and find "Rename this PC (Advanced)". Click "Change...". Then, in the new window, select "Domain" and enter "mydomain.com". Click OK. You will be prompted to enter the login information for "mydomain.com\jane_admin" because that is the account with permission to make this change. Enter the username and password and click OK. Then restart the machine if it doesn't restart on its own to make the changes. Next, we need to log back into DC-1 to confirm that Client-1 has been added. So once it loads, open Active Directory Users and Computers. Under "mydomain.com", open the "Computers" file, and you should see "Client-1" listed. The last thing we need to do is create one more Organizational Group called "_Clients" and add "Client-1" to it. So once again: right-click "mydomain.com" -> New -> Organizational Unit. Name it "_CLIENTS". Now under "Computers", drag Client-1 over to the "_CLIENTS" folder and it will be added. </p>

<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%203.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%203b.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%203c.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%203d.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%203e.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<img src="https://github.com/bigbearbunkie/Deploying-Active-Directory/blob/main/Deploy%20AD%20Step%203f.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />




<br />
