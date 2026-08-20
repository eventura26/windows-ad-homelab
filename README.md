# Windows Active Directory Home Lab
 
A self-built home lab simulating a small business IT environment, using Windows Server and Windows 11 virtual machines. Built to practice core sysadmin skills and prepare for CompTIA Security+.
 
## Overview
 
This lab simulates the basic infrastructure of a small office network:
- A Windows Server domain controller managing users, groups, and shared resources
- A Windows 11 client joined to the domain, used to test real end-user scenarios
- Ongoing work toward DHCP, Group Policy hardening, and centralized logging
## Environment
 
| Component | Details |
|---|---|
| Hypervisor | VirtualBox |
| Domain Controller | Windows Server, hostname `DC01`, static IP `192.168.10.10` |
| Client | Windows 11, hostname `CLIENT01` |
| Domain | `lab.local` |
| Network | VirtualBox Internal Network (`adlab`) |
| OU Structure | Ventura Users (Finance, HR, IT, Sales sub-OUs), Ventura Groups, Ventura Computers |
| DHCP Scope | `192.168.10.100` – `192.168.10.200` |
 
## What's Been Built So Far
 
- [x] Promoted Windows Server to a Domain Controller (Active Directory Domain Services)
- [x] Joined a Windows 11 client to the domain
- [x] Created Organizational Units (OUs) to organize users and computers
- [x] Created security groups and assigned users
- [x] Set up shared folders with group-based permissions
- [x] Tested end-user scenarios:
  - Verified users could access only their assigned shared folders
  - Performed password resets
  - Unlocked locked-out accounts
- [x] Installed and authorized the DHCP Server role on DC01
- [x] Created a DHCP scope (192.168.10.100–200) and confirmed CLIENT01 receives an automatic lease
- [x] Reorganized AD structure: moved CLIENT01 from the default Computers container into a dedicated `Ventura Computers` OU for proper GPO scoping
- [x] Applied a domain password policy via GPO (12-char minimum, complexity required, 90-day max age) and verified enforcement
- [x] Applied an account lockout policy via GPO (5 failed attempts, 15-min lockout) and simulated a lockout to verify it triggers correctly — then unlocked the account via AD
- [x] Applied a screen lock policy via GPO (User Configuration, linked to Ventura Users) and verified password-protected wake
- [x] Restricted local Administrators group membership on CLIENT01 via Restricted Groups GPO, and verified enforcement
- [ ] Set up audit logging and review Event Viewer logs
- [ ] Explore centralized logging (e.g. Wazuh) for a lightweight SIEM setup
- [ ] Simulate a broader attack scenario and document detection/mitigation
## Skills Demonstrated
 
- Active Directory Domain Services (AD DS) installation and configuration
- Organizational Unit (OU) and security group design
- File share permissions (NTFS + share-level)
- User account lifecycle management (creation, password resets, unlocks)
- Domain join and client-server troubleshooting
- DHCP server deployment and scope configuration
- Group Policy Object (GPO) design and troubleshooting, including Computer vs. User Configuration scope
- Security hardening: password policy, account lockout policy, screen lock enforcement, and least-privilege local admin restriction
- Diagnosing and correcting GPO application issues caused by AD object placement (OU structure)
## Notes & Troubleshooting
 
See [`issues-and-fixes.md`](./issues-and-fixes.md) for problems encountered along the way and how they were resolved.
 
## Screenshots
 
See the [`screenshots/`](./screenshots) folder for visual walkthroughs of each stage.
 
---
 
*This is a personal learning project built to develop hands-on Windows Server / Active Directory administration skills.*
