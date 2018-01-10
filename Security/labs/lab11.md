# Lab 11.1 Setting NTFS Permissions
- Log on server as Administrator
- confirm you are on domain
- click folder icon
- double click local disk C:
- create a new folder name Sales
- open Sales
- create new text document named January
- return to C:
- Right click Sales folder and click Security tab
- In the Group or user name box
- if Authenticated Users does not exist,
- click edit
- add "Authenticated"
- Check names
- OK
- open administrative tools
 
Server Manager
- tools
- Active Directory users and computers
- right click users
- create new user
- create nonadministrative user named Nicole Diver with username ndiver
- password Pa$$word
- close
- opem C:\Sales
- right click January -> Properties
- Security
- grey area = inherited permissions from container
- Edit
- Remove Server\ users permission
- OK
- cancel
- January Properites - Advanced
- Double Click Authenticated Users
-Advanced = disable inheritance
- convert inhertied permissions into expliict permission
- users, edit, select a principal
- type Administrators
0 select administrators for server, click ok
- click check box in Full Control row
- select Allow for Type
- Click OK


# Lab 11.2 Using NTFS Permissions
- log on to server as Nicole Diver
- SERVER\ndiver
- navigate to C: Sales
- try to createa  text file february
- try to delete january
- if necessary click Continue in File access denied box
- CLick no

- Navigate to C:
- create dir named Nicole
- create textfile named Diver
- save and close
- remove Authenticated Users, Administrators and Users from the NTFS permissions
- leave the SYSTEM account
- give Nicole Driver full control of the file
- log off

# Lab 11.3 Setting and Testing Share Permissions
- log in to server as Administrator
- navigate to C: Nicole
- Open Diver
- Right Click
- Properties
- Security
- Advanced
- Continue
- Change
- Type Administrators
- Check Names
- Ok
- Apply
- Right Click Driver
- Properties
- Security
- Edit
- Add DOmain Admins
- Click OK
- Diver Properties
- Advanced Domain Admins
- Edit
- Show advanced permissions
- Select:
	- traverse folder/ execute file
	- list folder/ read data
	- read attributes
	- read extended attributes
	- read permissions

- Server
- Server Manager
- Tools
- Active Directory Users and Computers
- NEw group
- name Research
- global security group
- Make two more groups Quality and Audit
- right click users
- click new - user
- create 3 new user accounts
	- edward said esaid Research, Quality
	- kent williams kwilliams Quality
	- william strunk wstrunk Audit
- C root
- create folders and text documents
- set share permissions, remove everyone, add appropriate security groups
- deny permission: yes > ok > close

- Folders:
	- Manuscripts / Tallesin  
		- Quality: allow change, read
		- Research: deny full control, change, read
	- Gloassaries/ Merck
		- Research: read
	- Contracts /GNU
		-  Audit: change, read
- log into Windows Seven as edsaid
- Start
- Control Panel
- Network and Internet
- View network computers and devices
- Click Turn on Network discovery and file sharing
- enter Admin username and password
- click yes
- double click Server
- see 3 folders shared
- try to modify the files
- do the same with the other 2 users		



# Lab 11.4 Auditing Permissions 
- Windows 7 as administrator
- firewall off
- server as administrator
- firewall off
- go to http://emcosoftware.com/permissions-audit/download
- save to desktop
- install
- uncheck box next to Lauch EMCO permissions audit XML professional
- Finish

- ServerManager
- tools
- active directory users and computers
- expand domain
- click new create one OU called research and another OU called Marketing
- create new User (research OU)
- more in lab :/

### Allow users to log on locally
- Server Manager
- Tools
- Group Policies
- Default Domain Controller Policy
- Edit
- Computer Management
- Plicies
- Windows Settings
- Expand Security Settings
- Select Local Policies
- User Rights Management
- Right CLick Allow Logon Locally
- Click on Properties
- Add needed users
