# configure-ad

<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1:Install Active Directory: Set up Active Directory Domain Services on DC-1 and promote it to a Domain Controller with a custom domain name.
- Step 2:Create Admin Account: Create Organizational Units (OUs) for employees and admins, then set up and assign a domain admin account.
- Step 3:Join Client to Domain: Configure DNS settings for the client machine, restart, and join it to the domain, then verify in Active Directory.
- Step 4:Enable Remote Desktop: Set up Remote Desktop on the client machine to allow domain users to log in.
- Step 5:Create User Accounts: Use PowerShell to create multiple user accounts, organize them in AD, and test by logging into the client machine

<h2>Deployment and Configuration Steps</h2>

<p>
<img width="764" alt="Screenshot 2025-01-03 at 12 26 27 PM" src="https://github.com/user-attachments/assets/2210206b-9dd1-48e8-a345-93cf9f957051" />

</p>
<p>
Set up Active Directory by installing AD DS on the primary server and promote it to a Domain Controller with a custom domain name. After completing the setup, organize the directory by creating Organizational Units (OUs) for employees and admins and set up a domain admin account for management tasks. Next, join the client machine to the domain by configuring its DNS, restarting it, and verifying its presence in the directory. Move the client to a designated OU for client devices to maintain an organized structure.
</p>
<br />

<p>
<img width="423" alt="Screenshot 2025-01-05 at 10 27 33 AM" src="https://github.com/user-attachments/assets/d963e426-ae74-4175-9f35-2e1a61105f27" />

</p>
<p>
Configure Remote Desktop on the client machine to allow domain users to connect. Adjust the settings as the domain admin, ensuring standard users can log in remotely. Then, use PowerShell on the Domain Controller to create multiple user accounts in bulk and organize them into the appropriate OU. Test the setup by logging into the client machine with one of the new accounts to confirm functionality. This demonstrates the process of configuring remote access and managing users in a domain environment.
</p>
<br />
<img width="493" alt="Screenshot 2025-01-05 at 11 06 20 AM" src="https://github.com/user-attachments/assets/7bd34e30-4c86-40bc-a9de-6ee5f30c7a1e" />

<p>

</p>
<p>
This process involves managing account lockouts, enabling and disabling accounts, and reviewing logs. Select a previously created user account, and attempt to login with an incorrect password mulitple times which triggers a lockout based on the configured Group Policy threshold. Once the account is locked, unlock the account in Active Directory, the password is reset, and a successful login is performed. Next disable the account, and an attempt to login demonstrates the expected error message. Finally, the account is re-enabled, access is restored, and the logs on both the Domain Controller and the client machine are reviewed to confirm the recorded events.
</p>
<br />
