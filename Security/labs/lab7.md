# Lab 7.1 Verifying the integrity of the hosts file
- Make sure domain is configured in Windows Server 2012
- Windows 7 Client is connected to the domain

## Explanation
- when you download software from internet
- did anyone change data/ is software successfully downloaded
- Download Kali
	- can run checksum
	- will have same value as on site

## lab 7.1 Integrity of hosts file
- download sigCheck
- put it on desktop
- download a file: e.g. WinSCP
- look for checksums on website
- cmd prompt as administrator
> cd Desktop
> sigcheck.exe -a -h winscp576.setup.exe
- wait a long time
- scroll down
- check if checksum (SHA1) is the same as listed on the website
- means program is downloaded without errors

# Lab 7.2 Installing the FTP Server Service and Wireshark
- Windows Server 2012
- using FTP client to connect to the server
- Administratior Account
- Server Manager
- Add roles and features
- click X Role based
- set up WebServer(IS)
- click next
- next, next
- scroll down  X to FTP server - FTP service
- next
- install
- creates a directory in C; drive where all ftp files will be
- Server Manager: All Servers
	- IIS
	- right click on server
	- Internet Information Services
	- Right Click Sites:
	- set own site: Sites>FTPtest	
	- Browse for folder: C: inetpub
		- ftp root
	- no SSL, next
	- clikc Basic
	- Allow Access to :All users
		- read permission	
		- write permission
- Server Manager > Tools > Active Directory Users and Computers
	- display users
- Add USers - Users> New> Set First name and last name,
set login, create password > Next
- go into ftptest
	- can set up messages (Welcome/ Exit messages/ banner)
- Apply
- FTP Authentication enabled
- FTP firewall support (if it doesn't work: enable entry in firewall)

## Set Up FTP Client
- login into ftp server:
	- cmd prompt as admin: ping server
	- cmd prompt **ftp server**
- if problems:
	- network and security
		- disable Windows Firewall
- no problems:
	- login with user you created (mbloom)
	- use password
- make a notepad file and put in inetpub/ftproot
- in cmd prompt use lcd (local directory
	-ls 
	- nameoftextfile.txt
	- "Transfer complete"
- check C: Users: administrator.GB for text file
- bye to log out of ftp

## Other notes
- Network and Sharing Center > Windows Firewall>
	- Advanced Sharing Options
	- turn on network discovery
- Windows Firewall Advanced Settings:
	- add inbound rule
	- New Rule > Port > TCP >  (21) > Allow Conenction
	- domain Only > FTP inbound rule 
	- finish
- Allow a program through Windows Firewall
	- inbound rules > New Rule
	- Port > TCP> 21 > Allow connection > Domain Only > FTP Inbound Name> Finish

- now you can go and enable windows fire wall

# Lab 7.3 Capturing and Analyzing FTP Traffic
- using Wireshark

# Lab 7.4 Caputuring and Analyzing Telnet Traffic
- using Wireshark

### Telnet Service
- login to Windows Server as administrator
- Server Manager > Add Roles and Features
- Role Based > server.gb.com
- TelnetServer > Next
- Install 

#### Once Installed
- Windows > Run > services.msc
- Telnet> Automatic> Apply > Start
	- up and running
- ServerManager ? Tools > ActiveDirectory Users and Computers > Use User >> Add > TelnetClients
- Windows 7:
	- Login as administrator
	- Control Panel> Programs and Features > Turn Windows Features on> [X] Telnet Client > OK
- cmd prompt > **telnet server**
	- hostname
	- dir
- retrieve data, put data there
- not very secure