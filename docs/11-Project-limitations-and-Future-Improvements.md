# Chapter 11: Project limitations and Future Improvements

Building this project provided practical experience in deploying a SIEM, monitoring Windows and Linux endpoints, collecting behavioural telemetry and investigating security events within a simulated SME environment. Throughout the project, I encountered several technical challenges that influenced the final implementation. Rather than viewing these as setbacks they became valuable learning experiences and helped me better understand the practical considerations involved when designing and maintaining a security monitoring platform.

# What Went Well

The primary objective of this project was to improve endpoint visibility by collecting and analysing security telemetry from multiple sources. This objective was successfully achieved by implementing:
- Windows and Ubuntu endpoint monitoring
- File Integrity Monitoring (FIM)
- PowerShell Script Block Logging
- Behavioural detection using Windows Event Logs
- Security Configuration Assessment (SCA)
- Incident investigation through alert correlation

By the end of the project, Wazuh was successfully collecting and presenting security telemetry from multiple endpoints, allowing events to be investigated through a single centralised platform. More importantly the project demonstrated that meaningful investigations require multiple sources of evidence rather than relying on individual alerts.


# Challenges Encountered

Like any real world project, several technical challenges influenced the implementation.

## Limited Hardware Resources

The laboratory was built using virtual machines running on an Apple Silicon (M1) MacBook Pro. Although the system performed well overall, available CPU, memory and storage resources were naturally more limited than those found in enterprise environments. As additional Wazuh modules were enabled, resource usage increased significantly, requiring careful optimisation to maintain a stable lab. Working within these constraints also highlighted an important aspect of cybersecurity engineering. 

## Vulnerability Detection

One feature that was intentionally left out of the final implementation was Wazuh's Vulnerability Detection module. After testing the feature, it became clear that enabling continuous vulnerability scanning required considerably more storage and processing resources than were available within the virtual laboratory. Rather than compromising the stability of the environment, I decided to disable this feature and focus on the core objectives of behavioural monitoring, endpoint visibility and alert investigation. Although Vulnerability Detection would have added another valuable source of telemetry the project still achieved its primary objectives without it.

## Sysmon Compatibility

Another challenge involved Microsoft Sysmon. Sysmon is widely used within Security Operations Centres because it provides extremely detailed Windows telemetry. However due to the Windows 11 ARM virtual machine running under UTM on Apple Silicon hardware, Sysmon was not fully supported within this environment.

To overcome this limitation, I used PowerShell Script Block Logging together with native Windows Event Logs. This still provided detailed behavioural telemetry and demonstrated that valuable security monitoring can be achieved without relying exclusively on Sysmon.

# Lessons Learned
One of the biggest lessons from this project is that effective security monitoring is not achieved by deploying a single security tool. Each monitoring capability contributes a different piece of the overall picture.

- File Integrity Monitoring identifies changes to important files.
- PowerShell Script Block Logging records administrative activity.
- Behavioural detection highlights suspicious system behaviour.
- Security Configuration Assessment evaluates the security posture of the endpoint.

When these different sources of telemetry are correlated, they provide significantly better visibility than any individual monitoring capability on its own. This project also reinforced the importance of understanding not only how security tools work but why they are configured in particular ways and how they contribute to the overall incident investigation process.

# Future Improvements

Although the laboratory successfully achieved its objectives, there are several areas that could be expanded in future versions. Such as following,

- Re-enabling Vulnerability Detection on hardware with greater storage capacity.
- Deploying Windows x64 virtual machines to enable full Sysmon support.
- Mapping detections to the MITRE ATT&CK framework.
- Implementing Sigma detection rules.
- Expanding the environment with an Active Directory domain.
- Adding additional Windows and Linux endpoints.
- Integrating AI assisted alert prioritisation to help security analysts focus on the highest-risk events.

These improvements would increase both the amount of available telemetry and the realism of the laboratory while providing additional opportunities for behavioural analysis and threat hunting.

# Final Reflection

This project demonstrates that improving cyberattack visibility is not achieved through a single monitoring capability. Instead, it requires multiple sources of telemetry that work together to provide context during security investigations. Despite the practical limitations of the laboratory environment, the completed implementation successfully demonstrated endpoint monitoring, behavioural analysis, security configuration assessment and incident investigation using Wazuh.

Most importantly, the project strengthened my understanding of how modern Security Operations Centres collect, analyse and correlate security telemetry to investigate suspicious activity. The experience gained throughout this project has provided a strong practical foundation for further work in security monitoring, behavioural analytics and cyberattack visibility within SME environments.
