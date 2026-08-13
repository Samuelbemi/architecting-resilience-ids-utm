
4.0	Practical Implementation and Experimental Environment: This section presents the practical implementation of the defence-in-depth security architecture developed for this research. It describes the experimental environment used to evaluate the effectiveness of Windows 11(case study) endpoint security, Snort Intrusion Detection System (IDS), and pfSense Unified Threat Management (UTM) within a simulated enterprise network. The section outlines the research environment, network topology, endpoint configuration, and the deployment of each security component, providing the technical foundation for the practical evaluation presented in the subsequent sections.
4.1 Research Environment: The research environment was designed to simulate a Windows 11 enterprise network using a virtualised infrastructure. A laboratory environment was established to evaluate the effectiveness of a defence-in-depth security architecture by integrating Windows 11 endpoint security, Snort Intrusion Detection System (IDS), and pfSense Unified Threat Management (UTM). This controlled environment enabled the deployment, configuration, monitoring, and evaluation of the different security layers under realistic enterprise networking conditions.
The virtualised environment was implemented using Oracle VirtualBox, with each security component deployed as a dedicated virtual machine. This approach provided an isolated and flexible platform for configuring the enterprise network, monitoring network traffic, and evaluating the interaction between endpoint, network, and perimeter security controls.
4.1a Network Architecture
The experimental environment comprised the following components:
•	Oracle VirtualBox – Virtualisation platform used to host the enterprise laboratory environment.
•	Windows 11 Professional – Enterprise endpoint operating system configured with Microsoft Defender security features and Wireshark installed for network traffic capture and analysis.
<img width="408" height="255" alt="image" src="https://github.com/user-attachments/assets/8d7f6ac3-525d-434d-997d-0f58e7da6f83" /> <img width="270" height="35" alt="image" src="https://github.com/user-attachments/assets/4d44f071-516b-4683-830e-91b58c8cd8dd" />
•	pfSense – Deployed as the Unified Threat Management (UTM) platform, providing firewall protection, DHCP services, network traffic filtering, and perimeter security.
•	Snort – Deployed as the Intrusion Detection System (IDS) for monitoring network traffic, detecting suspicious activity, and generating security alerts.
•	Ubuntu Desktop: Operating system hosting the Snort Intrusion Detection System (IDS).
<img width="437" height="284" alt="image" src="https://github.com/user-attachments/assets/d75b5baf-bea4-407b-a298-fc27805735a9" /> <img width="255" height="36" alt="image" src="https://github.com/user-attachments/assets/3399912c-3318-4d36-a736-8eab3e1365d7" />
4.2 Network Topology: The experimental network topology was designed to simulate a Windows 11 enterprise environment implementing a defence-in-depth security architecture. The topology consists of three primary security components deployed as separate virtual machines within Oracle VirtualBox: a Windows 11 Professional endpoint, a Snort Intrusion Detection System (IDS), and a pfSense Unified Threat Management (UTM) platform.
The Windows 11 Professional virtual machine represents a typical enterprise endpoint and serves as the primary system used throughout the practical evaluation. To facilitate network analysis, Wireshark was installed on the Windows 11 endpoint to capture and analyse network traffic generated during the experiments. The captured packets were used to validate network communications, observe traffic behaviour, and support the evaluation of security events detected by Snort IDS and controlled by pfSense UTM.
The pfSense virtual machine functions as the network gateway and perimeter security device, providing firewall protection, Dynamic Host Configuration Protocol (DHCP) services, and traffic filtering between the enterprise network and external networks. Snort was deployed on an Ubuntu virtual machine to monitor network traffic, detect suspicious activity, and generate security alerts.
The network topology provides the foundation for evaluating how Windows 11 endpoint security, network intrusion detection, and perimeter security operate together as complementary layers within a defence-in-depth security architecture.
<img width="490" height="691" alt="image" src="https://github.com/user-attachments/assets/8b885c37-836f-4ca1-9be2-ceeb93c29a41" /> <img width="291" height="37" alt="image" src="https://github.com/user-attachments/assets/bb6a2dfe-dbfe-422c-98be-eba29713ac17" />

Figure 1.1 illustrates the experimental network topology implemented for this research. All communications between the Windows 11 endpoint and external networks are routed through the pfSense UTM, while Snort monitors network traffic to detect suspicious activities. Wireshark, installed on the Windows 11 endpoint, was used solely for packet capture and traffic analysis during the practical evaluation. Together, these components provide the technical foundation for assessing the effectiveness of a defence-in-depth security architecture in securing Windows 11 enterprise environments.
4.3 Windows 11 Endpoint Configuration: The Windows 11 Professional virtual machine was configured to represent a typical enterprise endpoint within the experimental network. The endpoint served as the primary system for evaluating the effectiveness of Windows 11 built-in security controls as the first layer of defence within the proposed defence-in-depth security architecture.
The Windows 11 endpoint was configured with the following security features and components:
•	Microsoft Defender Antivirus – Enabled to provide real-time protection against malware and other malicious software.
•	Windows Defender Firewall – Configured to control inbound and outbound network traffic based on predefined security rules.
•	Automatic Security Updates – Enabled to ensure that the operating system received the latest security patches and updates.
•	User Account Control (UAC) – Enabled to help prevent unauthorised changes to the operating system.
•	BitLocker Drive Encryption – Available as a built-in Windows 11 security feature for protecting data at rest (where applicable).
•	Wireshark – Installed to capture and analyse network traffic generated during the practical evaluation. Packet captures were used to observe network communications and support the analysis of security events detected by the IDS and controlled by the UTM.
The Windows 11 endpoint was configured to obtain its IP address automatically from the DHCP service provided by the pfSense UTM. This configuration enabled seamless communication within the simulated enterprise network while ensuring that all inbound and outbound network traffic passed through the pfSense gateway.
The configured endpoint served as the primary target system throughout the practical evaluation. It was used to generate network traffic, simulate normal user activity, and observe how Windows 11 endpoint security, Snort IDS, and pfSense UTM interacted as complementary security layers within a defence-in-depth architecture. 
4.4 Snort IDS Deployment 
4.4.1 Overview of Snort Deployment: Snort was deployed as the Network-Based Intrusion Detection System (NIDS) within the experimental environment to provide continuous monitoring of network traffic traversing the enterprise network. Operating as an additional security layer within the proposed defence-in-depth architecture, Snort was configured to inspect network packets, identify suspicious activities, and generate security alerts based on predefined detection rules. This deployment enabled the evaluation of Snort's capability to complement Windows 11 endpoint security by providing enhanced network visibility and intrusion detection. 
4.4.2 Installation: The Snort IDS was deployed on an Ubuntu virtual machine within the Oracle VirtualBox environment. The installation included the Ubuntu operating system, Snort software, and the supporting software packages required for packet capture, rule processing, and traffic analysis. Once installed, Snort was configured to operate as a Network-Based Intrusion Detection System capable of monitoring network traffic within the simulated enterprise environment.
The installation environment consisted of:
•	Operating System: Ubuntu Desktop 26.04
•	Intrusion Detection System: Snort
•	Deployment Type: Network-Based Intrusion Detection System (NIDS)
•	Installation Method: Source/Binary installation (specify the method used)
•	Supporting Dependencies: Libpcap, DAQ (where applicable), PCRE, and other required software libraries. 
4.4.3 Network Configuration: Following installation, Snort was integrated into the enterprise network and configured to monitor communications between the Windows 11 endpoint and other devices within the laboratory environment. The monitoring interface was configured to capture and inspect network packets traversing the enterprise network, enabling the detection of suspicious activities during the practical evaluation.
The network configuration included:
•	Static IP address assignment for the Snort virtual machine.
•	Configuration of the monitoring network interface.
•	Definition of the protected enterprise network (HOME_NET).
•	Configuration of the external network (EXTERNAL_NET).
•	Network connectivity with the Windows 11 endpoint through the enterprise LAN.
•	Verification of packet capture and network communication. 
4.4.4 Snort Rule Configuration: Following the network configuration, Snort was configured with an appropriate rule set to enable the detection of suspicious network activities within the experimental environment. Detection rules were configured to inspect network traffic, identify predefined attack signatures, and generate alerts whenever suspicious or potentially malicious activity was observed.
The rule configuration included:
•	Configuration of the HOME_NET and EXTERNAL_NET variables.
•	Enabling of the required Snort rule categories.
•	Integration of the Community Rules.
•	Configuration of local detection rules for laboratory testing (where applicable).
•	Configuration of alert logging and output formats.
•	Validation of the rule set to ensure successful loading before commencing the practical evaluation.
The configured rule set enabled Snort to detect and report security events generated during the experimental attack scenarios, providing the network visibility required to evaluate its contribution within the proposed defence-in-depth security architecture. 
4.4.5 Deployment Validation: Following installation and configuration, Snort was successfully validated to ensure that it was operating correctly within the experimental environment. Validation activities included verifying successful service startup, confirming the loading of detection rules, testing packet capture on the monitoring interface, and generating sample network traffic to confirm that security alerts were produced as expected.
The successful validation confirmed that Snort was fully operational and ready for use during the practical evaluation presented in the subsequent sections of this research. 
4.5 pfSense UTM Deployment
4.5.1 Overview of pfSense Deployment:
•	pfSense was deployed as the Unified Threat Management (UTM) platform. 
•	It acts as the network gateway between the enterprise LAN and external networks. 
•	It provides perimeter security controls including firewall protection, DHCP services, traffic filtering, and network monitoring. 
•	It complements Windows 11 endpoint security and Snort IDS by providing network-level protection. 
4.5.2 Installation and Initial Configuration:
•	pfSense version 
•	Deployment method (Virtual Machine in Oracle VirtualBox) 
•	Virtual hardware configuration (only if required) 
•	Network adapter configuration 
•	Installation process overview 
Practical scenario:
•	Operating System: pfSense Firewall 
•	Deployment Platform: Oracle VirtualBox 
•	Installation Type: Virtual Machine deployment 
•	Network Interfaces: 
o	WAN Interface 
o	LAN Interface 
<img width="545" height="360" alt="image" src="https://github.com/user-attachments/assets/ee2026ee-5ed3-4763-9ff1-3a8470878d1b" /> <img width="192" height="28" alt="image" src="https://github.com/user-attachments/assets/477df430-205d-45ac-8b34-a0b516b3fd19" />
4.5.3 Network Interface Configuration
This is an important section because pfSense is the gateway for this network architecture. 
WAN Interface
•	Connection to external network/Internet 
•	IP assignment method (DHCP/NAT/static depending on network requirements) 
LAN Interface
•	Internal enterprise network 
•	Gateway IP address 
•	Communication with Windows 11 endpoint and Snort IDS 
Interface	Purpose	Configuration
WAN	External network connection	DHCP/NAT
LAN	Internal enterprise network	Static IP 
4.5.4 DHCP Server Configuration:
pfSense is configured as DHCP server, include:
•	DHCP enabled on LAN interface 
•	IP address range 
•	Automatic assignment of IP addresses 
•	Gateway and DNS configuration 
The DHCP service enabled centralised management of IP address allocation within the simulated enterprise network, ensuring that connected devices received valid network configurations through the pfSense gateway.
4.5.5 Firewall and Traffic Filtering Configuration
•	Firewall rules 
•	Allowed traffic 
•	Restricted traffic 
•	Inbound and outbound traffic control 
•	Network security policies 


Example:
Firewall rules were configured to regulate communication between the internal network and external networks, allowing legitimate traffic while providing the capability to restrict unauthorised connections.
4.5.6 Network Security Monitoring
•	pfSense logs 
•	Firewall events 
•	Connection monitoring 
•	Traffic visibility 
The monitoring capability of pfSense provided visibility into network activities and supported the identification of unusual or unauthorised communication patterns during the evaluation.
4.5.7 pfSense Deployment Validation
•	pfSense dashboard screenshot 
•	WAN/LAN status 
•	DHCP leases 
•	Firewall rules 
•	Successful connectivity test 
Validation activities:
•	Windows 11 obtained IP address from pfSense DHCP. 
•	Internet/network connectivity confirmed. 
•	Firewall rules operated as expected. 
•	Network traffic passed through the pfSense gateway. 
4.6 Attack Scenarios: To evaluate the effectiveness of the proposed defence-in-depth security architecture, a series of controlled attack scenarios were conducted within the experimental environment. The scenarios were designed to simulate common cyber threats encountered in Windows 11 enterprise environments and to assess the ability of Windows 11 endpoint security, Snort Intrusion Detection System (IDS), and pfSense Unified Threat Management (UTM) to prevent, detect, monitor, and respond to these threats.
Each attack scenario focused on a specific aspect of enterprise security, including network reconnaissance, identification of open ports and exposed services, Windows Defender Firewall evasion, intrusion detection, perimeter security, and denial-of-service (DoS) attacks. Collectively, these scenarios provided a practical assessment of how multiple security layers operate together within a defence-in-depth architecture to improve the overall security posture of Windows 11 enterprise environments.
The attack scenarios evaluated in this research are summarised in Table 4.1.
Table 4.1: Summary of Attack Scenarios
Scenario	Attack Scenario	Objective	Security Layer Evaluated
Scenario 1	Baseline ICMP Connectivity and Network Visibility 
	Establish baseline network communication and validate packet capture.	Snort IDS, pfSense UTM
Scenario 2	TCP Port and Service Detection	Identify active hosts, open ports, and exposed services.	Windows 11, Snort IDS
Scenario 3	Network Scanning and Reconnaissance	Assess the Windows 11 attack surface.	Windows 11 Endpoint
Scenario 4	Windows Firewall Protection and Controlled Bypass Testing	Evaluate the effectiveness of Windows Defender Firewall and complementary security controls.	Windows Defender, Snort IDS, pfSense UTM
Scenario 5	Snort IDS Detection and Alert Generation	Assess Snort's ability to detect suspicious network activity.	Snort IDS
Scenario 6	pfSense UTM Traffic Filtering and Blocking
	Evaluate pfSense firewall and traffic filtering capabilities.	pfSense UTM
Scenario 7	IDS and UTM Defence Validation	Evaluate detection and response to a controlled DoS attack.	Windows 11, Snort IDS, pfSense UTM
Scenario 8	Defence-in-Depth Security Effectiveness Evaluation
	Assess the combined effectiveness of all security layers.	Entire Defence-in-Depth Architecture
4.6.1 Attack Scenario 1
Windows 11 IP Address: 192.168.1.111
 Snort IP Address: 192.168.1.110
pfSense IP Address: 192.168.1.1
Scenario 1: Baseline ICMP Connectivity and Network Visibility 
Objective
To establish baseline network connectivity between the Snort IDS host and the Windows 11 enterprise endpoint and to evaluate the effect of the default Windows Defender Firewall configuration on ICMP communication.
Security Layer Evaluated: Snort IDS, pfSense UTM
Procedure
The first practical evaluation involved sending ICMP Echo Request (ping) packets from the Snort IDS host to the Windows 11 Professional virtual machine.
From the Snort host, the following command was executed:
ping 192.168.1.111 (windows 11 endpoint)
<img width="532" height="149" alt="image" src="https://github.com/user-attachments/assets/75c9efca-03b3-47f4-947f-83ecff6e886c" /> <img width="312" height="32" alt="image" src="https://github.com/user-attachments/assets/8f4600b5-94b7-494b-bab9-1aebeea1cb5e" />
Observation
The ICMP requests were unsuccessful because Windows Defender Firewall blocks inbound ICMP Echo Requests by default. As a result, the Windows 11 endpoint did not respond to the ping requests, preventing communication between the Snort host and the endpoint.
This behaviour demonstrates that Windows Defender Firewall provides an effective first layer of defence by restricting unsolicited inbound network traffic unless explicitly permitted.
Resolution
To establish communication within the laboratory environment, an inbound firewall rule was created on the Windows 11 endpoint to allow ICMP traffic originating from trusted devices on the enterprise network.
The firewall rule was configured to permit communication from:
•	192.168.1.1 – pfSense UTM (Default Gateway)
•	192.168.1.110 – Snort IDS Host
<img width="510" height="248" alt="image" src="https://github.com/user-attachments/assets/dbda8dc8-3654-41e1-9de2-6135a2543770" /> <img width="226" height="30" alt="image" src="https://github.com/user-attachments/assets/ff2b3644-d60d-43ab-8553-d08241dfda7a" />
After applying the firewall rule, the ICMP connectivity test was repeated from the Snort host.
ping 192.168.1.111
<img width="620" height="182" alt="image" src="https://github.com/user-attachments/assets/fb2ff9d8-5d8f-47aa-acce-40d489d387de" /> <img width="494" height="35" alt="image" src="https://github.com/user-attachments/assets/6e2bff25-999d-4c6e-a9b8-d04639b42a64" />
The Windows 11 endpoint responded successfully to the ICMP Echo Requests, confirming that communication had been established between the Snort IDS host and the Windows 11 endpoint.
The same steps were carried out from pfSence UTM to windows 11 endpoint and the ping was successful.
Result
The successful ICMP communication confirmed that the Windows Defender Firewall had been correctly configured to permit trusted network traffic while maintaining control over inbound connections. Establishing this baseline connectivity was necessary before conducting the subsequent practical evaluations, including network reconnaissance, intrusion detection, firewall evaluation, and denial-of-service testing.










