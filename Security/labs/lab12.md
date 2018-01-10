# Lab 12.1 Setting a Minimum Password Length Policy
- Server Manager
- Tools
- Group policy management
- Expand forest
- expand domains
- expand your domain
- Right click Default Domain Policy
- Edit
- Exapand Computer Configuration
- Expand Policies
- Expand Windows Settings
- Expand Security Settings
- Expand Account Policies
- Click Password Policy
- Double Click Minimum Password Length policy
- gpupdate /force

# Lab 12.2 Setting a Password History and Minimum Password Age Policies
- Same steps as last time
- select Password History
- select Minimum Password age policy
- gpupdate /force

# Lab 12.3 Enforcing Password Complexity Requirements
- same steps as before
- set password complexity to enabled
- gpupdate /force

# Lab 12.4 Setting Policies for Account Lockouts and Log on Hours
- Server Manager
- Tools
- Active Directory Users and Computers
- Click Account Log on hours / lockouts
- select which hours to lock out
- select which hours to enable log on
- apply
- gpupdate /force