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

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/ca4f91b4-7276-4bf7-b343-2c01cd7839f4)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/c54fb0e8-8d35-4ccb-bb8f-25e729b6f80e)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/96905cf0-0a63-46d9-bf5f-46f166275cc1)

  ![image](https://github.com/DevinWilliamsIT/configure-ad/assets/155914712/0bd80de4-1721-45d7-b41a-202c806a910d)




  

  

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
