<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)


<h2>Deployment and Configuration Steps</h2>

<p>
<img width="1680" alt="Screenshot 2025-01-28 at 8 09 10 PM" src="https://github.com/user-attachments/assets/7e01345c-8573-45a5-86e8-603c111a87c4" />
</p>
<p>
  Install Active Directory
install Active Directory Domain Services on Domain Controller and create a new forest(can be anything, just remember what it is), then log back in: Ex. mydomain.com\labuser
</p>
<br />

<p>
<img width="1680" alt="Screenshot 2025-01-29 at 4 26 08 AM" src="https://github.com/user-attachments/assets/d9bd9e29-c952-45a4-9857-d966c95d139b" />
</p>
<p>
In Active Directory Users and Computers (ADUC), create a couple of Organizational Units (OU's) called _EMPLOYEES, _ADMINS, and _CLIENTS
</p>
<br />

<p>
<img width="1680" alt="Screenshot 2025-01-29 at 4 13 44 AM" src="https://github.com/user-attachments/assets/9b02064b-a166-458b-a21b-29f0e7acf254" />
</p>
<p>
  Create a Domain Admin user within the domain
Create a new employee and add them to the “Domain Admins” Security Group
</p>
<br />

<p>
<img width="1680" alt="Screenshot 2025-01-29 at 4 16 21 AM" src="https://github.com/user-attachments/assets/6b6aebc1-c5d2-4e07-9d37-038fabd840b0" />
</p>
<p>
  Join Client-1 to your domain
Login to Client-1 as the original local admin and join it to the domain, log back into the Domain Controller & drag Client-1 into the "_CLIENTS" section in ADUC
</p>
<br />

<p>
<img width="1680" alt="Screenshot 2025-01-29 at 4 17 37 AM" src="https://github.com/user-attachments/assets/850e0267-d339-4c81-a067-402d1a9c9edf" />
</p>
<p>
  Setup Remote Desktop for non-administrative users on Client-1
Log into Client-1 as employee admin
Open system properties
Click “Remote Desktop”
Allow “domain users” access to remote desktop
  You can now log into Client-1 as a normal, non-administrative user now
</p>
<br />
