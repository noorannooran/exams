Midterm Review
## Introdution to Security
- challenges of securing info
- define security and why its important
- common types of attacks
- basic steps of attacks
- 5 basic principles of defense

### Challenges of Securing Information
1. Universally connected devices
- speed of attacks
- availability and simplicity of attack
- delays in security updates
- distributed attacks
- greater sophistication of attacks
- faster detection of vulnerabilities
- weak security update distribution
- BYOD & User confusion

#### Note
- the more convenient, the less secure

### Definition of Security
1. Confidentiality
   - authorized parties access information
2. Integrity
   - correct information, no alteration
3. Availability
   - accessible to **authorized** users
4. Authentication
   - genuine person **not** imposter
6. Accounting
   - tracking of events

#### Types of Attackers
- Cybercriminals
  - launch attacks against users
- Script Kiddies
  - limited knowledge of computer and network
- Brokers
  - uncover vulnerabilities and auction them off
- Insiders
  - employees, contractors, business partnets
- Cyberterrorists
  - ideologically motivated
- Hactivists
- State-sponsored attacks
  - spying on citizens, disrupt governments
  
### Basic Steps to an Attack
**Kill chain**: systematic process to target and engage an enemy
1. Reconnaisance
   - probe for information about the system
- Weaponization
   - create an exploit (e.g. virus) -> payload
- Delivery
  - email attachment/ through server
- Exploitation
  - triggers intruder's exploit
- Installation
  - installed to attack, or install a backdoor
- Command and control
  - remotely controlled by attacker
- Action on objectives

### Defending
1. Layering
   - several methods of protection
   - e.g. Crown Jewels
	 - layer 1 protective casing
	 - layer 2 special room with sensors
	 - layer 3 monitored by video cameras
	 - layer 4 surrounded by security guards
- Limiting
  - authorized personnel only
- Diversity
  - layers of defense must be **diverse**
- Obscurity
  - e.g. obscuring security guard shift changes
- Simplicity
  - e.g. guards do not understand how the other defenses work

### Importance of Security
- prevent data theft
- prevent identity theft
- avoid consequences of not securing information
- maintaining productivity
- foil cyberterrorism

## Malware & Social Engineering Attacks
- define malware
- types of malware
- payloads of malware
- types of social engineering psychological attacks
- social enginerring physical attacks

### Malware
- software that enters a system without the user's knowledge or consent that performs an unwanted/ harmful action

### Types of Malware
1. Circulation
   - spreading rapidly
2. Infection
   - infext/ embed self into system
- Concealment
  - avoid detection
- Payload capabilities
  - stealing password/ getting user data
  
#### Circulation
- Viruses
  - reproduces itself automatically on **host** computer
  - cannot spread by itself
  - can infect a file
- Worms
  - primary purpose to **spread** from computer to computer
  - aka NETWORK VIRUSES
  - cannot infect a file
- Trojans
  - exe masquerading as another activity
  - with the user's knowledge, malicious payload
  - can infect a file

#### Concealment
- **rootkit** hide the actions or presence of other types of software
- e.g. through music cds

#### Payload Capabilities
- collect data:
  - Spyware
  - Adware
	- can track user's activities and send to third parties
  - Ransomware
  - keylogger (software or hardware)
	- capture keystrokes, capture screen caps
- delete data
  - **logic bomb** code that lies dormant until triggered
- modify security settings
  - **backdoor** gives access to computer, program, service
- launch attacks
  - allows computer to be placed under remote control
  - **zombie** infected computer
  - **botnet** collection of zombies
	- under control of **bot herder**

### Social Engineering Psychological Approaches
- gathering information for an attack
- impersonation
- phishing:
  - pharming: redirects user to fake site
  - spear phishing: specific users
  - whaling: e.g. CEOs
  - vishing: telephone call
- spam
  - unsolicited emails
  - image spam cannot be filtered
- hoax
  - false warning e.g. from IT department
- typo squatting
  - near- URLS e.g. goggle.com
- watering hole
  - smaller group of specific individuals
  - id common website and infect with malware

#### Social Engineering Tactics
1. Authority
- Intimidation
- Concensus/ social proof
- Scarcity
- Urgency
- Familiarity/ Liking
- Trust

#### Physical Social Engineering Tactics
1. Dumpster diving
- Tailgating
  - authorized person opens the door, anyone can follow
- Shoulder surfing

## Application and Networking-Based Attacks
- list and explain the different types of server-side web application attacks
- define client-side attacks
- explain how overflow attacks work
- list different types of networking based attacks

### Server Side Web Application Attacks
- Cross-site Scripting (XSS)
  - launch attacks on other computers that access the server
  - inject scripts into a web application server
  - **Solution**: turn off scripting in client browser to reduce risk, also reduces ability to use dynamic websites
- SQL Injection
  - targets SQL servers
  -  malicious commands
  - **Email Address Unknown**
	- user input is filtered, SQL attack cannot be applied
  - **Server Failure**
	- user input is not filtered, directly sent to database
- Directory Transversal
  - uses malformed input
  - move from root dir to restricted directories
> **zero day attack** exploiting previously unknown vulnerabilities

### Client Side Application Attacks
>  target vulnerabilities in client applications that interact with compromised server

#### Drive By Download
- id vulnerable web server, inject content through scripting applications, gain access to web server OS
- craft zero-pixel **iframe** to avoid visual detection
- users visit infected site, browser downloads script through hidden inline frame
- script will instruct browser to connect to attackers webserver to download malware
  
#### Header Manipulation
- attacker can modify referrer field to hide that the webpage is coming from another site

#### Cookies
- can be stolen and used to impersonate the user, track browsing or buying habits

#### Attachments
- files attached to email
- used to spread Trojans, etc.

#### Session hijacking
- attacker impersonates user using session token
- uses XXS
- eavesdrop on transmission or guessing a User Token

#### Malicious Add-Ons
- attacker creates malicious add-ons to launch attacks against the user's computer
- Java, Adobe Flash Player, Apple QuickTime, Adobe Acrobat Reader

#### Impartial Overflow Attacks
- target either server or client

##### Buffer overflow attack
- process attempts to store dtaa in a RAM beyond the boundaries of fixed-length storage buffer
- dtaa overflows into adjacent memory locations **buffer overflow**
- the storage buffer contains the **return address**, attacker can overflow the buffer with a new address -> malicious code

### Networking Based Attacks
- Denial of Service (DoS) : distributed DoS
- Ping flood : ICMP requests
- Smurf attack : ICMP request, hide attacker address
- SYN flood attack
  - send SYN segments with modified source address
- Interception:
  - Man in the Middle
	- receives data from devices, passes it on
	- **passive** : capture, record, sends to the recipient
	- **active** : contents are captured and altered before sending to the recipient
  - replay
	- copy of transmission before sending to the recipient, then used later
- Poisoning
  - ARP poisoning
	- modify **MAC** addresses in ARP cahce so the IP address points to a different computer
  - DNS poisoning
	- substitute DNS address (**IP address**), auto redirected to another devlice 
- Attacks on access rights
  - privilges to access hardware and software
  - **privilege escalation**
	- exploit a vulnerability to gain access to resources
  - **transitive access**
	- System 1 can access System 2, System 2 can access System 3, System 1 can access System 3
	- Microsoft Active Directory
	  - all domains trust each other in two-way transitive trust
	  
#### Summary
> Networks = high priority, single vulnerability = thousands of devices


## Host, Application and Data Security
- list steps for securing a host computer
- define application security
- explain how to secure data

### Securing the Host
> **security control** : any device or process used to reduce risk
> **administrative controls**: actions users may do, must do, cannot do
> **technical controls**: managed by devices
- Security Control
- External Perimeter Defences
  - restrict access to areas where equipment is located
- Internal physical access security
  - hardware locks
  - proximity readers
  - access lists
  - mantraps
  - protected distribution systems for cabling
- Hardware Security
  - cable lock
- Securing the OS
- Security through configuration
- Security through design
- Securing with anti-malware
  - pop up blockers
  - anti spam
  - antivirus
  - antispyware
  - host-based firewalls

### Application Security
- development: security should be considered through all phases of SDLC
  - application configuration baselines
  - secure coding concepts
  - application hardening and patch management

### Securing Data
> DLP Data Loss Prevention: security tools used to recognize and id data critical to the organization and ensure it's protected
- Data in Use, data in transit, data at rest

#### 3 types of DLP sensors
1. DLP Network Sensors
   - installed on perimeter of network : monitor network traffic **in transit**
- DLP Storage Sensors
  - installed on network storage devices : protect data **at rest** ensure files on hard drives are encrypted
- DLP Agent Sensors
  - installed on each host device: protect data **in use** : watch for actions like printing, copying to USB, burning to CD or DVD

### Summary
> Security control: any device/ process used to reduce risk
> Hardware security: physical security: protect the hardware of the host system
> One means of securing data is through data loss prevention DLP

## Cryptography
- define cryptography
- describe hash, symmetric, asymmetric cryptographic algorithms
- list the ways in which cryptography is used

### Definitions
> **cryptography**: scrambling of data so it cannot be read
> science of transforming information into secure form
> **stenography**: hides existence of data
> **cryptographic algorithm**: procedures based on a mathematical formula used to encrypt and decrypt data

### Cryptography and Security:
- **Confidentiality**: encrypted information can only be viewed by those provided the key
- **Integrity**: encrypted information cannot be changed except by authorized users that have the key
- **Availability**: authorized users are provided the decryption key to access the information
- **Authentication**: proof that the sender was legitimate and not an imposter can be obtained
- **Non-repudiation**: individuals are prevented from fraudulently denying their involvement in a transaction

### Algorithms
1. Stream Cipher
   - substitution cipher; substitutes one letter for another
   - fast when plaintext is short; consumes more overhead if plaintext is long
   - more prone to attack; engine that generates stream does not vary
2. Block Cipher
   - takes a block of plaintext
   - considered more secure; output is more random
3. Sponge Function
   - takes input a string of any length, returns a string of any requested variable length
4. Hash Algorithm
   - creates a **digital fingerprint** AKA *digest* of a set of data
   - aka "Hashing"
   - **not** encryption: used to determine integrity of message, contents of file
   - **one-way** cannot be used to reveal original data
   - considered secure if:
	 1. Fixed size
	 - Unique
	 - Original
	 - Secure
   - examples: MD5, SHA-1, SHA-2, (SHA-224, SHA-256, SHA-512)
   - **whirlpool**: a *digest* of 512 bits
   
### Symmetric Cryptographic Algorithms
> primary weakness: distributing and maintaining a secure single key among multiple users, scattered geographically
- aka **private key cryptography**
- uses same key to encrypt and decrypt
- keys should be kept private

#### **DES** Data Encryption Standard
- one of first widely popular symmetric cryptography algorithms
- 56 bit key length
- block cipher
- divides plaintext into 64-bit blocks, exe DES algorithm 16 times
- **56-bit key is no longer secure**

#### 3DES (Triple Data Encryption Standard)
- hardware performance > software performance
- addresses several key weaknesses of DES
- no longer considered secure

#### AES : Advanced Encryption Standard
- 3 steps on every block (128 bits) of text
  - multiple rounds dependent on key size:
	- 128 : 9 rounds
	- 192 : 11 rounds
	- 256 : 13 rounds **aka AES-256**
- bytes are substituted and rearranged, multiplication performed based on arrangement
- **still secure**: no successful attacks on AES

#### One TIme Pad (OTP)
- plaintext + random key
- cannot be broken mathematically; does not require use of the computer
- **pad**: long sequence of random letters
  - combined with plaintext = **ciphertext**
- in order to decrypt, recipient must have copy of the pad
- used once, then destroyed
- **unbreakable**

### Asymmetric Cryptographic Algorithms
- uses 2 keys instead of 1
  - **public key** : known to everyone - used to encrypt message
  - **private key** : known only to the individual - used to decrypt message
- called **public key cryptography**
- can work in both directions
- use **Digital Signatures** : electronic verification of the sender:
  - verify sender
  - prevent sender from disowning message
  - prove integrity of message
- use digital signature + public key encryption

#### RSA 
- most common
- stands for last names of developers Rivest, Shamir, Adleman
- slower than other algorithms:
  - DES : approx 100x faster in software; 10000x faster in hardware
- uses prime numbers

#### ECC
- uses sloping curves
- elliptic curve
- alternative for prime-number for **mobile and wireless**
  - smaller key sizes
  
#### Quantum Cryptography
- behaviour of microscopic objects
- quantum computing <> quantum cryptography
  - e.g. observing photons randomly for polarizations,
	- records the polarization, sends to other person,
	  - other person records, sends measurements, person A confirms which are correct which are converted into a string of bits that forms their secret key
	  
### Key Exchange
> problem: exchanging symmetric private ey
> **Out of band communication** separate means of communications

#### Solutions:
- DH Diffier Hellman: requires both parties to agree on a large prime number and related integer, both separately create the same key
- DHE Diffie-Hellman Ephermeral - uses different keys; keys are **temporary**, used once and discarded
- ECDH Elliptic Curve Diffie-Hellman - uses elliptic curve
- Perfect Forward Secrecy - public key systems that generate random public keys different each session
  - if compromised, can only reveal contents of one message
  
### Encryption through software
- File and file system cryptography
  - using OS's file system
- PGP/GPG Pretty Good Privacy/ Gnu Privacy Guard
  - use both symmetric and asymmetric cryptography
  - used for protecting digital signatures and 3DES or IDEA (GPG doesnt use IDEA- patent)
- Windows Encryption: can set in Advanced Attributes of file, storing the file in an encrypted folder, using Cipher.exe
- Whole Disk Encryption Cryptography: entire disks
- BitLocker drive encryption

### Software Encryption
- USB device encryption
  - all data is auto-encrypted
  - requires password before connecting
  - tamper-resistent cases
  - remotely track and control activity on devices
  - can be remotely disabled
- Hard disk drive encryption
  - can perform a **cryptographic erase** on specific data
- TPM Trusted Platform Module
  - provides cryptographic services; on the motherboard
  - random number generator
  > pseudo random generator  is PRNG
- Suite B : NSA approved set of cryptographic algorithms
  - AES 128 or 256
  - signatures with ECC e56 and 384 bit numbers
  - key exchange : ECDHE
  - hashing: SHA-2
  - not released to public

# Chapter 7: Netowrk Security
## Security Through Network Devices
- use security features in standard network hardware
- *layered security* aka *defense in depth*
- more difficul for attackers

### OSI Reference Model
- Open Systems Interconnection
- how a network prepares data for deliver over the network
- how data is handled when received
- **layers**

### OSI Layers
1. Physical Layer
   - send / receive signals from network
2. Data Link Layer
   - divide data into frames
   - error detection/ correction
3. Network Layer
   - picks the route for the packet
   - handles addressing
4. Transport Layer
   - error free data given to user
5. Session Layer
   - permit two parites to communicate
6. Presentation Layer
   - how data is presented to user
7. Application layer
   - user interface

## Switches
- work like hubs except can read MAC addresses
- Unicast - send to one
- Broadcast - send to all

### Monitoring Traffic on Switches
1. Port mirroring
   - copy traffic to a monitoring port
2. Network Tap (Test Access Point)
   - device installed on the network
   
### Switch Attack and Defense
1. Mac Flooding
   - overflow switch address table with fake MAC addresses
   - use a switch that can close ports with too many MAC addresses
2. MAC address impersonation
   - configure only one port to each MAC address
3. ARP poisoning
   - forged ARP packet
   - use ARP detection appliance
4. Port mirroring
   - connect device to mirror port
   - secure switch in locked room
5. Network tap
   - tap is connected to intercept frames
   - restrict physical access
   
## Routers
- Network Layer 3
- forward packets across networks
- can filter specific types of network traffic

## Load Balancers
- evenly distribute work across network
- advantages:
  - reduced overload of server
  - optimized bandwidth
  - downtime reduced
- software OR hardware

### layer 4 load balancers
- act upon data in Network and Transport layer protocols
### layer 7 load balancers
- distribute requests based on data found in Application Layer protocols (HTTP)
- can use HTTP headers, cookies, data to make a decision on distribution

### Security
- detect and stop attacks directed at server or application
- detect and prevent DoS and protocol attavks
- hide HTTP error pages, remove server identification headers
- hide internal network information

## Proxies
- act as substitutes for the primary device
- client connects first to proxy server, checks cache, connects to external web server and requests the service, then forwarded to the client
- **application-aware proxy** : *knows* the application protocols it supports

### Advantages
- increased speed
- reduced costs
- improved management
- stronger security

## Hardware
### Firewalls
- inspect packets, accept or deny entry
- first line of defense

#### Filtering
1. Stateless packet filtering
   - permits or denies based on conditions set by admin
2. Stateful packet filtering
   - keeps a record of a connection, makes decisions based on the connection and the conditons

#### Actions
- Allow
- Drop
- Reject
- Ask

#### Firewall Methods
1. Rule Based Firewalls
   - use firewall rules
   - contain info such as:
	 - source address
	 - destination address
	 - source port
	 - destination port
	 - protocol
	 - direction
	 - action
 - static in nature, straightforward, inflexible
2. Application-Aware Firewalls
   - NGFW Next-Generation Firewall
   - id applications that send packets
   - make decision sbased on the application
   - e.g. Web application Firewall
	 - looks at applications using HTTP

## Spam Filters
- Install spam filter with SMTP server:
  - simple, effective
  - filter lists on port, sends non-spam to SMTP server
  - spammer does not know it is not received
- Install spam filter on the POP server
  - spam passes through SMTP server and delivered to mailbox
  - increased cost in storage, transmission, backup, data
- Third Party Entity
  - directed to third party, cleansed before redirected to organization
  - changing MX Mail Exchange record

## VPN Concentrators
- virtual private network
- enables users to enter a public network as if it were secure
- encrypts **ALL** data transmitted between remote device and network


### VPN Types
- Remote Access VPN
  - or virtual private dial-up network
  - user-to-LAN
  - remote users
- Site to Site VPN
  - multiple users connect to other sites over the internet

### Protocols
1. SMTP Simple Mail Transfer Protocol: Port 25
2. POP Post Office Protocol: Port 110

### VPN Transmissions
- **endpoint**
  - end of tunnel between VPN devices
- **VPN concentrator**
  - aggregates thousands of VPN connections
- built-in VPN endpoint:
  - handles all VPN setup, encapsulation, encryption

#### Tunneling protocols
- Generic Routing Encapsulation (GRE)
  - framework for how to pakcage guest protocol for transport over IP
- IPsec
  - subprotocols:
	- ESP: Encapsulated Security Payload
	  - encrypts using a symmetric key
	- AH: Authentication Header
	  - creates a difgest of packer header
- Remote access uses IPsec or L2tP Layer2 Tunneling Protocol

### Software vs Hardware
- Software: on mobile devices gen.
  - flexibility
  - worse performance/ security
- Hardware: site-to-site gen.
  - more security
  - better performance
  - more flexibility
  - only network device manages VPN functions
  - used for collecting two LANs through a VPN tunnel

## Internet Content Filters
- monitor internet traffic and block access to pre-selected websites REACTIVELY
- URL filtering
- malware inspection
- prohibiting file downloads
- profiles
- detailed reporting

### Web Secure Gateways
- PROACTIVE
- blocks malicious content in real time as it appears
- can block:
  - Adware and Spyware
  - Cookies
  - Instant messengers
  - P2P file sharing
  - Script Exploits
  - TCP/IP malicious code attacks

### Intrusion Detection and Protection
- IDS Intrusion Detection System
  - detect attacks as it occurs
- IPS Intrusion Prevention System


# Chapter 8: Administering a Secure Network
## Common Network Protocols
### TCP/IP Transmission Control Protocol/ Internet Control Protocol
   - IP : adressing and routing (Layer 3)
   - TCP: main transport layer (Layer 4)  
### Seven Layers
1. Physical
2. Data Link
3. Network
4. Transport
5. Session
6. Presentation
7. Application

### TCP/IP protocols
- ICMP Internet Control Message Protocol
- SNMP Simple Network Management Protocol
- DNS Domain Name System
- File transfer and storage:
  - NetBIOS
  - Telnet
- a new and more secure version of IP

### ICMP
1. Informational and Query Messages
- Error Messages

#### Fields
1. Type
- Code
- Checksum
- Message Body

### ICMP Attacks
- Network Discovery
  - send ICMP echo requests
  - send ICMP address mask request to a host
	- determine subnet mask
- Smurf Attack
  - broadcast ping request
  - ask response from all computers
- ICMP Redirect Attack
  - send packets to another router AKA malicious device
- Ping of Death
  - exceeds size of IP packet
  - causes host to crash
  
### SNMP
- allows admins to remotely monitor, manager, configure devices on a network
- agent or service that listens for commands
- **community string** password
  - read-only
  - read-write

#### Vulnerabilities SNMPv1 &2
- public and private community strings
- default strings unchanged = vulnerability
- strings transmitted as cleartext

### DNS
- maps symbolic name with IP address
- distributed among different servers

#### DNS Attacks
- DNS Poisoning
  - substitutes addresses
  - computer is redirected to a fraudulent IP address
  - prevented by using *BIND* Berkeley Internet Name DOmain
	- ignore DNS records not relevant to query
	- DNSSEC Domain Name System Security Extensions
	- allows to be digitally signed
- DNS Transfer
  - asks valid DNS server for a zone transfer
  - map internal netowrk

### FTP
- FTP
- SCP Secure Copy Protocol

#### FTP
- connect to FTP server
  - Trivial File Transfer Protocol (TFTP)
  - uses less memory, limited functionality
  - used for transfer of config files between devices
- Command Prompt
- Web Browser
- FTP client

> active mode: client opens a command channel connection
- firewall can see data channel connection as unsolicites
- PORT command
> passive mode: client initiates the data channel connection
- PASV command
- server responds with TCP port number

#### Vulnerabiltiies
- cleartext not encryption
- vulnerable to man in the middle attacks

### Secure Transmissions over FTP
- FTPS FTP Secure
  - SSL Secure Sockets Layer
  - TLS Transport Layer Security
  - encrypts commands sent over control port
  - the data port may or may not be encrypted
- Secure FTP SFTP
  - entire protocol of itself
  - single TCP port
  - encrupts and compresses all data and commands
- Secure Copy Protocol (SCP)
  - encrypts files and commands
  - file transfer cannot be interrupted and resumed
  - UNIX and Linux platforms
  
### Storage Protocols
- SAN Storage Area Network
  - deticated network storage facility
- Protocols
- isCSI Internet Small Computer System Interface
  - IP based
  - transmit data over LANs, WANS, Internet
- FibreChannel FC
  - high speed storage network protocol
  - 16 GB per second
- Fibre Channel Over Ethernat FCoE
  - use fast Ethernet networks
  
#### Fibre Channel
- FC Zones
  - hard zone:
	- all members id by physical port number
  - soft zone:
	- software based
	- unauthorized zone members can see restricted data

#### NetBIOS
- transport protocol used by Windows to allow applications on different devies to communicate over a LAN
  - NetBIOS over TCP/IP (NBT protocol)
- attacker can get:
  - computer names
  - contents of remote cache
  - list of local NetBIOS names
  - list of unresolved names
- recommended disabled or used only if necessary

#### Telnet
- text-based communication
- application
- terminal emulation program that connects to a server

##### Vulnerabilities
- data unencrypted
- passwords can be discovered
- use SSH instead of TelNet

### IPV6
- 64 bits instead of 32
- enhanced security features

## Network Administration Principles
- Procedural rules
  - authoritative, direction for conduct
- Technical Rules
  - dictated by procedural rules
  - e.g. configuring a firewall
- rule-based managerment approach:
  - following rules that addreess security, analyzing and monitoring logs, network design management, port security

### Device Security: Routers
- create a network design
- use meaningful router name
- secure all ports
- set a strong admin password
- make changes from the console and not remotely

### Attacks
- DoS : use a Flood Guard
  - controls a device's tolerance for unanswered service requests
  - helps prevent a DoS atttack
  - max number of developing connections device can tolerate

#### Monitoring and Analyzing Logs
- seucrity access log
  - reveal requests for files
- audit log
  - record which user performed an action
- event logs
  - unsuccessful events
- firewall log
  - IP addresses rejected and dropped
  - probes to ports that have no application services running
  - source-routed packets: packets that originate outside the network
  - suspicious outbound connections
  - unsuccesful logins

### Log Management Issues
- multiple devices generating logs
- large volume of data
- different log formats
- use a centralized device log analyzer

## Network Design Management
### Network Separation
- seperate secure from unsecure parts
- e.g. "air gap"

### Loop Protection
- switching loop can cause a broadcast storm
- broadcast storm prevented with loop protection
  - Spanning Tree Algorithm STA
	- determine switch has multiple ways to communicate, determine best path while blocking others

### VLAN management
- virtual LAN
- configure empty switch ports to connect to unused VLAN
- change default VLAN names
- confifure ports on the switch that pass packets to explicitly forward specific tags
- configure VLANS so that public devices are not on a private VLAN

### Port Security
- disable unused interfaces
- using MAC limiting and filtering
- IEEE 802.1x

### IP Telephony
- cost savings
- simplified management
- application development
- reduced infrastructure requirements
- reduced regulatory requirements
- increased user productivity

#### IP Telephony Attacks
- OS : softphones operating on standard PCs
- VoIP protocols: inadequate authentication, integrity protection, confidentiality
- Network acknowledgement: flood VoiP with DoS attacks
- Spam

### Virtualization
- multiple physical storage devices can be viewed as a single unit
- *Host Virtualization*
  - virtual machine is created
  - runs a **hypervisor** that manages VM OS
  - supports one or more **guest systems**

#### Advantages
- host availability
- host elasticity
- reduce costs
- uninterrupted server access:: live migration
- patch compatibility
- create snapshots
- security control testing
- sandboxing

#### Disadvantages
- will be vulnerable if not updated
- single hypervisor compromised = all compromised
- security tools do not adapt well to multiple VMs

### Cloud Computing
- on demand self service
- univrsal client support
- invisible resource pooling
- immediate elasticity
- metered services

#### Clouds
- Public Cloud
  - services are offered to all users with access through Internet
- Community Cloud
  - open to specific organizations
- Private Cloud
  - private network
  - reduces cost savings
- Hybrid Cloud
  - private/ public

#### Service Models
1. Software as a Service
- Platform as a Service
- Infrastructure as a Service


# Chapter 11 : Access Control Fundamentals
## Terminology
- *Identification*:
  - e.g. a user logging in with username
- *Authentication*:
  - e.g. checking the user's credentials (password)
- *Authorization*:
  - granting permission to take the acton (e.g. logging in)
- *Access*:
  - right given to access specific resources (e.g. files, applications)
- *Object*:
  - specific resource ie. file or device
- *Subject*:
  - user or process trying to access an object
- *Operation*:
  - action taken by the subject over the object e.g. deleting a file

### Roles of Individuals
- *Owner*:
  - responsible for the information
  - determines level of security needed
- *Custodian*:
  - day to day activities have been assigned to
  - reviews security settings, maintains record of access
  - AKA administrator
- *End-User*:
  - accesses information in the course of routine job responsibilities
  - follows org. security guidelines
  
## Access Control Models
- framework for controlling access

### Discretionary Access Control (DAC)
- least restrictive
- every object has an owner
- owners can create and access, and give permissions
- used on UNIX and Windows

#### Weaknesses
- risk: decisions of the end-user to set level of security
- inheritance: subjects permissions inherited by any programs executed
  - e.g. Malware could use subject's permissions
- can automatically reduce user's privilege level 

### Mandatory Access Control (MAC)
- most restrictive
- assigns user's controls according to the custodian
- user has no freedom to set controls
- used in military settings
- match object labels with subject labels
  - can have equal or greater in order to access the subject

#### Elements
1. Labels
   - classification labels
	 - e.g. confidential, secret, top secret
   - privilege labels
	 - e.g. clearance
2. Levels
   - top secret > secret > confidential

#### Implementations
1. Lattice model
   - different "rungs" have different security levels
   - subjects are assigned a rung, as well as objects
2. Bell-La Padula (BLP) model
   - additional restriction
   - prevents subjects from creating a new object, performing functions on objects lower than their own
   - variation: Biba Integrity Model
	 - protect data integrity
3. Manadatory Integrity Control (MIC)
   - windows uses
   - controls access to securable objects
   - uses SID : security identifier
   - links SID to integrity level
   - *User Account Control*
	 - must enter administrative password before installing software
	 
### Role Based Access Control (RBAC)
- Non Discretionalu Access Control
- "Real worl"
- based on user's job function in an organization
- permission is given to roles, users are assigned roles

### Rule Based Access Control (RBAC)
- **automated provisioning**
- dynamically assigned roles to subjects based on rules defined by adminadventure castle in the clouds in the sky top floor

## Best Practices
1. Separation of Duties
   - users with too many responsibilities
   - don't give any one person total control
2. Job Rotation
   - individuals moved from responsibilites
   - limit the time ind. are in a position to manipulate security
   - expose avenues for fraud
   - reduce burnout
3. Least Privilege
   - limiting access to what user needs to complete tasks
4. Implicit Deny
   - if condition is not explicity met, access is r
5. Mandatory Vacations
   - audit while away

## Access COntrol List
- set of permissions attached to an object
- who is allowed to access
- what operations they can perform

## Access Control Entry
- each entry in the ACL Table

### Four Items
- SID
- Access Mask
  - rights allowed and denied
- Flag
  - what permissions are granted?
- set of flags
  - inherit permissions?
  
### ACL Limitiations
- inefficient
- difficult to manage in enterprise setting


### Group Policy
- Microsoft Windows Feature
- stored in Group Plicy Objects
  - linked to domains, websites
- can update many users by updating Group policy Object

#### Local Group policy
- used to configure settings not a part of Active Directory

### Account Restrictions
- time of day
  - when a user can log in
- account expiration
  - *orphaned account* remain active after user has left
  - *dormant account* one that has not been accessed
  - security risks; therefore account expiration

## Authentication Services
- AAA Authentication, Authorization, Accounting Server
- or authentication server

### Common AAA Servers
- RADIUS
  - industry standard
  - messages never directly sent between device and server
- Kerberos
  - authentication system
- Terminal Access Control Access Control System
  - forward username and password to a centralized server
- LDAP Lightweight Directory Access Protocol
  - directory service: database stored on netowrk 
- SAML Security Assertion Markup Language
  - XML standard that allows web domains to exchange authentication and authorization data with each other
  
# Review Questions
## Chapter 8
1. Which high-speed storage network protocols used by a SAN is IP based?
   - a. isCSI
2. Which Fibre Channel zone is the most restrictive?
   - FC hard zone
3. An attacker can use NetBIOS to determine the following except ____
   - c. list of remote NetBIOS names
4. Which type of log can provide details regarding requests for specific files on a system>
   - b. access log
5. WHich type of device log contains the most beneficial security data?
   - c. firewall log
6. WHich type of cloud is offered to all users?
   - c. public cloud
7. Which of these would NOT be a valid Internet Control Message protocol error message?
   - d. Router Delay
8. ICMP is used by each of these attacks EXCEPT ___
   - ICMP poisoning
9. Which version of SNMP is considered the most secure?
   - SNMP v3
10. Which DNS attack replaces a fraudulent address for a symbolic name?
	c. DNS poisoning
11. Which of these is the most secure protocol for transferring files?
	c. SFTP
12. Each of these is a technique for securing a router EXCEPT?
	- a. making all configuration changes remotely
13. Which statement about a flood guard is true?
	- b. It prevents DoS or DDoS attacks
14. Each of these is an entry in a firewall log that should be investigated EXCEPT?
	- b. successful logins
15. if a group of users must be separated from other users, what is the most secure network design?
	- b. connect them to different switches and routers
16. Why is loop protection necessary?
	- c. it prevents a broadcast storm that can cripple a network
17. what does MAC limiting and filtering do?
	- a. it limits devices that can connect to a switch
18. In a network using IEEE 802.1x a supplicant
	- b. makes a request to the authenticator
19. Which statement is true regarding security for a computer that boots to Apple Mac OS X then runs a Windows Virtual Machine?
	- d. The Windows virtual machine needs its own security
20. Which of the following is NOT a security concern for virtualized environments?
	- c. Virtual servers are less expensive than their physical counterparts

## Chapter 11
1. What is the current version of TACACS?
   - TACACAS+
2. How is SAML used?
   - b. Allows secure web domains to exchange user authentication and authorization data
3. A RADIUS authentication server requires that the ___ be authenticated first
   - supplicant
4. Which of these is NOT part of the makeup of the AAA elements in network security?
   - d. determining user need
5. With the development of IEEE 802.1x port security the __ authentication server has seen even greater usage
   - a. RADIUS
6. WHich authentication protocol is available as a free download that runs on Microsoft Windows, Apple Mac OS X and Linux?
   - d. Kerberos
7. What is the version of the X.500 standard that runs on a personal computer over TCP/IP?
   - d. LDAP
8. A user entering her username would correspond to the __ action in access control?
   - b. identification
9. A process functioning on behalf of the user who attemps to access a file is known as a(n) ____
   - c. subject
10. What is the name given to the individuals who periodically reviews security settings and maintains records of access by users?
	- b. custodian
11. In the __ model, the end- user cannot change any security settings
	- d. Mandatory Access Control
12. Which statement about Rule Based Access Control is true?
	- a. It requires that a custodian set all rules
13. ___ in access control means that if a condition is not explicitly met, then access is to be rejected
	- c. Implicit Deny
14. Which of these is a set of permissions that is attached to an object?
	- a. Access Control List
15. Which Microsoft Windows feature provides centralized management and configuration of computers and remote users who are using Active Directory?
	- c. Group Policy
16. An ___ constructs LDAP statements based on user inputs in order to retrieve information from the database or modify its contents
	- d. LDAP injection attack
17. What is the least restrictive access control Model?
	- a. Discretionary Access Control
18. The principle known as ___ in access control menas that each user should be given only the minimal amount of privileges necessary for that person to perform his job function
	- c. least privilege
19. An ___ is the person who is responsible for the information, determines the level of security needed for the data, and delegated security duties as needed
	- a. owner
20. In the MAC model every subject and object ____
	- c. is assigned a label


## Quiz 1 A&A

1. What type of malware is heavily dependent on a user in order to spread?
   - virus
-  What term is used to describe a means of gathering information for an attack by relying on the weakness of individuals?
   - social enginerring
- WHat is the term used to describe unsoclicited messages received on instant messaging software?
  - spam? **incorrect?**
- Select the term for individuals who want to attack computers yet lack the knowledge of computers and networks needed to do so
  - Script Kiddies

#### Match the following with the appropriate definitions
- A software program that delivers advertising content in a manner that is unexpected and unwanted
  - Adware
- Computer code that lies dormant until it is triggered by a specific logical event
  - logic bomb
- A logical computer network of zombies under the control of an attacker
  - botnet
- A false warning designed to trick users into changing security settings on their computer
  - hoax
- A phishing attack that using telephone calls instead of emails
  - vishing/ voice phishing
- Software code that gives access to a program or service circumventing normal security protections
  - Trojan
- Computer virus written in a script known as macro
  - macro virus
- Software or hardware device that captures and stores each keystroke that a user types
  - keylogger
- phishing attack that targets specific users
  - spear phishing
- malicious computer code that reproduces itself on the same computer
  - computer virus

### Q&A continued
- In information security, what constitutes a loss?
  - loss of information
  - financial loss due to time
  - loss of reputation
- One of the armoured virus infection techniques utililizes encryption to make virus code more difficult to detect, in addition to separating virus code into different pieces and injecting throughout the infected program code. what is the name for this technique?
  - Swiss Cheese
- What is the type of malware that appears to have a legitimate use but actually contains something malicious
  - Trojan
- Which of the following is not one of the four methods for classifying the various types of malware?
	- Source
- According to the US bureau of labor statistics what percentage of growth is the available job outlook supposed to reach by the end of the decade?
  - 22%
- Select the information protection item that ensures information is correct and that no unauthorized person or malicious software has altered that data
  - Integrity
- The physical procedure whereby an unauthorized person gains access to a location by following an authorized user is known as?
  - Tailgating
- In what kind of attack can attackers make use of hundreds of thousands of computers under their control in an attack agaianst a single server or network?
	- logical
	
### True or False
- Spreading similarly to a virus, a worm inserts itself malicious into a program or data file
  - False
- The demand for certified IT professionals who know how to secure networks and computers is at an all-time low
  - False
- Security is the goal to be free from danger as well as the process that achieves that freedom
  - True
	
