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
      <li>Restart and then log back into DC-1 as user: mydomain.com\labuser</li>
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
