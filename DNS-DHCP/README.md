# DNS and DHCP

## Overview

This section documents the DNS and DHCP configuration, verification, and troubleshooting completed in the Enterprise IT Support Lab.

## DNS Configuration

### Domain Controller

- DNS Server: DC01
- IP Address: 192.168.10.10
- Domain: lab.local

DNS was configured on DC01 to provide name resolution for the Active Directory environment.

## DNS Verification

Verified domain name resolution using:

    nslookup lab.local

Verified domain controller name resolution using:

    nslookup DC01.lab.local

Both names successfully resolved to:

    192.168.10.10

## DNS Troubleshooting

A deliberate DNS failure was created on CLIENT01 by configuring an incorrect DNS server:

    8.8.8.8

The client could still communicate with DC01 by IP address, but normal DNS resolution failed.

The configured DNS server was investigated and compared with the domain controller DNS server.

An explicit DNS query against the correct DNS server was used to confirm that the DNS service itself was functioning:

    nslookup DC01.lab.local 192.168.10.10

## DNS Resolution

The root cause was an incorrect DNS server configured on CLIENT01.

The DNS configuration was corrected to:

    192.168.10.10

After the correction, DNS resolution and domain controller discovery were successfully verified.

## DHCP Configuration

### Scope

- Scope Name: Office-LAN
- IP Range: 192.168.10.100 – 192.168.10.200
- Subnet Mask: 255.255.255.0
- Exclusion Range: 192.168.10.1 – 192.168.10.50
- DNS Server: 192.168.10.10
- DNS Domain: lab.local
- Default Gateway: Not configured for the isolated lab network

## DHCP Client Verification

CLIENT01 was configured to obtain its network configuration automatically through DHCP.

Verified the DHCP lease using:

    ipconfig /all

CLIENT01 received:

- IPv4 Address: 192.168.10.100
- Subnet Mask: 255.255.255.0
- DHCP Server: 192.168.10.10
- DNS Server: 192.168.10.10
- DNS Suffix: lab.local

## Network and Domain Verification

Verified connectivity to DC01:

    ping 192.168.10.10

Verified DNS resolution:

    nslookup lab.local

Verified Active Directory domain controller discovery:

    nltest /dsgetdc:lab.local

All tests completed successfully.

## Troubleshooting Flow

SYMPTOM → Domain name resolution failed on CLIENT01

INFORMATION GATHERING → Checked IP configuration, DNS configuration, and connectivity

HYPOTHESIS → CLIENT01 was using an incorrect DNS server

TEST → Compared DNS configuration and tested name resolution against the correct DNS server

ROOT CAUSE → CLIENT01 was configured to use 8.8.8.8 instead of the internal DNS server

FIX → Corrected the DNS configuration to 192.168.10.10

VERIFY → Confirmed DNS resolution, DHCP configuration, DC connectivity, and domain controller discovery
