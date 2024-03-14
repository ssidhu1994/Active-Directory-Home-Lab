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



Download Windows 10 and Windows Server 2019 ISO files:  <br/>

![Screenshot 2024-03-13 212327](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/d9e2235f-b49f-4299-87ea-c8dd00a11636)

![Screenshot 2024-03-13 213228](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/727d2347-4018-4420-8d87-33d0b111d283)

![Screenshot 2024-03-13 213246](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/086feaf0-3b4b-4220-a6b7-d24a8be2fafc)

![Screenshot 2024-03-13 213257](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/2d7cdbd2-5c53-4208-8e63-080326530be5)






Create a virtual machine for Domain Controller and host active directory. Call it DC(Domain Controller) for simplicity.: <br/>
Version: Select "Other Windows(64-bit). Adjust Ram & CPU count according to your PC specifications. <br/>

Equip virtual machine with two network adapters.  <br/>
Two Nics(Network interface controller). One dedicated for internet(Adapter 1 NAT)  <br/>
2nd dedicated for internal VMware network(Adapter 2 Internal network):  <br/>

Install Windows Server 2019 on Domain Controller:  <br/>

Select "Windows Server 2019 Standard Evaluation (Desktop Experience) followed by Custom: Install Windows only(advanced):  <br/>

Create default password of "Password1" We will use this as universal password for lab purposes:  <br/>

To login, click input > Keyboard > Insert Ctrl+Alt+Del followed by password we created earlier. <br/>
<
Insert Guest Additions CD image to reduce lag in VM. Double click the inserted image and run "VBoxWindowsadditions.amd64". Follow instructions on screen and click on reboot later. After Shutdown VM <br/>

Assign IP Addresses:  <br/>

Assign and label the correct network adapter
Start by selecting the Ethernet connection that is connected to the internet. View status of each adapter by right-clicking on it. Rename the one with "IPv4 Address: 10.0.2.15"(Which is the one connected to internet) to Internet and the other "unrecognized" one to X_INTERNAL_X. The unrecognized adapter is due to DHCP server not being able to find IP Address, so internal VM one was provided.



In internal adapter options, right-click and select properties, double click Internet Protocol Version 4(TCP/IPv4). Change option to "Use the following IP address:" and enter the IP address: 172.16.0.1 and subnet mask as 255.255.255.0
For DNS, Once AD is installed, it automatically installs DNS. So we can enter the same IP Address above 172.16.0.1(Server will use itself as DNS server)



Name server, establish Active Directory, specify domain name:  <br/>






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
