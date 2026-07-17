# Lab Architecture

## Introduction

This chapter describes the virtual environment used in the project. The laboratory is designed to simulate a small business network.It contains multiple operating systems communicate across an isolated virtual network while generating security relevant telemetry.

The environment consists of three virtual machines hosted on a single Apple MacBook Pro using UTM virtualisation. Each virtual machine performs a specific role within the laboratory. It also allow security events to be observed from multiple perspectives including Windows, Linux and network traffic. Using virtual machines provides a safe and repeatable environment for learning operating system administration, network communication and security monitoring without affecting production systems.

## Host System

The virtual laboratory is hosted on an Apple MacBook Pro using Apple Silicon architecture. UTM is used as the virtualisation platform to create and manage isolated virtual machines.

| Component | Configuration |
|-----------|---------------|
| Host Device | Apple MacBook Pro |
| Operating System | macOS version 26.5.2 |
| Processor | Apple Silicon M1 |
| Virtualisation Platform | UTM |
| Purpose | Host all virtual machines used throughout the project |

## Virtual Machines

The laboratory consists of three virtual machines.

### Windows 11 Workstation
Role:
- Employee workstation
- PowerShell activity generation
- Windows Security logging
- Event Viewer analysis
- SSH client
- Web browsing
- Administrative activity

Primary telemetry:

- Windows Security Log
- PowerShell Operational Log
- Windows Defender Logs (where available)

### Ubuntu Server
Role:
- SME server
- SSH server
- Authentication monitoring
- Firewall monitoring
- Linux system administration
- Central server for investigation scenarios

Primary telemetry:

- SSH authentication logs
- systemd journal
- UFW firewall logs
  
### Ubuntu Desktop
Role:
- Administration workstation
- Network testing
- Connectivity verification
- Wireshark packet capture
- Controlled activity simulation

Primary telemetry:

- Network traffic
- Terminal activity
- Connectivity testing

## Virtual Machine Resource Allocation
The following resource allocation provides sufficient performance while allowing multiple virtual machines to operate on the same host system.

| Virtual Machine | RAM | CPU Cores | Disk | Purpose |
|-----------------|----:|----------:|-----:|---------|
| Windows 11 | To be recorded | To be recorded | To be recorded | Employee workstation |
| Ubuntu Server | To be recorded | To be recorded | To be recorded | Server |
| Ubuntu Desktop | To be recorded | To be recorded | To be recorded | Administration workstation |


## Network Design
The laboratory uses an isolated virtual network created within UTM. Each virtual machine communicates only with systems inside the laboratory while maintaining internet connectivity where required for software installation and updates. This configuration enables safe testing of authentication, remote administration and network communication without exposing activity to external systems. The detailed IP configuration and network topology are documented in Chapter 3.
The network contains:
- Windows workstation
- Ubuntu Server
- Ubuntu Desktop
- Shared virtual network

## Architecture Overview
The overall architecture is shown below.

```text
                         Internet
                             │
                             │
                     UTM Virtual Network
                             │
        ┌────────────────────┼────────────────────┐
        │                    │                    │
        │                    │                    │
 Windows 11 VM        Ubuntu Server VM     Ubuntu Desktop VM
 Workstation           SSH / Logging        Administration
        │                    │                    │
        │                    │                    │
 Windows Logs         Linux Logs          Testing Activity
 PowerShell           SSH Journal
 Event Viewer         UFW Logs
        │                    │
        └──────────────┬─────┘
                       │
                 Wireshark Capture
                       │
               Event Correlation
                       │
          Investigation Timeline
```


## Design Rationale

A multi platform environment was selected because security investigations frequently require evidence from multiple operating systems and network sources.**Windows** provides user activity and PowerShell telemetry. **Ubuntu Server** provides authentication and firewall logging. **Wireshark** provides visibility into network communication between systems. Correlating these independent sources allows individual security events to be reconstructed more accurately than relying on a single log source.

## Limitations

The laboratory intentionally remains small and focuses on practical learning rather than enterprise scale deployment. Current limitations include:

- Three virtual machines
- No Active Directory environment
- No enterprise SIEM deployment
- Limited user population
- Manual event correlation
- Apple Silicon virtualisation constraints
- Limited hardware resources compared with enterprise environments

These limitations are discussed further in Chapter 15.
