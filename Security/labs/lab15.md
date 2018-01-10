# Lab 15.1 Footprinting
- what systems are up and running?
- Boot server or seven
- make sure firewall disabled
- boot Kali Linux
- configure network activity:
	- Terminal
	- ifconfig
	- if IP address is 127.0.0.1
	- configure IP address manually / start network service
		- /etc/init.d/networking start
		- ifconfig -- ip address?
	- Virtual Machine / Network Adapter
		- verify vmware recognizes network adapter
		
- Kali Linux Desktop
- Applications
- Kali Linux
- Information Gathering
- Live Host Identification
- nmap
- cmd line
	- nmap -iflist
- cmd line
	- zenmap
- target : serverIpAddress/24 ENTER
	- will start listing all the ports open on server and connected computer
- click through hosts, topology, service tabs etc

# Lab 15.2 Enumeration
- learning about the OS and services
- Kali Linux Terminal
- nmap
	- review options
- type nmap -sT -v ServerIpAddress (4 seconds)
- nmap -sS -v ServerIpAddress (37 seconds)
- with Seven ip address (2 seconds)

## Options
- -A
	- OS detrection
- can use Amap
	- amap -bqv ServerIpAddress 389
		- id service listening on server at port 389