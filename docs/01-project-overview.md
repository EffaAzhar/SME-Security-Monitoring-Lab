# Project Overview

## Introduction

Small and medium sized enterprises (SMEs) increasingly rely on digital systems to support business operations, communication and data management. Many organisations deploy basic security controls such as antivirus software and firewalls, understanding and investigating suspicious activity remains a significant challenge. Security relevant information is often distributed across multiple operating systems, applications and network devices, making it difficult to build a complete picture of what has happened during a security event.

This project presents the design and implementation of a virtualised SME security monitoring laboratory using Windows 11, Ubuntu Server and an additional Linux administration workstation. The laboratory combines host based telemetry, authentication logs, PowerShell operational logs, firewall activity and network packet captures to investigate how security events observed across different systems can be correlated into a single investigation timeline.

Rather than focusing on offensive security or exploitation techniques, this project emphasises **defensive security monitoring, behavioural analysis and evidence correlation** within an isolated and ethically controlled virtual environment.

## Problem Statement

Security events are commonly recorded by multiple systems including operating systems, applications, authentication services and network devices. However analysing these log sources independently provides only a partial understanding of what actually occurred.

For example, an SSH authentication failure recorded by a Linux server confirms that an unsuccessful login attempt occurred but does not reveal the associated network communication, any previous reconnaissance activity or whether authentication later succeeded. Similarly a network packet capture can confirm that communication took place without identifying the authenticated user or the commands executed after login.

The absence of correlation between host and network telemetry can reduce investigative visibility and increase the time required to understand security incidents. This project investigates whether **combining multiple sources of evidence improves the reconstruction and interpretation of security relevant events within a simulated SME environment.**

## Research Question

**How can host and network telemetry be correlated to improve cyberattack visibility in a simulated SME environment?**

## Research Objectives

The objectives of this project are to:

- Design and implement a virtualised SME security monitoring laboratory.
- Configure Windows and Linux systems to generate useful security telemetry.
- Establish a baseline of normal administrative and user activity.
- Collect authentication, PowerShell, firewall and network evidence from multiple sources.
- Generate controlled and non destructive suspicious behaviours within an isolated environment.
- Correlate host and network evidence into chronological investigation timelines.
- Evaluate whether multi source correlation improves the visibility of security related events.


## Project Scope

The laboratory consists of three virtual machines connected through an isolated virtual network:

- Windows 11 virtual machine acting as an employee workstation.
- Ubuntu Server virtual machine providing SSH services and server side logging.
- Ubuntu Desktop virtual machine used for administration and controlled testing.

The project focuses on:

- Windows Security logging
- PowerShell Operational logging
- Ubuntu authentication logging
- SSH monitoring
- Firewall monitoring using UFW
- Network traffic analysis using Wireshark
- Behavioural analysis
- Multi-source log correlation
- MITRE ATT&CK behavioural mapping

The project does **not** include:

- Malware development or execution
- Exploitation of third party systems
- Password cracking
- Active Directory deployment
- Enterprise-scale SIEM implementation
- Cloud infrastructure
- Artificial intelligence or machine learning detection models
  
## Project Architecture Overview

The laboratory follows a simplified SME  architecture where a Windows workstation communicates with an Ubuntu Server across an isolated virtual network. A third Linux virtual machine is used for administration, testing and controlled simulation of security related activities.

Network communication is monitored using Wireshark while Windows and Ubuntu generate native security telemetry through their respective logging mechanisms. Each platform contributes different evidence during an investigation:

- Windows records user activity and PowerShell execution.
- Ubuntu Server records authentication events, SSH activity and firewall logs.
- Wireshark captures network communication between systems.

Combining these independent sources provides greater investigative visibility than analysing any single log source in isolation.


## Ethical Considerations

All activities performed during this project are conducted within a personally owned and isolated virtual laboratory. No third party systems, public infrastructure or production environments are targeted. Suspicious behaviours are intentionally limited to safe activities such as authentication testing, administrative commands, PowerShell enumeration and controlled network communication.

Before publishing project evidence, sensitive information including passwords, cryptographic keys, personal information, public IP addresses and system identifiers will be removed or sanitised where appropriate.

## Expected Outcomes

The expected outcome of this project is a practical demonstration of how host and network telemetry can be combined to improve investigative visibility within a simulated SME environment. The completed laboratory will provide documented evidence showing how authentication events, PowerShell activity, firewall events and network communication can be reconstructed into chronological investigation timelines using multiple independent data sources.

The project will also demonstrate practical knowledge of Windows administration, Linux administration, networking, packet analysis, security monitoring and behavioural investigation within a repeatable virtual laboratory.

## Skills Demonstrated

This project demonstrates practical experience in:

- Windows 11 Administration
- Ubuntu Server Administration
- Linux System Logging
- Windows Event Viewer
- PowerShell Operational Logging
- SSH Configuration and Authentication
- Firewall Management using UFW
- Network Packet Analysis using Wireshark
- TCP/IP Networking
- Behavioural Security Monitoring
- Multi-Source Log Correlation
- Security Event Investigation
- MITRE ATT&CK Behavioural Mapping
- Technical Documentation
- Git and GitHub Version Control


## Project Chapters

The project is organised into the following chapters:

1. Project Overview
2. Lab Architecture
3. Virtual Network Configuration
4. Windows Workstation Configuration
5. Ubuntu Server Configuration
6. Logging and Telemetry Sources
7. Normal Behaviour Baseline
8. Authentication Monitoring
9. PowerShell Behaviour Monitoring
10. Network Traffic Monitoring
11. Safe Suspicious Behaviour Simulation
12. Multi-Source Log Correlation
13. MITRE ATT&CK Mapping
14. Findings and Evaluation
15. Limitations and Future Work
