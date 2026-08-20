# Windows Active Directory Home Lab

A self built home lab simulating a small business IT environment, using Windows Server and Windows 11 virtual machines. Built to practice core sysadmin skills and prepare for CompTIA Security+.

## Overview

This lab simulates the basic infrastructure of a small office network:
- A Windows Server domain controller managing users, groups, and shared resources
- A Windows 11 client joined to the domain, used to test real end-user scenarios
- Ongoing work toward DHCP, Group Policy hardening, and centralized logging

## Environment

| Component | Details |
|---|---|
| Hypervisor | VirtualBox |
| Domain Controller | Windows Server 2022, hostname `DC` |
| Client | Windows 11, hostname `CLIENT01` |
| Domain | `lab.local` |
| Network | Internal/private virtual network |

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
- [ ] Configure DHCP scope for automatic client IP assignment
- [ ] Apply Group Policy Objects (GPOs) for security hardening (password policy, account lockout, USB restrictions, screen lock)
- [ ] Set up audit logging and review Event Viewer logs
- [ ] Simulate an attack (e.g. brute-force logon) and demonstrate detection/mitigation

## Skills Demonstrated

- Active Directory Domain Services (AD DS) installation and configuration
- Organizational Unit (OU) and security group design
- File share permissions (NTFS + share-level)
- User account lifecycle management (creation, password resets, unlocks)
- Domain join and client-server troubleshooting

## Notes & Troubleshooting


## Screenshots


---

*This is a personal learning project built to develop hands-on Windows Server / Active Directory administration skills.*
