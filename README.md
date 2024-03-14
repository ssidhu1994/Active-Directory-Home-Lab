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

1.Download and install Oracle Virtual Box: <br/>
![Screenshot 2024-03-13 212327](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/d9e2235f-b49f-4299-87ea-c8dd00a11636)

2.Download Windows 10 and Windows Server 2019 ISO files(Recommend to save on desktop or easy to access folder):  <br/>

![Screenshot 2024-03-13 213228](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/727d2347-4018-4420-8d87-33d0b111d283)

![Screenshot 2024-03-13 213246](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/086feaf0-3b4b-4220-a6b7-d24a8be2fafc)

![Screenshot 2024-03-13 213257](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/2d7cdbd2-5c53-4208-8e63-080326530be5)

3. Create a virtual machine for Domain Controller and host active directory:  <br/>
Call it DC(Domain Controller) for simplicity. <br/>
Version: Select "Other Windows(64-bit). Adjust Ram & CPU count according to your PC specifications. <br/>

![Screenshot 2024-03-13 224057](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/9b29c5a9-86cf-499e-be0c-4850b8f87028)
![Screenshot 2024-03-13 223504](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/cf2ff8f0-f0c3-4b1c-949b-b48c61acd4ee)
![Screenshot 2024-03-13 223910](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/bb8e3733-cbc7-47f9-9e73-52f92d7ba1b3)

4.Equip virtual machine with two network adapters:  <br/>
Two Nics(Network interface controller). One dedicated for internet(Adapter 1 NAT)  <br/>
2nd dedicated for internal VMware network(Adapter 2 Internal network)  <br/>

![Screenshot 2024-03-13 224329](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/5573e8e1-a127-48b9-81d7-03a515f60fb0)
![Screenshot 2024-03-13 224346](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/0307c855-8429-4cad-bc8b-018df1004909)


5.Install Windows Server 2019 on Domain Controller:  <br/>

![Screenshot 2024-03-13 225535](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/e2f21109-2bb1-4b18-a7e0-32a751ec3eab)

![Screenshot 2024-03-13 225558](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/09a79031-e782-4f81-9b13-c0c490e5ccde)

Select "Windows Server 2019 Standard Evaluation (Desktop Experience) followed by Custom: Install Windows only(advanced):  <br/>
Create default password of "Password1" We will use this as universal password for lab purposes:  <br/>

![Screenshot 2024-03-13 230839](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/268fa95f-d3f0-4dc9-b437-de2d412defc1)

![Screenshot 2024-03-13 231821](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/b2334fc3-849d-41af-9e32-c854f64682fb)

![Screenshot 2024-03-13 231839](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/947e9f93-2a8d-4587-b9b7-3a3a73e82f9c)

![Screenshot 2024-03-13 232623](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/71706429-add3-4625-bf4d-dd28f258ffd3)

To login, click input > Keyboard > Insert Ctrl+Alt+Del followed by password we created earlier. <br/>

![Screenshot 2024-03-13 232924](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/88f2c338-2cae-485c-a4d2-7185ad7f5aec)

Insert Guest Additions CD image to reduce lag in VM. Double click the inserted image and run "VBoxWindowsadditions.amd64". Follow instructions on screen and click on reboot later. After Shutdown VM <br/>

![Screenshot 2024-03-13 233639](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/dcaac46f-8f34-482a-876e-af696a00aa1c)

![Screenshot 2024-03-13 234138](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/89519995-a8bd-4e9a-bc80-3f0757f9eaa5)

Assign IP Addresses:  <br/>
Select the computer icon from bottom right icon tray, click unidentified network > Change adapter options.

![Screenshot 2024-03-13 235307](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/ddb12733-b5a2-4044-ab9f-5ca187632923)

![Screenshot 2024-03-13 235318](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/9a2864b2-0104-474b-876c-957821346b76)

Here we see our two nics(Network interface controller) from earlier. Assign and label the correct network adapter
Start by selecting the Ethernet connection that is connected to the internet. View status of each adapter by right-click > Status > Details. Rename the one with "IPv4 Address: 10.0.2.15"(Which is the one connected to internet) to "Internet" and the other "unrecognized" one to X_INTERNAL_X. The unrecognized adapter is due to DHCP server not being able to find IP Address, so internal VM one was provided.

![Screenshot 2024-03-13 235333](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/c382f8c6-4186-4ba7-a24e-1bf4231a7f98)

![Screenshot 2024-03-13 235402](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/c252391f-7856-44e4-a1da-664ed056e9a5)

![Screenshot 2024-03-14 001737](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/1cfbc947-0990-404f-8cd4-a92b172d0af4)

![Screenshot 2024-03-14 002118](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/06a2daa1-9286-4223-a28d-ea49f3328f44)

In X_INTERNAL_X adapter options, right-click and select properties, double click Internet Protocol Version 4(TCP/IPv4). Change option to "Use the following IP address:" and enter the IP address: 172.16.0.1 and subnet mask as 255.255.255.0
For DNS, Once AD is installed, it automatically installs DNS. So we can enter the same IP Address above 172.16.0.1(Server will use itself as DNS server)

![Screenshot 2024-03-14 144551](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/e677ad2f-cbb2-4946-9575-c57785134355)



























5.Name server, establish Active Directory, specify domain name:  <br/>






7.Configure NAT and Routing for internet access:  <br/>

8.Set up DHCP to assign IP addresses to Windows 10 machine:  <br/>

9.Run PowerShell script to create 1,000 users in Active Directory:  <br/>

10.Create another virtual machine, install Windows 10, connect to private network:  <br/>


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
