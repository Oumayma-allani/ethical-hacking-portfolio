# Network Reconnaissance with Nmap

## Overview

This project documents a hands-on network reconnaissance and enumeration exercise performed in an isolated virtual lab environment.

The objective was to identify active hosts, discover exposed ports and services, and analyze the attack surface of an intentionally vulnerable Metasploitable machine using Nmap.

## Lab Environment

- **Attacker machine:** Kali Linux
- **Target machine:** Metasploitable
- **Virtualization:** VMware
- **Network:** Isolated private lab network
- **Tools:** Nmap

> All testing was performed against intentionally vulnerable systems in a controlled lab environment.

## Objectives

- Discover active hosts on the network
- Identify open TCP ports
- Detect running services and versions
- Perform operating system reconnaissance
- Identify exposed SMB services
- Understand how network enumeration contributes to attack surface discovery

## Host Discovery

The first phase consisted of identifying active hosts within the lab subnet.

```bash
nmap -sn 10.6.6.0/24
```

The scan identified several active hosts, including the Kali testing machine and the Metasploitable target.

## Service Enumeration

Nmap service and version detection was then used against the target:

```bash
nmap -sV 10.6.6.129
```

This allowed exposed network services and their versions to be identified.

## SMB Discovery

Further reconnaissance identified SMB-related services on:

```text
139/tcp  netbios-ssn
445/tcp  microsoft-ds
```

These ports indicated that SMB enumeration could be performed during the next phase of the assessment.

## Key Findings

The reconnaissance phase revealed:

- Multiple exposed network services
- SMB services available through ports 139 and 445
- Service/version information useful for further vulnerability analysis
- A relatively large attack surface on the intentionally vulnerable target

## Security Perspective

Network reconnaissance is an important early phase of a penetration test.

Information such as exposed ports, services, versions and operating systems can help identify unnecessary services, outdated software and potential attack vectors.

## Next Step

The next project focuses on **SMB enumeration using enum4linux and smbclient**.
