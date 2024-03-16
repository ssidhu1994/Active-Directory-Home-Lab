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
6. <b>Name server, establish Active Directory, and create dedicated domain admin account</b>
7. <b>Configure NAT and Routing for internet access</b>
8. <b>Set up DHCP to assign IP addresses to Windows 10 machine</b>
9. <b>Create new client user. Create another virtual machine, install Windows 10, connect to private network</b>
10. <b>Bonus: Run PowerShell script to create 1,000 users in Active Directory</b>


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

5.Name server, establish Active Directory, and create dedicated domain admin account:  <br/>

From server manager, select "Add roles and features". Select next x2 and until you see "Select server role". Select "Active Directory Domain Services". Click add features and continue with installation. 
Select yellow flag from upper right corner and click "Promote this server to a domain controller". Select Add a new forest and call it mydomain.com(Keep it simple for lab). 
For password we will use the same "Password1" and disable "Create DNS delegation". Click next until installtion is complete, after which the VM will restart.

![Screenshot 2024-03-14 145847](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/9aac421c-8190-4687-bfc7-fa3a8771d0bd)

![Screenshot 2024-03-14 150213](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/e2eaa17c-cbba-4283-964a-4a684927a9c2)

![Screenshot 2024-03-14 151211](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/d4b1b08d-cdb6-4174-a274-134d49cd93a4)

![Screenshot 2024-03-14 160606](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/5e20c6a9-2cbe-467a-bfbf-35992166371d)

![Screenshot 2024-03-14 160657](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/3b3cb124-67b8-4d09-b5e3-f8ab4e019153)

![Screenshot 2024-03-14 160746](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/20528794-e2d5-4db0-ad52-c94ae14cc7f3)

![Screenshot 2024-03-14 160855](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/c29cbf89-716e-467e-8e47-f5357c172c94)

To create dedicated admin account, bottom left click start > Windows Administrative Tools > Active Directory Users and Computers.
Under forest our newly created domain, right click > New > Organizational units(Fancy way of saying folder) and name it _ADMINS.
Once we created _ADMINS, right-click again > New > user. Create the user you would like. For User logon name, industry standard is a- first letter of firstname followed by lastname.
For password use same "Password1" and check "Password never expires" for lab purpose. You should now see the new user, but it's not a admin yet.
Next right-click new user > Properties > Member Of tab > Add > in "Enter the object names to select, type "domain admins" and click check name followed by ok. Click apply and ok to finalize.

![Screenshot 2024-03-14 162337](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/37694986-7444-4352-ba5d-203128d0456d)

![Screenshot 2024-03-14 162434](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/def8e095-e88b-46a2-abcc-04ac4723061b)

![Screenshot 2024-03-14 162519](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/edc7e25d-9529-4b6b-b00e-3ab2d29915ab)

![Screenshot 2024-03-14 162655](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/3d1884dc-60f7-4a2d-b49e-8d26e7e11fc6)

![Screenshot 2024-03-14 162725](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/818dd73b-82d3-46a7-9224-19f6e34113b5)

![Screenshot 2024-03-14 162807](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/3502e52b-d91a-40e0-8dd6-79d1f003bc2e)

![Screenshot 2024-03-14 164028](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/bf7e36ee-cd4a-45a0-ad13-8fff1905c78f)

![Screenshot 2024-03-14 164046](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/2b3c32c2-9cf2-4c3b-8c38-acd0fee2d9b2)

![Screenshot 2024-03-14 164054](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/b6541bcf-c897-4e49-9221-22461b808f1d)

![Screenshot 2024-03-14 164118](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/06df0cb6-3bf1-4d02-aa0b-3e3489ceb6bb)

![Screenshot 2024-03-14 164130](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/ac1478af-378c-4ec7-a130-1d6f9cddb68b)

To use our newly created admin account logout of account from start menu, but this time select "Other user". 
Enter the logon username and password and you should be able to login using the new admin account

![Screenshot 2024-03-14 165549](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/c19ed6e8-e12a-4f89-a77e-c39ba18a88ee)

![Screenshot 2024-03-14 165608](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/7ee49b94-54ae-49b1-b3a7-b68fd01aa786)

![Screenshot 2024-03-14 165626](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/98c0c392-d498-4519-88c2-0376ad6bbf5a)

7.Configure NAT and Routing for internet access:  <br/>

Start by clicking "Add roles and features" > Next x3 > check box "Remote Access". Select Routing(It will automatically select first option) > Add features > Install.
Click tools from upper right corner > Routing and Remote Access > right-click server name > Configure and Enable Routing and Remote Access.
Select Network address translation (NAT) > select the IPv4 address which we named earlier to INTERNET. Server should have a upwards green arrow and connected to internet

![Screenshot 2024-03-14 170057](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/fdb96cbb-7866-472d-82aa-56af9b639e17)

![Screenshot 2024-03-14 170126](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/d6261656-0a4c-494d-ad20-caeda64c3be7)

![Screenshot 2024-03-14 170205](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/34b39cd4-61e5-4a1a-abc5-1b20343fef3b)

![Screenshot 2024-03-14 170218](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/05c3165f-be51-4db1-835f-a0643ad5dcf8)

![Screenshot 2024-03-14 171623](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/a518f0b8-9b90-4bff-ad17-f416d4965049)

![Screenshot 2024-03-14 171048](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/68bb0776-1021-48f8-bde8-775b9db11599)

![Screenshot 2024-03-14 171124](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/6234c76e-c4ea-43cc-8992-162bccde71dd)

![Screenshot 2024-03-14 171232](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/6aa37b17-77c2-4860-9516-2a0e36fd7d0d)

![Screenshot 2024-03-14 172422](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/74f55e12-acce-4ebb-8a7a-c41526a11e08)

8.Set up DHCP to assign IP addresses to Windows 10 machine:  <br/>

The purpose of setting up DHCP server is to allow windows 10 clients to get an IP address to access the internet.
Start by going to add roles and features > Next x3 > check box "DHCP Server", add feature and next until install.
Next Click Tools > DHCP. You will notice the red down arrow indicating the server is down. Right click IPv4 and click "New Scope".
We will name the scope after the IP range, 172.16.0.100-200. Next we enter the start address(172.16.0.100) & end address(172.16.0.200).
Length we will change to 24 so we have Subnet mask of 255.255.255.0. Skip adding any exclusions. The lease duration is how long a client can use the IP address from the server before it needs to be refreshed.
CLick "Yes, I want to configure these options now". We want to enable this because we want to configure which server to use for DNS & default gateway so the clients can access the internet. 
For Router, we will add 172.16.0.1. This is because we configured NAT on the domain controller and the domain controller has routing configured. After click add followed by next until finish.
Onces finished, right-click the DHCP server and Authorize. Right-click once more and click refresh. You should now see the IPv4 & IPv6 turn green with upwards arrow.

![Screenshot 2024-03-16 154528](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/7ebba184-7aa6-482e-893a-2a5c6385d0bc)

![Screenshot 2024-03-16 154616](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/85a3df28-99f2-4360-9ead-bd2517018014)

![Screenshot 2024-03-16 155317](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/d33e8aac-1b90-4ce4-a677-fdccfba2f2f1)

![Screenshot 2024-03-16 155436](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/31206fd4-66f0-40ee-b30a-2c31dcc62937)

![Screenshot 2024-03-16 160238](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/8401ce66-f84f-49ad-b732-13f37b3841e0)

![Screenshot 2024-03-16 160328](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/a4cdf9e9-604f-44c8-a6b4-237cc7063559)

![Screenshot 2024-03-16 160356](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/3e0427f0-d795-491c-85f8-accb8d2ce80a)

![Screenshot 2024-03-16 160405](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/e45adfb5-1832-4970-8b68-c9dff5478405)

![Screenshot 2024-03-16 160413](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/7ed8952a-7cb7-4ddc-b8e3-679b0b21a618)

![Screenshot 2024-03-16 160509](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/71e7f524-9fba-4e34-934c-b74bd950fa8b)

![Screenshot 2024-03-16 160530](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/d585739b-990b-4fcb-bb24-444e6b8c104e)

![Screenshot 2024-03-16 160542](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/a0257ff1-f846-424e-8cde-0bb29b52bd72)

![Screenshot 2024-03-16 160553](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/56de7c23-9b6a-4022-9f4d-48f915b324e9)

9.Create new client user. Create another virtual machine, install Windows 10, connect to private network:  <br/>

To create new user








Next we will create a new VM server which the have windows 10 for our newly created client. Start by clicking new > name it CLIENT1 > Set hardware to your PC specifications. 
Once server is created, click settings and under network, change adapter 1 to Internal Network. This is because we configured DHCP address from main controller. This mimics a corprate network.
Now start the new VM and browse to the location you put the Windows.iso file and click next. When it askes to activate windows, click "I don't have a product key", and follow the on screen instructions.
We will install Windows 10 pro because it can join the domain, home can't. Custom install followed by next. 


![Screenshot 2024-03-16 182648](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/ec9872ea-06f5-4a77-9f5d-178346cc20c3)

![Screenshot 2024-03-16 182712](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/52036531-87cc-417f-8908-2743b585b1ef)

![Screenshot 2024-03-16 182857](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/250df3cc-e337-4471-ac22-829c773e84cc)

![Screenshot 2024-03-16 183208](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/4b741acc-cf31-4d37-970c-6191fe3ddc98)

![Screenshot 2024-03-16 183248](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/587bf918-cede-41e0-82de-b8148fe8ac55)

![Screenshot 2024-03-16 183313](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/730d0bf3-2828-4cd6-a647-bc633afafacf)

![Screenshot 2024-03-16 183330](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/2251f0ad-2602-439a-a265-073e22e5f477)

![Screenshot 2024-03-16 183337](https://github.com/ssidhu1994/Active-Directory-Home-Lab/assets/141093027/62a7b777-333d-48aa-bd2e-14dbd4ddc7aa)











10.Bonus:Run PowerShell script to create 1,000 users in Active Directory:  <br/>




<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
