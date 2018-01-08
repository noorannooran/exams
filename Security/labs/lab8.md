# Lab 8.1 Configuring Widnows Firewall on Windows Server 2012
- share a desktop from windows 7 to windows server
- Windows Server 2012
- Server Manager > Local Server > Remote Desktop > Allow Remote connectiosn to this computer
	- Select Users > Add predefined user (molly bloom)
- Server Manager > Tools > Group Policy Managerment
	- click gb.com
	- expand domains
	- expand gb.com
	- expand domain controllers
	- click default domain controller policy
		- right click : click edit
- Editing Domain control policy
- computer configuration> Policies > Windows settings
- expand security settings
	- expand local policies
	- user right agreement click
	- click allow log on through remote desktop servies
	- click Define policy settings
	- add User or group
	- remote desktop users browse > check name for Remote Desktop : Users
	- Apply
- Force group policy update
- Run cmd > cmd prompt  **gpupdate /force**
- Firewall > Advanced Setting> Inbound Rules> Remote Desktop : User TCP-in UDP-in
	- ensure it says Allow and Allow
- Windows 7:
	- remote desktop connection	
	- Computer: server
	- login with mbloom / user
- check in cmd promp ping server

# Lab 8.2 Configuring Windows Firewall on Windows 7
- Windows 7 as administrator
- Control Panel> Program and Features > IIS Internet Information Services > OK
- Browser> your IP address > IIS7
- C: inetpub/ wwwroot
	- create new text document
	- write some html save as Default.html
- log in to windows server
	- login as administrator
- browser > windows 7 ip 
	- will not get a response
	- because firewall is blocking communication

## Setting up the firewall on windows 7
- Windows 7 ? control Panel> firewall> advanced settings
- inbound rule > World Wide Services HTTP traffic in
	- General > Enabled > Apply

- Go back to server
- try to browser> windows 7 ip 

- IIS Services Manager > Sites> Can change Port that the IIS service is run on 
- Windows 7 Firewall> Inbound Rules > Create New Rule > Port > Next (specify port number 81 or whatever)
	- next > allow connection > Next > Name the rule : Private Website or whatever
- go back to Winodws Server >  Browser> Windows 7ip:port81 (or whatever new port is)

# Lab 8.3 Installing and Configuring an SSH Server
- uses port 22
- add an entry into firwall

## Steps set up Server
- Windows Server 2012
- explorer: google freesshd download tool
- downloads: save to desktop
- double click the .exe.
	- create desktop icon
	- yes create private key
	- no system service
- click the sshd
right click > settings > see that it's running
- theres an RSA  and DSA key
- create a banner:
	- text document on desktop SSHbanner
	- write a message for the banner, save
- settings> banner message > browse for banner message
- settings again> Encryption = any
- add a User under  users
	- Administrator set up login	
	- domain gb.com
	- ok
- can set up mbloom 
	- click shell
	- can log into shell

# Lab 8.4 Installing and Configuring an SSH Client
## Client
- download PuTTy from website
- install putty.exe
- save on desktop
- run putty.exe
- make sure host name is server
- open putty
- Network and Sharing Centre> Firewall > check if it's up and running

- go to server 
- Netowrk and Sharing Center> Advanced Settings > Inbound rules
- set up a new rule
	- port > next >  TCP > port number 22
	- allow connection > next > next
	- name the inbound rule Inbound SSH
- run putty.exe
	- host name server
	- login as administrator
	- with password
	- again, as mbloom
	- enter password
	- confirm it works