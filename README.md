# Active-Directory-Lab--PS-Academy-Windows-Server-2019-and-Windows-10-VM
This lab demonstrates a small Active Directory environment built on Windows Server 2019 with a Windows 10 client VM.
A compact AD lab built on Windows Server 2019 and Windows 10 that demonstrates OU management, user provisioning (single + bulk), roaming profiles, home folders, mapped drives, and a GPO that prohibits access to Control Panel/PC Settings. Includes PowerShell snippets, GPO config notes, and troubleshooting tips.
# Active Directory Lab — PS Academy

This project demonstrates a small **Active Directory lab** built with **Windows Server 2019** (Domain Controller) and a **Windows 10 VM** (client).  
It covers user provisioning, OU structure, Group Policy Objects (GPOs), mapped drives, and roaming profiles — simulating what you’d see in a real-world enterprise environment.

---

## Lab Overview

- **Domain/Forest**: `psacademy.local`
- **Server**: `server01.psacademy.local` (Windows Server 2019, AD DS, DNS, File Server)
- **Client**: `win10-client.psacademy.local` (Windows 10 joined to domain)
- **Organizational Units (OUs)**: `DevSecOps`, `IT`
- **Users**: Created individually and via CSV bulk import
- **Policies configured**:
  - Prohibit access to Control Panel & PC Settings
  - Map home drives automatically
  - Roaming profiles and home folders

---

## Repository Contents

