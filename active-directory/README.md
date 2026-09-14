# Active Directory

## Overview

This section documents the Active Directory implementation completed in the Enterprise IT Support Lab.

## Domain

- Domain: lab.local
- Domain Controller: DC01
- Domain Controller IP: 192.168.10.10
- Client: CLIENT01

## Organizational Unit Structure

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

## Users

### IT

- Marshal

### HR

- Arjun

## Security Groups

- IT-Support
- HR-Staff

Users were assigned to appropriate security groups to control access to organizational resources.

## Active Directory Tasks Completed

- Created organizational units
- Created domain users
- Created security groups
- Added users to security groups
- Created computer accounts
- Verified Active Directory objects using PowerShell
- Troubleshot a missing computer account
- Troubleshot a workstation trust relationship failure
- Unlocked a locked user account

## PowerShell Verification

Example command used to verify organizational units:

    Get-ADOrganizationalUnit -Filter * |
    Select-Object Name, DistinguishedName

Example command used to verify a user:

    Get-ADUser -Identity Arjun -Properties LockedOut,Enabled |
    Select-Object Name,SamAccountName,Enabled,LockedOut

## Practical Troubleshooting

The lab included real troubleshooting scenarios involving:

- Account lockout
- Missing computer account
- Domain trust relationship failure
- Security group membership
- Access control
- Domain resource access

The objective was to practice the investigation and resolution process used by IT Support and System Administrators in an Active Directory environment.
