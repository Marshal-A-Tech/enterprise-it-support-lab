# Windows Troubleshooting

## Overview

This section documents hands-on Windows troubleshooting scenarios completed in the Enterprise IT Support Lab.

## Troubleshooting Methodology

All incidents were approached using the following support workflow:

SYMPTOM → INFORMATION GATHERING → HYPOTHESIS → TEST → ROOT CAUSE → FIX → VERIFY → DOCUMENT

## Troubleshooting Scenarios Completed

### Account Lockout

- Investigated a locked Active Directory user account.
- Verified the account lockout status using PowerShell.
- Unlocked the account using Active Directory PowerShell tools.
- Verified that the account was no longer locked.
- Confirmed successful user login.

### DNS Resolution Failure

- Identified incorrect DNS configuration on CLIENT01.
- Verified connectivity to DC01 by IP address.
- Tested DNS resolution using nslookup.
- Corrected the DNS server configuration.
- Verified domain name resolution and domain controller discovery.

### Domain Trust Relationship Failure

- Investigated a workstation trust relationship error.
- Verified that the CLIENT01 computer account was missing from Active Directory.
- Created the required computer account in the correct OU.
- Restored network communication with the domain controller.
- Repaired the workstation secure channel.
- Verified access to domain resources.

### GPO Drive Mapping

- Investigated an HR network drive mapping issue.
- Used gpresult to verify Group Policy application.
- Identified the effect of a disabled GPO link.
- Investigated the Drive Map Update action.
- Removed the existing mapping using the Delete action.
- Restored the Update configuration.
- Verified successful H: drive mapping.

### Access Denied

- Investigated Access Denied when accessing the HR shared folder.
- Verified the logged-in user using whoami.
- Checked Active Directory group membership.
- Identified missing HR-Staff group membership.
- Added the user to the required security group.
- Verified restored access to the HR shared folder.

### Low Disk Space

- Investigated reduced free disk space on CLIENT01.
- Checked disk usage.
- Identified a large test file consuming approximately 60 GB.
- Removed the unnecessary file.
- Verified that available disk space returned to approximately 68 GB.

### High CPU Usage

- Investigated approximately 100% CPU utilization.
- Identified a PowerShell process consuming significant CPU resources.
- Traced the process to a CPU-intensive background job.
- Stopped and removed the background job.
- Verified that CPU utilization returned to a normal idle level.

### Windows Service Failure

- Investigated a stopped Windows Update service.
- Checked the service status using PowerShell.
- Reviewed Event Viewer and Service Control Manager events.
- Started the Windows Update service.
- Verified the service returned to Running status.

### Application Launch Failure

- Investigated an application that failed to launch.
- Verified the configured executable path.
- Used Test-Path to determine whether the executable existed.
- Identified an invalid application path.
- Verified a valid executable path.
- Confirmed successful application launch.

### Printer Troubleshooting

- Checked installed printers and printer drivers.
- Investigated the Microsoft Print to PDF printer status.
- Identified the printer queue status.
- Used PowerShell to manage the printer state.
- Verified the printer status after troubleshooting.

## Tools Used

- PowerShell
- Command Prompt
- Event Viewer
- Active Directory Users and Computers
- Group Policy Management
- Windows Services
- Windows Printer Management
- ipconfig
- ping
- nslookup
- nltest
- gpresult
- whoami
- Get-Process
- Get-Service
- Get-Printer
- Get-PrinterDriver

## Support Skills Demonstrated

- User and account troubleshooting
- Windows system troubleshooting
- Network troubleshooting
- DNS troubleshooting
- Active Directory troubleshooting
- Group Policy troubleshooting
- File and folder access troubleshooting
- Performance troubleshooting
- Service troubleshooting
- Application troubleshooting
- Printer troubleshooting
- PowerShell-based administration
- Root-cause analysis
- Verification and documentation
