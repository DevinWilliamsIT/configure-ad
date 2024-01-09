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
1. Firstly, we are going to setup our resources in Azure (portal.azure.com).
  <ul>
    <li>Create the Resource Group and Domain Controller VM (Windows Server 2022) named “DC-1” with at least 2 vcpu's</l>
    <li>Set Domain Controller’s (DC-1) NIC Private IP address to be static</li>
    <li>Create the Client VM (Windows 10) named “Client-1”. Use the same Resource Group and Vnet that was created in Step 1.</li>
    <li>Ensure that both VMs are in the same Vnet</li>
  </ul>

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/ef7247d8-be10-4db3-ba7e-4db7cc43fdef)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/c54fb0e8-8d35-4ccb-bb8f-25e729b6f80e)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/131644f2-2c07-4ee3-acfb-129876d6e676)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/0bd80de4-1721-45d7-b41a-202c806a910d)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/cbaba373-cae6-42ef-8708-ae1bc00188a7)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/704cbd66-0cb7-4b9d-a6fb-2dafa36acb74)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/06cd38d5-1077-4031-9298-39cc6de2c059)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/e3a7ef81-3c80-447c-b1e5-51ac339ad3bb)

  <br />

  <p>
    2. Next we are going to ensure connectivity between the client and Domain Controller
    <ul>
      <li>Login to Client-1 with Remote Desktop and ping DC-1’s private IP address with ping -t</li>
      <li>Login to the Domain Controller (DC-1) and enable ICMPv4 in on the local windows Firewall</li>
      <li>Check back at Client-1 to see the ping succeed</li>
    </ul>
  </p>

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/cd6cbaa4-f5c2-48f0-92a0-0d766a3ed951)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/b8c0f530-61fa-4359-8a3d-32d9522e885a)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/f89ad7e7-82af-4b00-8b63-3fcc1bb02d37)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/95c0157a-c061-49b6-aa11-57ded2bfceec)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/6e3bc1f1-4922-46a8-bc47-08bcd1e1aed3)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/4f4edb73-7f57-45fb-b80d-dfd364a6ec6f)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/ae43b487-7b18-4c21-9f52-33d48649810f)

  <br />

  <p>
  3. Next we are going to install Active Directory.
    <ul>
      <li>Login to DC-1 and install Active Directory Domain Services</li>
      <li>Promote as a DC: Setup a new forest as mydomain.com</li>
      <li>Restart and then log back into DC-1 as user: mydomain.com\devuser</li>
    </ul>
  </p>

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/7c87f5ca-6b7a-4b08-bd53-12120de3e9d5)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/79980bfb-1d6f-4a04-a9a2-332c7491c23b)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/2d90652a-bd9c-4cfe-a2c3-083d1464bc94)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/b19add13-6d5b-4337-af98-3d6803cdb53f)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/626cfb4e-35ce-42e1-ab6a-cb676e7e567a)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/2efff94b-4dfe-4898-8a5c-80c7f3499b81)

  <br />

  <p>
    4. Now we are going to Create an Admin and Normal User Account in Active Directory
    <ul>
    <li>In Active Directory Users and Computers (ADUC), create an Organizational Unit (OU) called “_EMPLOYEES”</li>
    <li>Create a new OU named “_ADMINS”</li>
    <li>Create a new employee named “Steph Curry” (same password) with the username of “steph_admin”</li>
    <li>Add steph_admin to the “Domain Admins” Security Group</li>
    <li>Log out/close the Remote Desktop connection to DC-1 and log back in as “mydomain.com\steph_admin”</li>
    <li>User steph_admin as your admin account from now on</li>
    </ul>
  </p>

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/bf9c6d30-1623-4ad3-a1ad-2aa6aab3aee3)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/d076bd04-e374-4aa2-83a9-ae8dbc228cac)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/6c5888e0-d27f-44c4-9e2c-507858516d2b)
  
  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/4b938943-05f0-4273-b8b6-60362eba08a6)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/c96a2a84-c58a-425d-b297-005d28af5ab8)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/4a122979-207c-439a-94a9-dcc8f3c27082)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/41cd74d6-b226-4f3c-a53e-7dfa7b59e1a0)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/2037a21d-e54f-4edf-9ac8-cd6eec5b8d30)

  <br />

  <p>
    5. Next we are going to join Client-1 to your domain (mydomain.com)
    <ul>
      <li>From the Azure Portal, set Client-1’s DNS settings to the DC’s Private IP address</li>
      <li>From the Azure Portal, restart Client-1</li>
      <li>Login to Client-1 (Remote Desktop) as the original local admin (devuser) and join it to the domain (computer will restart)</li>
      <li>Login to the Domain Controller (Remote Desktop) and verify Client-1 shows up in Active Directory Users and Computers (ADUC) inside the “Computers” container on the root of the domain</li>
      <li>Create a new OU named “_CLIENTS” and drag Client-1 into there</li>
    </ul>
  </p>

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/b09febe6-e65f-4c7f-a5d6-cdc4c73d2009)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/45cc5410-2eef-472b-81ed-ec8a94e9ca59)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/a9de97cf-bb62-40c3-b486-4feffa5e6848)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/1cab5d4e-e6b7-4d39-bcff-5ca6958c18fe)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/a79787bf-8476-42c8-9eff-806b67c46fdb)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/045f2892-2143-4ba6-a861-24be3dac5cc9)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/2abee2d9-5b9e-47fe-912e-b8fe5038d42a)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/04301b63-a64b-4072-be02-d73889b3f534)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/abd3b5ec-e897-4b6b-876a-661c60689703)

  <br />

  <p>
    6. Next we are going to setup Remote Desktop for non-administrative users on Client-1
    <ul>
    <li>Log into Client-1 as mydomain.com\steph_admin and open system properties</li>
    <li>Click “Remote Desktop”</li>
    <li>Allow “domain users” access to remote desktop</li>
    <li>You can now log into Client-1 as a normal, non-administrative user now</li>
    </ul>
  </p>

  


  

  
  
  

  















  

























  

  

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
