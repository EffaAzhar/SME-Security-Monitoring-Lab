# Chapter 09 : Security Configuration Assessment (SCA)

## Research Question

**How can continuous security configuration assessment improve cyberattack visibility by identifying insecure system configurations before they can be exploited?**

# Introduction

While behavioural monitoring focuses on detecting what users and attackers do on a system, security monitoring must also evaluate **how securely the system itself is configured**. Even if no malicious activity is currently occurring, weak security settings may increase the likelihood of a successful attack.
Security Configuration Assessment (SCA) enables organisations to continuously assess endpoint configurations against recognised security best practices such as the Center for Internet Security (CIS) Benchmarks. By identifying insecure configurations before they are exploited, organisations can reduce their attack surface and strengthen their overall security posture.
In this chapter, Wazuh's Security Configuration Assessment module was used to evaluate the Windows 11 endpoint against the **CIS Microsoft Windows 11 Enterprise Benchmark v3.0.0**. The collected results demonstrate how configuration assessment complements behavioural monitoring by providing visibility into the security posture of monitored systems.

## What is Security Configuration Assessment?

Security Configuration Assessment (SCA) is a host based security capability that evaluates whether an operating system complies with recognised security baselines and industry best practices.
Unlike vulnerability scanners, which search for missing patches or vulnerable software versions, SCA focuses on identifying insecure operating system configurations that could increase organisational risk.
Wazuh performs these assessments by comparing endpoint configurations against predefined policies such as the CIS Benchmarks and reporting whether each security control passes or fails.
Examples include:
- Weak password policies
- Insecure account settings
- Poor authentication controls
- Disabled security features
- Incorrect registry configurations
- Missing operating system hardening

## Why Security Configuration Assessment Matters

Many successful cyber attacks occur because systems are misconfigured rather than because software vulnerabilities exist.
Continuous configuration assessment enables security teams to identify these weaknesses before attackers exploit them. Rather than waiting for suspicious behaviour to appear, organisations can proactively reduce their attack surface through improved security configuration.
Examples include:

- Weak password policies enabling brute force attacks
- Default administrator accounts remaining unchanged
- Blank passwords being permitted
- Weak account lockout policies
- Missing system hardening

# Practical Activity

The Windows 11 endpoint was assessed using Wazuh's Security Configuration Assessment module.

The assessment was performed against:

**CIS Microsoft Windows 11 Enterprise Benchmark v3.0.0**

The assessment automatically evaluated hundreds of individual security controls. Each evaluated control was classified as:
- Passed
- Failed
- Not Applicable

Detailed information was also provided for each individual security control including:
- Technical rationale
- Description
- Recommended remediation
- Compliance mappings
- Assessment method

# Results

The Security Configuration Assessment successfully analysed the Windows endpoint against **482 individual CIS security checks**.

The assessment reported:

- **123 Passed checks**
- **349 Failed checks**
- **10 Not Applicable checks**

Overall compliance score:

**26%**

The failed controls primarily related to password policy and account security settings while correctly configured controls were automatically identified as compliant.
Each assessment included detailed remediation guidance and compliance mappings to recognised frameworks as following which provides security analysts with both technical findings and practical recommendations for improving endpoint security.

- CIS Controls
- PCI-DSS
- ISO 27001
- SOC 2
- CMMC

# How This Improves Cyberattack Visibility

Behavioural monitoring answers the question:

> **"What happened?"**

Security Configuration Assessment answers the question:

> **"Why was it possible?"**

For example behavioural monitoring may identify repeated authentication attempts against an endpoint.

Security Configuration Assessment can reveal whether:

- Password complexity is weak
- Password history is insufficient
- Administrator accounts use predictable names
- Account security policies require strengthening

Combining behavioural telemetry with configuration assessment provides significantly greater cyberattack visibility than either approach independently.
Security analysts gain visibility into both attacker behaviour and the underlying system weaknesses that may have enabled the attack.
This layered visibility supports more effective threat hunting, prioritised remediation and improved defensive decision making.

# What My Work Demonstrates

This practical exercise demonstrates that endpoint visibility extends beyond monitoring user behaviour. Using Wazuh's Security Configuration Assessment module, the Windows endpoint was automatically evaluated against the **CIS Microsoft Windows 11 Enterprise Benchmark v3.0.0** providing a detailed assessment of its security posture. The assessment successfully identified both compliant and non compliant security controls while supplying technical explanations, remediation guidance and compliance mappings for each finding.

Unlike behavioural monitoring, which detects actions performed on the endpoint, Security Configuration Assessment identifies weaknesses in the operating system configuration that may increase the likelihood of future attacks. Within this simulated SME environment, combining behavioural detection with continuous configuration assessment provides a more comprehensive understanding of endpoint security and directly supports the overall objective of improving cyberattack visibility.

# Conclusion

This chapter demonstrated how Security Configuration Assessment enhances endpoint visibility by continuously evaluating operating system security settings against recognised industry benchmarks. The successful assessment of the Windows endpoint using the CIS Microsoft Windows 11 Enterprise Benchmark illustrates how Wazuh can identify insecure configurations, provide remediation guidance and measure compliance against established security frameworks.

When combined with the behavioural monitoring techniques implemented in previous chapters, Security Configuration Assessment enables security analysts to understand both **how attackers behave** and **which security weaknesses may have enabled their activity**. Together these capabilities strengthen cyberattack visibility and support proactive security management within SME environments.

# Evidence

## Figure 9.1 – Security Configuration Assessment Dashboard

The Security Configuration Assessment dashboard summarising the Windows endpoint compliance score against the CIS Microsoft Windows 11 Enterprise Benchmark v3.0.0.

![SCA Dashboard](../images/ch09/23-sca-overview.png)



## Figure 9.2 – Failed Password History Policy

Example of a failed CIS control identifying that the password history policy does not meet the recommended security baseline. Wazuh provides the rationale, remediation guidance and compliance mappings for the failed control.

![Password History Policy Failed](../images/ch09/24-password-history-failed.png)



## Figure 9.3 – Failed Administrator Account Configuration

Example of a failed CIS control identifying that the built-in Administrator account has not been renamed. Wazuh explains the associated security risk and provides remediation guidance.

![Administrator Account Failed](../images/ch09/25-administrator-account-failed.png)



## Figure 9.4 – Successful Security Control

Example of a successfully configured CIS security control showing that local accounts with blank passwords are restricted from remote logon. Wazuh verifies the configuration and maps it to multiple compliance frameworks.

![Passed Security Control](../images/ch09/26-blank-password-policy-passed.png)
