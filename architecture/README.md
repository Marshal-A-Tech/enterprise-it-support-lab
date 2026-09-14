# Architecture

## Lab Environment

### Domain Controller

- Hostname: DC01
- Operating System: Windows Server 2022
- IP Address: 192.168.10.10
- Domain: lab.local
- Services: Active Directory Domain Services, DNS, DHCP

### Client

- Hostname: CLIENT01
- Operating System: Windows 10/11
- Network: DHCP
- DHCP Address Range: 192.168.10.100 – 192.168.10.200
- Domain: lab.local

## Network

| Device | IP Address | Role |
|---|---|---|
| DC01 | 192.168.10.10 | Domain Controller, DNS, DHCP |
| CLIENT01 | DHCP | Domain Client |

## Active Directory

lab.local
└── Company
    ├── Users
    │   ├── IT
    │   ├── HR
    │   ├── Finance
    │   └── Sales
    ├── Computers
    │   ├── IT
    │   └── Office
    └── Groups

## Core Services

- Active Directory
- DNS
- DHCP
- Group Policy
- File Sharing
- NTFS Permissions
- Windows Troubleshooting
- Event Viewer
- PowerShell
