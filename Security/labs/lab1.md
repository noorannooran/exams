- 80 or  60 GB RAM needed
- need to have the ISO's available
- will be available on the lab machine

# Lab 1 Create Windows Server 2012 RS Virtual machine
1. Start VMWorkStation
- New Virtual Machine
- Install from disc or image
- Drag image in or browse for image
- use 60 GB
- Memory 2 GB
- install in folder VMs
- follow install instructions
- selecting Operating System : Select second option:
	- Windows Server 2012 R2 Standard Evaluation Server with a GUI
- Accept agreement
- Custom Install Advanced Option
- New Partition: Full Capacity (60GB)
- Select new Partition for primary disc
- will take a while to install
- allow to restart when needed

## Set up settings
- User name : Administrator
- Password: Pa$$word
- Finish

## Send CTRL + ALT + DEL
- login using set password

# Lab 1 b Create Windows 7 Professional Virtual machine **NOT HOME EDITION**
1. Start VMWorkstation
2. New Virtual Machine
- Install from disc or image
- browse for Windows 7 Professional ISO
- Continue
- Unselect Easy Install
- Continue
- Default: Capacity 60GB
- Memory 2GB
- Finish
- Save In VMs folder
- Default Installation Settings
- Next
- Install
- Accept License Terms
- Next -> Custom Advanced Installation
- Drive > New > Maximum GB > Format
- Next
- Allow to Install, will take some time
- Once Installation is complete:
- username test
- type a password: Pa$$word
- Don't need the product key (uncheck box)
- settings - set proper time
- set as Home Network
- cmd ipconfig to check that you have connection

# Lab 1c Live boot of Kali Linux Virtual machine
1. VmWorkStation
- File > New
- Create new machine from ISO
- use disc image > look for Kali Linux ISO
- continue
- asks what OS - set up as Linux - Ubuntu 64
- Default settings : 20 GB hard drive capacity
	- memory 1GB
- don't need to change these default settings
- Finish
- select folder VM where virtual machines are stored
- first screen: Select Live (amdx64) LIVE BOOT NOT INSTALL
- Allow to boot, will take a few minutes
- Terminal ifconfig see if you're getting an ip address

- **make sure all firewalls are disabled for windows 7 and windows server**
- **make sure you can ping from each machine to each machine **

# Lab 1D Create a domain in Windows Server 2012 and connecting Windows 7 Professional as a client to the domain
## Windows Professional
1. Log in to Windows 7 Professional
- Control Panel > Admin tools > Computer management> Local users > Users> Administrator
- right click > new password > create password
- right click > properties > General> unclick account is disabled
- **make sure windows firewall is off for future labs **

## Windows Server
1. **firewall off**
- Log into Windows Server
- Add Roles and Features
- Click next
- Role based feature
- Next
- Select server from server pool (keep as is)
- Select Active Directory Domain Service
- Set up DNS Server (same as Windows Server)
- Continue (ignore Warning)
- Next
- Next
- Next
- Restart the destination server automatically if required
- Install
	- will take a while
- Click on Exclamation mark in Server Manager
- Remote this server to become a domain controller
- Add a new forest
- root domain name gb.com
- Next
- Password for domain controller : Pa$$word
- confirm password: Pa$$word
- Next
- Next (ignore warning)
- Wait
- Next
- Wait
- Keep all settings as is
- Next
- Check that the domain name is gb.com
- Next
- Ignore Warnings (static ip address)
- Install (Ignore warning)
- Wait
- Restarts
- CTRL + ALT + DEL
- GB\Administratior
- Login with Pa$$word
- ServerManager
- Local Server
- shows you AD DS is running
- DNS is running

## Connect Windows 7 to Windows Server
1. get IP address of Windows Server
- get IP address of Windows 7
- see if they will ping eachother 
- Windows 7 Network Properties > Local Connection > 1pV4
- SET DNS ip to IP address of server
- Desktop
- Left click Windows 
- Computer 
- Properties
- Change Settings 
- Click Domain
- Write gb.com
- username Administrator
- password is Pa$$word
- should be able to see "Welcome to gb.com domain"
- now connected to domain
- Restart
- Will show Test_PC\test
- Right click Windows
- Computer
- Properties
- domain : gb.com
- can rename PC to "client"

