# Laboratory Environment

This directory documents the practical laboratory environment used to conduct the research.

The laboratory is implemented as a controlled virtualised cybersecurity environment and consists of the following principal components:

* **Kali Linux** - controlled test/attacker machine
* **Windows 11 Pro** - case-study enterprise endpoint
* **Ubuntu Linux with Snort** - Intrusion Detection System (IDS)
* **pfSense** - Unified Threat Management (UTM) platform
* **VirtualBox** - virtualisation platform

The laboratory documentation will record the configuration, networking, deployment, and operational role of each component.

## Laboratory Components

### Kali Linux

Kali Linux provides the controlled test and attacker environment used to generate authorised security-testing traffic against the Windows case-study environment.

### Windows 11 Pro

Windows 11 Pro represents the Windows enterprise endpoint used as the case-study system for evaluating the effectiveness of layered security controls.

### Snort IDS

Snort is deployed as the network-based Intrusion Detection System. It is used to monitor relevant network traffic and generate security alerts based on configured detection rules.

### pfSense UTM

pfSense provides the Unified Threat Management layer, including firewall-based traffic control, filtering, logging, and other gateway security functions relevant to the experimental evaluation.

### VirtualBox

VirtualBox provides the virtualised laboratory platform on which the experimental systems are deployed and interconnected.

Detailed configuration and experimental evidence will be documented in the relevant laboratory and experiment directories.
