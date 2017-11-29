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

## Host, Application and Data Security

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
	
