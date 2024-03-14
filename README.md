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
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/dc4f6b36-daad-41af-9ace-f8d2a0aac857" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Download Windows 10 and Windows Server 2019 ISO files:  <br/>
<br/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/a508ea67-a9e3-4459-9acb-4bea1a48dc23" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/0d3e233e-628b-46b2-b164-e2632337ca04" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/4f565cf5-d6dd-4344-9712-10b77343b7e2" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/56593ba5-947f-4b19-b35c-a04559dd320b" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Create a virtual machine for Domain Controller and host active directory. Call it DC(Domain Controller) for simplicity.: <br/>
Version: Select "Other Windows(64-bit). Adjust Ram & CPU count according to your PC specifications. <br/>
<br/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/0c1f0da2-a4ce-4a2a-ad97-2fb4e8303251" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/dc002ccc-f9c8-485e-b17b-8d4acb87d291" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/6a44740e-a08f-4b7a-a081-91fb2d5b74e5" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Equip virtual machine with two network adapters.  <br/>
Two Nics(Network interface controller). One dedicated for internet(Adapter 1 NAT)  <br/>
2nd dedicated for internal VMware network(Adapter 2 Internal network):  <br/>
<br/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/128b1831-037a-49b2-be7a-3e0455098031" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/6882c4b4-4e7a-4eb2-8d8e-2e77428594a5" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
Install Windows Server 2019 on Domain Controller:  <br/>
<br/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/cf805d7a-e873-4092-bbac-0972538c6c79" height="70%" width="70%" alt="Disk Sanitization Steps"/>  <br/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/b145b964-d379-4d58-bfcb-d289acedaf70" height="70%" width="70%" alt="Disk Sanitization Steps"/>  <br/>
<br/>
Select "Windows Server 2019 Standard Evaluation (Desktop Experience) followed by Custom: Install Windows only(advanced):  <br/>
<br/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/3621043a-ad47-4cff-bea5-90cc40f17675" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/6084e94e-d820-4a32-8b1b-8be26862303c" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/53531a1a-c1ea-435f-b213-f5c40ab01011" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />
<br />
Create default password of "Password1" We will use this as universal password for lab purposes:  <br/>
<br/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/e0ec2508-fdb8-4258-8eb8-91162ef271b6" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />
<br/>
To login, click input > Keyboard > Insert Ctrl+Alt+Del followed by password we created earlier. <br/>
<br/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/d45bf49a-448a-46bc-b445-7834ef39c992" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />
<br/>
Insert Guest Additions CD image to reduce lag in VM. Double click the inserted image and run "VBoxWindowsadditions.amd64". Follow instructions on screen and click on reboot later. After Shutdown VM <br/>
<br/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/0447ed81-5ecd-4803-ba5d-46f206f459fa" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/5ccef606-ca3c-4b2e-a4d6-ea70edb1cb8d" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/a2016360-0da2-4e8d-905b-6d5d0f7b189f" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />
<br/>
Assign IP Addresses:  <br/>

Assign and label the correct network adapter
Start by selecting the Ethernet connection that is connected to the internet. View status of each adapter by right-clicking on it. Rename the one with "IPv4 Address: 10.0.2.15"(Which is the one connected to internet) to Internet and the other "unrecognized" one to X_INTERNAL_X. The unrecognized adapter is due to DHCP server not being able to find IP Address, so internal VM one was provided.

<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/287e628a-30be-4b97-8ce0-b0278d54c65e" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/36f5c523-4e00-4ce2-960c-e13a5c43782c" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/728a5958-139b-4f3f-af33-c22bc3b19161" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/0587e85b-7c39-4dc8-8ce7-32654c9c9477" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/b1b831df-6aad-4b23-8e96-97701c5a4f6b7" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/e1b50881-f2bb-4647-bb07-8f607c330f1e" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/366e7d30-1a33-4505-a9e5-50abb60e69b8" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />

In internal adapter options, right-click and select properties, double click Internet Protocol Version 4(TCP/IPv4). Change option to "Use the following IP address:" and enter the IP address: 172.16.0.1 and subnet mask as 255.255.255.0
For DNS, Once AD is installed, it automatically installs DNS. So we can enter the same IP Address above 172.16.0.1(Server will use itself as DNS server)

<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/91e873c9-df9b-4037-b649-5edf64cf9e95" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />

Name server, establish Active Directory, specify domain name:  <br/>
<br/>
Select "Add roles and features"<br/>
<br/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/e54f1bb5-00da-4059-bb28-7a879b86fdb9" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />
<br/>
Select Next until you reach image below. Select "Active Directory Domain Services". Click add features and next until install.<br/>
<br/>
<img src="https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/9bfb5c6f-b603-40ec-9157-104b225074d7" height="70%" width="70%" alt="Disk Sanitization Steps"/> <br />







Configure NAT and Routing for internet access:  <br/>

Set up DHCP to assign IP addresses to Windows 10 machine:  <br/>

Run PowerShell script to create 1,000 users in Active Directory:  <br/>

Create another virtual machine, install Windows 10, connect to private network:  <br/>


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
