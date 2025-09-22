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

---

## Features Implemented

1. **OU & User Management**  
   - Created `DevSecOps` and `IT` OUs  
   - Provisioned users with home folders and roaming profiles  
   - Bulk import using PowerShell & CSV  

2. **Roaming Profiles & Home Folders**  
   - Home directories stored at: `\\server01\home\%username%` (mapped to `H:`)  
   - Roaming profiles stored at: `\\server01\profiles\%username%`  

3. **Group Policy Objects (GPOs)**  
   - Disabled Control Panel and Settings for certain OUs  
   - Mapped network drives via GPO preferences  

4. **Drive Mapping**  
   - Automatic mapping of `H:` drive on login  
   - Configured through GPO (Drive Maps)  

---

## Sample Outputs

- 📄 [gpresult.html](gpresult.html) — Example Group Policy Results report  
- 📄 [users.csv](users.csv) — Example bulk import file  

---

## Scripts

All scripts are in the [scripts/](scripts/) folder. Example:

- **`create-ou.ps1`** — Creates `DevSecOps` and `IT` OUs  
- **`create-users.ps1`** — Bulk imports users from CSV, sets profile paths & home folders  
- **`create-shares.ps1`** — Creates and shares `Home` and `Profiles` folders with NTFS permissions  

---

## Validation & Testing

- Verified GPO application using:  
  - `gpupdate /force`  
  - `gpresult /r` and [gpresult.html](gpresult.html)  
- Confirmed:  
  - Control Panel restricted  
  - H: drive auto-mapped  
  - Roaming profiles loaded  

---

## Next Steps

- Add screenshots of OU structure, GPO editor, and gpresult outputs  
- Expand with more GPOs (BitLocker, Windows Updates, password complexity)  
- Explore hybrid identity by connecting to Azure AD  

---

## License

This lab is for educational purposes. Feel free to fork, adapt, and reuse.  
MIT License.

