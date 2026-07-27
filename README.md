
# SME Security Monitoring and Threat Detection Lab

A practical cybersecurity project demonstrating how multiple sources of endpoint telemetry can be collected, analysed and correlated to improve cyberattack visibility within a simulated Small and Medium sized Enterprise (SME) environment.

This repository documents the complete design, implementation and evaluation of a virtualised Security Information and Event Management (SIEM) laboratory built using **Wazuh**. The project integrates Windows and Ubuntu endpoints to demonstrate behavioural monitoring, file integrity monitoring, PowerShell logging, security configuration assessment and incident investigation through alert correlation. Rather than focusing solely on tool deployment, the project explores **how different security monitoring capabilities work together to provide greater visibility into endpoint activity and support security investigations.**


# Lab Architecture


```
                    Internet
                        │
                        │
          ┌─────────────┴─────────────┐
          │                           │
     Windows 11                 Ubuntu Desktop
          │                           │
          └─────────────┬─────────────┘
                        │
                 Wazuh Agents
                        │
                        │
                Ubuntu Server
              Wazuh Manager / SIEM
                        │
                        ▼
        Behavioural Monitoring
      File Integrity Monitoring
 Security Configuration Assessment
     Incident Investigation
```


# Project Overview

Modern cyber attacks generate large volumes of endpoint telemetry from multiple sources. Analysing these events individually often provides only limited visibility into attacker behaviour.

This project demonstrates how a Security Information and Event Management (SIEM) platform can centralise and correlate security telemetry from Windows and Linux endpoints, allowing security analysts to investigate suspicious activity more effectively.

Throughout the project, Wazuh was configured to collect security events from multiple monitoring capabilities, including:

- File Integrity Monitoring (FIM)
- PowerShell Script Block Logging
- Behavioural Detection
- Security Configuration Assessment (SCA)
- Windows Event Logs
- Linux Authentication Logs


# Project Objective

The objective of this project is to design and implement a practical security monitoring laboratory that demonstrates how endpoint telemetry can be collected, analysed and correlated to improve cyberattack visibility within a simulated SME environment.


# Research Question

> **How can host and endpoint telemetry be correlated to improve cyberattack visibility within a simulated SME environment?**


# Laboratory Environment

| Component | Technology |
|-----------|------------|
| SIEM Platform | Wazuh |
| Wazuh Manager | Ubuntu Server |
| Windows Endpoint | Windows 11 ARM |
| Linux Endpoint | Ubuntu Desktop |
| Virtualisation | UTM |
| Host Machine | Apple MacBook Pro (Apple Silicon M1) |


# Technologies Used

- Wazuh SIEM
- Ubuntu Server
- Ubuntu Desktop
- Windows 11
- PowerShell
- Windows Event Logs
- PowerShell Script Block Logging
- File Integrity Monitoring (FIM)
- Security Configuration Assessment (SCA)
- OpenSSH
- Linux Authentication Logs
- UFW Firewall
- Wireshark
- Git & GitHub

# Skills Demonstrated

- SIEM Deployment and Configuration
- Endpoint Monitoring
- Behavioural Detection
- File Integrity Monitoring
- Security Configuration Assessment
- PowerShell Logging
- Security Event Analysis
- Alert Correlation
- Incident Investigation
- Windows Security Monitoring
- Linux Administration
- Technical Documentation
  
# Repository Structure

```
SME-Security-Monitoring-and-Threat-Detection-Lab
│
├── README.md
├── docs/
│   ├── 01-project-overview.md
│   ├── 02-lab-architecture.md
│   ├── 03-Wazuh-Server-Deployment.md
│   ├── 04-Endpoint-Agent-Deployment.md
│   ├── 05-Baseline-System-Activity.md
│   ├── 06-File-Integrity-Monitoring.md
│   ├── 07-PowerShell-Script-Block-logging.md
│   ├── 08-Behavioural-Detection-and-PowerShell-Reconnaissance.md
│   ├── 09-Security-Configuration-Assessment(SCA).md
│   ├── 10-Incident-Investigation-Through-Alert-Correlation.md
│   └── 11-Project-limitations-and-Future-Improvements.md
│
└── screenshots/
```


# Key Monitoring Capabilities

### Endpoint Monitoring

Security telemetry is continuously collected from Windows and Ubuntu endpoints and forwarded to the Wazuh Manager for centralised analysis.


### Behavioural Monitoring

PowerShell Script Block Logging captures detailed command execution, enabling behavioural analysis rather than simply recording process execution.

### File Integrity Monitoring

Critical files and directories are monitored for file creation, modification and deletion events, improving visibility into unauthorised system changes.

### Security Configuration Assessment

Endpoint configurations are evaluated against recognised CIS Benchmarks, allowing insecure configurations to be identified before they are exploited.


### Incident Investigation

Multiple sources of telemetry are correlated to reconstruct endpoint activity and support incident investigations through a centralised SIEM platform.

# Key Learning Outcomes

Throughout this project I gained practical experience in:

- Deploying and configuring a SIEM platform
- Monitoring Windows and Linux endpoints
- Collecting and analysing endpoint telemetry
- Investigating PowerShell activity
- Detecting behavioural indicators
- Assessing endpoint security posture
- Correlating alerts during security investigations
- Documenting technical projects using GitHub

# Project Limitations

The laboratory was intentionally developed within a resource constrained virtual environment. Some advanced capabilities, such as Wazuh Vulnerability Detection and Microsoft Sysmon could not be fully implemented due to hardware limitations associated with the Apple Silicon virtual environment. 

# Future Improvements

Future enhancements could include:

- Vulnerability Detection
- Microsoft Sysmon integration
- MITRE ATT&CK mapping
- Sigma rule integration
- AI-assisted alert prioritisation
- Active Directory domain environment
- Additional Windows and Linux endpoints
- Automated response using Wazuh Active Response

# Conclusion

This project demonstrates that meaningful cyberattack visibility is achieved through the collection and correlation of multiple sources of endpoint telemetry rather than relying on a single monitoring capability. By integrating behavioural monitoring, File Integrity Monitoring, PowerShell logging, Security Configuration Assessment and incident investigation techniques, this laboratory demonstrates how a SIEM platform can provide comprehensive visibility into endpoint activity within a simulated SME environment. The project also highlights the importance of understanding practical implementation challenges, evaluating technical limitations and continuously improving security monitoring capabilities through iterative development.

## Author

Cybersecurity portfolio project developed by **Effa Azhar**.

GitHub: **https://github.com/EffaAzhar**
