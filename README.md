<h1>Active Directory Home Lab</h1>

<h2>Description</h2>
In this Lab, we are going to walk through how to create an active directory home lab environment using Oracle Virtual Box. Configuring and running this lab will help develop our understanding of how active directory and windows networking works.
<br />

<h2>Lab Overview</h2>

1. <b>Download and install Oracle Virtual Box</b> 
2. <b>Download Windows 10 and Windows Server 2019 ISO files</b>
3. <b>Create a virtual machine for Domain Controller and host active directory</b>
4. <b>Equip virtual machine with two network adapters</b>
5. <b>Install Windows Server 2019 on Domain Controller, assign IP addresses</b>
6. <b>Name server, establish Active Directory, specify domain name</b>
7. <b>Configure NAT and Routing for internet access</b>
8. <b>Set up DHCP to assign IP addresses to Windows 10 machine</b>
9. <b>Run PowerShell script to create 1,000 users in Active Directory</b>
10. <b>Create another virtual machine, install Windows 10, connect to private network</b>


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle Virtual Box</b>
- <b>Windows Server 19 ISO</b>
- <b>Windows 10 ISO</b>
- <b>Server Manager</b>
- <b>Active Directory Users and Computers</b>
- <b>CMD</b>

<h2>Environments Used </h2>

- <b>Windows 10</b>
- <b>Windows Server 2019</b>


<h2>Program walk-through:</h2>













Download and install Oracle Virtual Box: <br/>
<br/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/dc4f6b36-daad-41af-9ace-f8d2a0aac857" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Download Windows 10 and Windows Server 2019 ISO files:  <br/>
<br/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/a508ea67-a9e3-4459-9acb-4bea1a48dc23" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/0d3e233e-628b-46b2-b164-e2632337ca04" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/4f565cf5-d6dd-4344-9712-10b77343b7e2" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/56593ba5-947f-4b19-b35c-a04559dd320b" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Create a virtual machine for Domain Controller and host active directory. Call it DC(Domain Controller) for simplicity.: <br/>
Version: Select "Other Windows(64-bit). Adjust Ram & CPU count according to your PC specifications. <br/>
<br/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/0c1f0da2-a4ce-4a2a-ad97-2fb4e8303251" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/dc002ccc-f9c8-485e-b17b-8d4acb87d291" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/6a44740e-a08f-4b7a-a081-91fb2d5b74e5" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Equip virtual machine with two network adapters.  <br/>
Two Nics(Network interface controller). One dedicated for internet(Adapter 1 NAT)  <br/>
2nd dedicated for internal VMware network(Adapter 2 Internal network.:  <br/>
<br/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/128b1831-037a-49b2-be7a-3e0455098031" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/6882c4b4-4e7a-4eb2-8d8e-2e77428594a5" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Install Windows Server 2019 on Domain Controller, assign IP addresses:  <br/>
<br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Name server, establish Active Directory, specify domain name:  <br/>
<br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Configure NAT and Routing for internet access:  <br/>
<br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
Set up DHCP to assign IP addresses to Windows 10 machine:  <br/>
<br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
Run PowerShell script to create 1,000 users in Active Directory:  <br/>
<br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
Create another virtual machine, install Windows 10, connect to private network:  <br/>
<br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
