BrightIwara-Portfolio
Enterprise Windows Server & Azure Hybrid Lab

Author: Bright Iwara
Role: IT Support → System Administrator (Portfolio Project)

📌 Project Overview

This project demonstrates a full on-premises Windows Server environment integrated with Microsoft Azure using hybrid identity.
It includes:

Active Directory Domain Services
 DNS & DHCP
 Group Policies (Advanced)
 Folder Redirection & Roaming Profiles
 File & Storage Services
 Remote Access & WinRM
 WDS + PXE Boot deployment
 VirtualBox Replica
 Backup & Restore
 Azure AD Connect (Hybrid Identity)
 Azure Identity Security & Monitoring
 Network Monitoring & Performance
 Basic Hardening

This setup is designed as a real-world enterprise lab environment suitable for System Administrator & Cybersecurity portfolios.


📡 Network Diagram (Logical View)

                 ┌────────────────────────────────────┐
                 │           Office Network           │
                 │     Router/DHCP: 10.59.1.1         │
                 └────────────────────────────────────┘
                               │
                               │
                ┌──────────────────────────────────┐
                │   Windows Server 2022 (DC01)     │
                │   - AD DS / DNS / DHCP           │
                │   - File Services                │
                │   - GPO Management               │
                │   - Azure AD Connect             │
                │   IP: 10.59.1.50                 │
                └──────────────────────────────────┘
                               │
                               │
                ┌──────────────────────────────────┐
                │   Windows Server 2022 (Replica)  │
                │   VirtualBox Replica Target      │
                │   IP: 10.59.1.51                 │
                └──────────────────────────────────┘
                               │
                               │
                ┌──────────────────────────────────┐
                │  Windows 10 Client               │
                │  - Domain Joined BRIGHTIWARA.com │
                │  - Folder Redirection            │
                │  - GPO Applied                   │
                └──────────────────────────────────┘

                       ┌─────────────────────┐
                       │      Azure AD       │
                       │  - Users & Groups   │
                       │  - Security         │
                       │  - Hybrid Identity  │
                       └─────────────────────┘


.Active Directory Domain Services (AD DS)

✔ Installed Roles

* Active Directory Domain Services
* DNS Server
* Group Policy Management

✔ Domain Created

Domain Name: BRIGHTIWARA.com
Forest Functional Level: 2022


✔ Tasks Completed
Created OU structure:

BrightIwaraUsers
BrightIwaraComputers
BrightIwaraAdmins
Joined Windows 10 client to domain
Created & managed domain users

.DNS Configuration

✔ Forward Lookup Zone


Zone: BRIGHTIWARA.com (Primary DNS Zone)


✔ Reverse Lookup Zone

Created for network subnet.

✔ Records Created

* A Records for Server & Client
* SRV records auto-created by AD
* PTR records for reverse lookup

DHCP Server Configuration

✔ Scope
Scope Name: BrightScope
Range: 10.59.1.51 – 10.59.1.200
Gateway: 10.59.1.1
DNS: 10.59.1.50 (DC01)
Lease Duration: 8 days

✔ Reservations
Created for domain-joined machines.

Group Policy Management

✔ Policies Configured

* Background wallpaper
* Software deployment
* Restrict Control Panel
* Drive Mapping (Z:\SharedData)
* Folder Redirection (Documents)
* Security Hardening Policies
* WinRM enablement
* RDP enable policy


File & Storage Services

✔ Shared Folders

* SharedData
* UserData (Redirected Folders)

✔ Permissions

* SMB Sharing
* NTFS permissions
* Principle of Least Privilege

Folder Redirection & Roaming Profiles

 ✔ Redirection Path


\\DC01\UserData\USERNAME\Documents


✔ Result

* Documents folder now follows users between computers
* Data stored centrally on server
* Backed up automatically from server side

Remote Access & Management

✔ Tools Enabled

* RDP
* PSRemoting (WinRM)
* Server Manager Remote Access
* Firewall Rules Configured

✔ Successful tests
Manage DC01 from Client
Manage Client from DC01


WDS + PXE Boot Deployment
✔ Configured Items

* Windows Deployment Services installed
* Boot Image + Install Image added
* PXE Boot enabled in VirtualBox
* Windows 10 deployed automatically using PXE

Backup & Restore (Windows Server Backup)
✔ Completed

* Full Server Backup
* Scheduled Weekly + Daily backup
* Backup stored on secondary virtual disk


VirtualBox Replica (Server to Server)
✔ Replica Setup


Primary Server: 10.59.1.50  
Replica Server: 10.59.1.51  
Authentication: Kerberos  
Replication Frequency: 5 minutes  

✔ Outcome

Real-time VM replication for disaster recovery.


Azure AD Connect (Hybrid Identity)

✔ Configuration Summary

 Installed Azure AD Connect
 Synced On-Prem AD users → Azure AD
 Enabled Password Hash Sync
 Devices Hybrid Joined
 Service Account created
 Sync Scheduler running every 30 minutes


Microsoft Entra (Azure AD)
 Configured in Tenant

 Users & Groups
 Security Defaults
 MFA enforced
 Identity Protection (basic)
 Admin Roles (Global Admin, User Admin)



Monitoring & Performance

 Tools Used

 Performance Monitor
 Data Collector Sets
 Event Viewer (Security, Application, System)
 Resource Monitor


Hardening & Security Baseline**
 Policies Applied

 Disable SMBv1
 Firewall rules tightened
 Strong Password + Lockout Policies
 RDP restricted
 Admin Group Protection
 Logging & Audit policies


Tools Used

Virtualization

 VirtualBox


Operating Systems

Windows Server 2022
Windows 10 Enterprise

Azure Services
 Entra ID (Azure AD)
 Azure AD Connect
 Resource Groups
 Identity Protection


Skills Demonstrated

 🖥 System Administration

* AD DS
* DNS, DHCP
* GPO Management
* File & Storage Services

Cloud / Hybrid

* Azure AD Connect
* Hybrid Identity
* Cloud-backed authentication

🔐 Security

* Hardening
* Audit policies
* Access control

🛠 Infrastructure

* WDS deployment
* Backup system
* Failover replica
* Network monitoring

Conclusion

This project demonstrates full ability to deploy, manage, secure, and integrate an enterprise Windows Server environment with Azure services.
It shows the skills required for:

IT Support Analyst
Systems Administrator
Microsoft 365 / Azure Administrator
Tier 2/3 Support
Identity & Access Management
