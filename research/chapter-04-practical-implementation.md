
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
<img width="437" height="284" alt="image" src="https://github.com/user-attachments/assets/d75b5baf-bea4-407b-a298-fc27805735a9" />  <img width="255" height="36" alt="image" src="https://github.com/user-attachments/assets/b0c2278a-db11-4f37-a122-9c5425959a67" />


4.2 Network Topology: The experimental network topology was designed to simulate a Windows 11 enterprise environment implementing a defence-in-depth security architecture. The topology consists of three primary security components deployed as separate virtual machines within Oracle VirtualBox: a Windows 11 Professional endpoint, a Snort Intrusion Detection System (IDS), and a pfSense Unified Threat Management (UTM) platform.
The Windows 11 Professional virtual machine represents a typical enterprise endpoint and serves as the primary system used throughout the practical evaluation. To facilitate network analysis, Wireshark was installed on the Windows 11 endpoint to capture and analyse network traffic generated during the experiments. The captured packets were used to validate network communications, observe traffic behaviour, and support the evaluation of security events detected by Snort IDS and controlled by pfSense UTM.
The pfSense virtual machine functions as the network gateway and perimeter security device, providing firewall protection, Dynamic Host Configuration Protocol (DHCP) services, and traffic filtering between the enterprise network and external networks. Snort was deployed on an Ubuntu virtual machine to monitor network traffic, detect suspicious activity, and generate security alerts.
The network topology provides the foundation for evaluating how Windows 11 endpoint security, network intrusion detection, and perimeter security operate together as complementary layers within a defence-in-depth security architecture.

<img width="490" height="691" alt="image" src="https://github.com/user-attachments/assets/8b885c37-836f-4ca1-9be2-ceeb93c29a41" /> <img width="291" height="37" alt="image" src="https://github.com/user-attachments/assets/bb6a2dfe-dbfe-422c-98be-eba29713ac17" />

Figure 4.2.1 illustrates the experimental network topology implemented for this research. All communications between the Windows 11 endpoint and external networks are routed through the pfSense UTM, while Snort monitors network traffic to detect suspicious activities. Wireshark, installed on the Windows 11 endpoint, was used solely for packet capture and traffic analysis during the practical evaluation. Together, these components provide the technical foundation for assessing the effectiveness of a defence-in-depth security architecture in securing Windows 11 enterprise environments.

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

<img width="545" height="360" alt="image" src="https://github.com/user-attachments/assets/ee2026ee-5ed3-4763-9ff1-3a8470878d1b" /> <img width="255" height="28" alt="image" src="https://github.com/user-attachments/assets/8c8a75b6-5b20-4334-a2f8-7bb60f0a65a6" />


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

6 Attack Scenarios: To evaluate the effectiveness of the proposed defence-in-depth security architecture, a series of controlled attack scenarios were conducted within the experimental environment. The scenarios were designed to simulate common cyber threats encountered in Windows 11 enterprise environments and to assess the ability of Windows 11 endpoint security, Snort Intrusion Detection System (IDS), and pfSense Unified Threat Management (UTM) to prevent, detect, monitor, and respond to these threats.
Each attack scenario focused on a specific aspect of enterprise security, including network reconnaissance, identification of open ports and exposed services, Windows Defender Firewall evasion, intrusion detection, perimeter security, and denial-of-service (DoS) attacks. Collectively, these scenarios provided a practical assessment of how multiple security layers operate together within a defence-in-depth architecture to improve the overall security posture of Windows 11 enterprise environments.
The attack scenarios evaluated in this research are summarised in Table 4.1.
Table 4.1: Summary of Attack Scenarios
Scenario	Attack Scenario	Objective	Security Layer Evaluated

Scenario 1	Baseline ICMP Connectivity and Network Visibility 
	Establish baseline network communication and validate packet capture.	Snort IDS, pfSense UTM
	
Scenario 2	Network Scanning and Reconnaissance	Assess the Windows 11 attack surface.	Windows 11 Endpoint

Scenario 3	 TCP Port and Service Detection	Identify active hosts, open ports, and exposed services. Windows 11, Snort IDS

Scenario 4	Windows Firewall Protection and Controlled Bypass Testing	Evaluate the effectiveness of Windows Defender Firewall and complementary security controls.	Windows Defender, Snort IDS, pfSense UTM

Scenario 5	Snort IDS Detection and Alert Generation	Assess Snort's ability to detect suspicious network activity.	Snort IDS

Scenario 6	pfSense UTM Traffic Filtering and Blocking
	Evaluate pfSense firewall and traffic filtering capabilities.	pfSense UTM
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

Scenario 2: Network Reconnaissance (Nmap Scan)
Objective
To identify active hosts, open ports, and exposed services on the Windows 11 endpoint using Nmap and to evaluate the ability of Snort IDS to detect reconnaissance activities within the enterprise network.
Security Layer Evaluated: Windows 11, Snort IDS
Practical Procedure

Step 1: Discover Active Hosts using sweep ping command
Use Nmap to identify active hosts on the enterprise network.
On Snort VM: sudo nmap -sn 192.168.1.0/24
<img width="507" height="271" alt="image" src="https://github.com/user-attachments/assets/5ea98091-cf2d-4741-ae94-7c9f65324006" /> <img width="328" height="42" alt="image" src="https://github.com/user-attachments/assets/d98b8100-4f2c-4a8a-a0a9-3d554ebf06fb" />

Result
•	Windows 11 endpoint detected. 
•	pfSense gateway detected. 
•	Snort host detected. 

Step 2: Scan the Windows 11 Endpoint for Open Ports and Services
Run a TCP SYN scan against the Windows 11 endpoint.
sudo nmap -sS 192.168.1.111
<img width="470" height="248" alt="image" src="https://github.com/user-attachments/assets/3fcb6d63-7446-462e-bad4-bf9b8e9ca159" /> <img width="451" height="61" alt="image" src="https://github.com/user-attachments/assets/bd3a8a9d-074e-40c9-b99e-079dda7d0a97" />


Result
The Nmap scan identified the following open ports and associated services on the Windows 11 endpoint:
Port	Service	Description
135/TCP	MSRPC	Microsoft Remote Procedure Call (RPC) service used for communication between Windows applications and network services.
139/TCP	NetBIOS-SSN	NetBIOS Session Service used for legacy file and printer sharing over TCP/IP.
445/TCP	Microsoft-DS	Server Message Block (SMB) service used for file sharing, printer sharing, and Active Directory communication.

Analysis
The scan confirmed that the Windows 11 endpoint was exposing several Microsoft networking services that are commonly found in enterprise environments. These services support essential organisational functions such as remote procedure calls, file sharing, and network resource access. However, they also increase the system's attack surface if not properly secured.
Port 135 (MSRPC) is frequently targeted during reconnaissance because it provides information about Windows services and can be used as an entry point for exploiting vulnerabilities in Microsoft RPC services.
Port 139 (NetBIOS Session Service) supports legacy network communication and file sharing. Although still used in some environments, it is often considered a security risk if exposed unnecessarily because it may disclose system information and facilitate unauthorised access.
Port 445 (Microsoft-DS/SMB) is one of the most critical services within Windows enterprise networks. While it is essential for file sharing, printer sharing, and domain communication, it has historically been exploited by malware and ransomware families, including the WannaCry ransomware attack, making it a common target during network reconnaissance and exploitation attempts.
The identification of these open ports demonstrates that enterprise endpoints may expose legitimate services required for business operations. Consequently, organisations should not rely solely on Windows Defender Firewall for protection. Additional security controls, such as Snort IDS for intrusion detection and pfSense UTM for network traffic filtering and perimeter protection, provide complementary layers of defence that improve visibility into reconnaissance activities and strengthen the overall security posture of the enterprise environment.
Step 4: Monitor Snort IDS
Monitor Snort on the Ubuntu IDS host.
This command was run on the Snort IDS:
sudo snort -q -c /usr/local/etc/snort/snort.lua -i <interface> -A alert_fast
Another terminal was open and the below command was run:
Sudo nmap -sS 192.168.1.111 
Full scan result of snort IDS below:
-- [0] enp0s8 -------------------------------------------------- Packet Statistics -------------------------------------------------- daq received: 4229 analyzed: 4222 allow: 4222 rx_bytes: 256365 -------------------------------------------------- codec total: 4222 (100.000%) discards: 119 ( 2.819%) arp: 18 ( 0.426%) eth: 4222 (100.000%) icmp6: 5 ( 0.118%) ipv4: 4144 ( 98.153%) ipv6: 60 ( 1.421%) tcp: 4080 ( 96.637%) udp: 119 ( 2.819%) -------------------------------------------------- Module Statistics -------------------------------------------------- ac_full searches: 115 matches: 2219 bytes: 9058 -------------------------------------------------- appid packets: 4085 processed_packets: 4085 total_sessions: 4061 service_cache_adds: 59 bytes_in_use: 9912 items_in_use: 59 -------------------------------------------------- arp_spoof packets: 18 -------------------------------------------------- back_orifice packets: 57 -------------------------------------------------- binder raw_packets: 18 new_flows: 4061 service_changes: 1 inspects: 4079 -------------------------------------------------- detection analyzed: 4222 -------------------------------------------------- http_inspect flows: 1 scans: 2 reassembles: 2 inspections: 2 responses: 1 max_concurrent_sessions: 1 total_bytes: 179 -------------------------------------------------- port_scan packets: 4204 trackers: 22 -------------------------------------------------- stream flows: 4061 total_prunes: 2022 idle_prunes_proto_timeout: 2022 tcp_timeout_prunes: 1999 udp_timeout_prunes: 22 icmp_timeout_prunes: 1 -------------------------------------------------- stream_icmp sessions: 5 max: 5 created: 5 released: 5 -------------------------------------------------- stream_tcp sessions: 3999 max: 3999 created: 3999 released: 3999 instantiated: 3999 setups: 3999 restarts: 1 syn_trackers: 3998 syn_ack_trackers: 1 segs_queued: 1 segs_released: 1 segs_used: 1 rebuilt_packets: 2 rebuilt_bytes: 185 syns: 3998 syn_acks: 11 rsts: 10 rsts_ok_rfc5961: 10 fins: 2 max_segs: 1 max_bytes: 185 flush_on_asymmetric_flow: 1 asymmetric_flows: 1 -------------------------------------------------- stream_udp sessions: 57 max: 57 created: 57 released: 57 total_bytes: 8052 -------------------------------------------------- tcp bad_tcp4_checksum: 6 bad_tcp6_checksum: 51 -------------------------------------------------- udp bad_udp4_checksum: 58 bad_udp6_checksum: 4 -------------------------------------------------- wizard tcp_scans: 1 tcp_hits: 1 udp_scans: 57 udp_misses: 57 -------------------------------------------------- Appid Statistics -------------------------------------------------- detected apps and services Application: Services Clients Users Payloads Misc Referred unknown: 57 0 0 0 0 0 -------------------------------------------------- Summary Statistics -------------------------------------------------- process signals: 1 -------------------------------------------------- timing runtime: 00:07:03 seconds: 423.548355 pkts/sec: 10 o")~ Snort exiting student@student-VirtualBox:~$ 

Observation
During the Nmap reconnaissance activity, Snort IDS was executed on the Ubuntu host to monitor network traffic generated against the Windows 11 endpoint. Snort successfully captured and analysed 4,222 packets during the test period.
The Snort runtime statistics indicated significant TCP scanning activity, with 4,204 packets processed by the port scan detection module. Furthermore, the scan detection component identified one TCP scan event and one TCP scan hit, confirming that Snort successfully observed reconnaissance activity targeting the Windows 11 endpoint.
The TCP stream analysis also recorded 3,998 SYN packets, demonstrating the behaviour associated with a TCP SYN reconnaissance scan. These findings demonstrate that while Windows 11 endpoint security controls may restrict access to exposed services, network-based intrusion detection provides additional visibility by identifying suspicious reconnaissance activities occurring within the enterprise network.
Summary of the Scan result:
port_scan
packets: 4204
tcp_scans: 1
tcp_hits: 1
Analysis
The Nmap reconnaissance exercise demonstrated that Windows 11 exposes legitimate enterprise services that may increase the attack surface if not properly secured. Although Windows Defender Firewall provides endpoint-level protection, Snort IDS added an additional security layer by detecting reconnaissance behaviour and providing network visibility that is not available from endpoint protection alone. This show Windows Defender Firewall protects the endpoint, but IDS provides visibility into attacker behaviour before exploitation occurs.

                                                                                                                                                                                                                                                                                                                                                                                                                                                                          Scenario 3: TCP Port and Service Detection
Objective
To enumerate the services exposed by the Windows 11 endpoint following network reconnaissance and to assess the potential attack surface presented by these services within an enterprise environment.
Security Layer Evaluated: Windows 11 Endpoint Security
Procedure
Following the successful Nmap reconnaissance scan conducted in Scenario 2, service enumeration was performed to obtain detailed information about the services running on the Windows 11 endpoint.
The following command was executed from the Snort host:
sudo nmap -sV 192.168.1.111
The -sV option instructs Nmap to perform service version detection by probing each open port to identify the associated service.
<img width="416" height="270" alt="image" src="https://github.com/user-attachments/assets/16ea5cf9-3a66-4c1b-88e6-bfac6d647da9" /> <img width="255" height="40" alt="image" src="https://github.com/user-attachments/assets/45fd4aa0-2e27-40fc-b8ad-b56396de38d2" />


Results
The scan identified the following services on the Windows 11 endpoint:
Port	Service	Purpose
135/TCP	MSRPC	Microsoft Remote Procedure Call used for communication between Windows services and applications.
139/TCP	NetBIOS Session Service	Supports legacy file and printer sharing over TCP/IP.
445/TCP	Microsoft-DS (SMB)	Provides file sharing, printer sharing, and network resource access within Windows enterprise environments.
Analysis
The results indicate that the Windows 11 endpoint exposes several Microsoft networking services commonly required for enterprise operations. Although these services are legitimate and necessary for administrative and business functions, they also increase the attack surface of the endpoint.
Services such as MSRPC and SMB are frequently targeted during reconnaissance and exploitation because they can reveal valuable information about the operating system and available network resources. Historically, vulnerabilities affecting SMB have been exploited by high-profile malware and ransomware campaigns, demonstrating the importance of securing these services through timely patching, strong access controls, and network segmentation.
This scenario demonstrates that endpoint security extends beyond enabling Windows Defender Firewall. Organisations should regularly identify and review exposed ports and services to minimise unnecessary exposure while ensuring that essential business services remain available. The findings reinforce the importance of integrating endpoint security with complementary security controls, such as Snort IDS for network intrusion detection and pfSense UTM for network and perimeter protection, as part of a defence-in-depth security architecture.
Remark
The service enumeration confirmed that the Windows 11 endpoint exposes legitimate enterprise services that support normal business operations but also contribute to the system's attack surface. Effective enterprise security therefore requires continuous monitoring, vulnerability management, and layered security controls to reduce the likelihood of these services being exploited by attackers.

Scenario 4: Windows Firewall Protection and Controlled Bypass Testing
Objective
To evaluate the effectiveness of Windows Defender Firewall in restricting unauthorised inbound network connections and to assess the behaviour of complementary security controls when a controlled connection attempt is made from an unauthorised source.
Present Network Setup:
•	Windows 11 = protected endpoint 
•	Kali Linux (192.168.1.113) = controlled test/attacker source 
•	Windows Firewall = endpoint protection 
•	192.168.1.1 and 192.168.1.110 = explicitly permitted sources 
•	192.168.1.113 = not in the permitted source list
Security Layers Evaluated
•	Windows Defender Firewall – Endpoint traffic control 
•	Snort IDS – Network traffic monitoring and detection 
•	pfSense UTM – Network and perimeter traffic control 

Practical Procedure
Step 1 Verify the Windows Firewall baseline
On the Windows 11 machine (192.168.1.111):
1.	Press Windows + R. 
2.	Type: wf.ms

<img width="510" height="224" alt="image" src="https://github.com/user-attachments/assets/c01d3f2a-4c3b-42e4-be80-5853afc62c80" /> <img width="614" height="304" alt="image" src="https://github.com/user-attachments/assets/7633f7a3-ef3e-489c-b0e6-7cac8f4138ee" /> <img width="428" height="36" alt="image" src="https://github.com/user-attachments/assets/2780bbcd-ca3f-4687-be21-021b801a0abb" />

Step 2: Test the protected endpoint from kali
Now we test whether the Windows Firewall rule actually restricts the unauthorised source, Kali 192.168.1.113.
Run these commands on Kali Linux:
ping -c 4 192.168.1.111 and sudo nmap -Pn -sS -p 135,139,445 192.168.1.111

<img width="526" height="27" alt="image" src="https://github.com/user-attachments/assets/b6f65978-49e3-4027-b2e4-b69483f57007" />  <img width="517" height="173" alt="image" src="https://github.com/user-attachments/assets/fca26cfc-3b4f-45dc-9cc3-5a6ea7d2e3f9" />  <img width="526" height="27" alt="image" src="https://github.com/user-attachments/assets/b9ac82c9-b801-43e8-85b3-d1d71d4216ab" /> <img width="593" height="275" alt="image" src="https://github.com/user-attachments/assets/9ac1ceaf-b871-4692-b244-ce0bd1c9f451" />
 
Result and Observation:
The ICMP ping was unsuccessful - an indication that the inbound firewall rule is restricting the kali host from connectivity, why the TCP SYN scan results shows that tcp port was filtered. 

Kali machine (192.168.1.113) can reach the Windows host at 192.168.1.111, but the three tested TCP ports are reported as filtered:
Port	Service	Result
135	MSRPC	Filtered
139	NetBIOS-SSN	Filtered
445	Microsoft-DS/SMB	Filtered
The important observation is that the TCP port are filtered not open. This means that Windows Defender Firewall is actively blocking access to these port, preventing traffic from reaching it.
Breakdown of the TCP SYN Stealth Scan result:
Kali-to-Windows baseline test
•	Source: Kali Linux — 192.168.1.113 
•	Destination: Windows 11 — 192.168.1.111 
•	Test: TCP SYN scan 
•	Ports: 135, 139, 445 
•	Host status: Up 
•	TCP ports: Filtered 
•	Nmap version: 7.98 
•	MAC vendor: Oracle VirtualBox virtual NIC
Snort IDS - Network traffic monitoring and detection 
Step 3 - Check Snort during the same test
Now we need to know if Snort detect the connection attempts from Kali 192.168.1.113 to Windows 192.168.1.111
Run this command on snort host and leave snot running then repeat step 2:
sudo snort -i enp0s8 -c /usr/local/etc/snort/snort.lua -A alert_fast
Result of Snort displays:
pcap DAQ configured to passive.
Commencing packet processing
++ [0] enp0s8
This means Snort is running and listening on enp0s8 but does not produced any observation.
Step 3 Result:
Snort was operational and configured for passive packet capture on interface enp0s8. However, no corresponding Snort alert or observable event was generated during the controlled TCP scan from Kali Linux (192.168.1.113) to Windows 11 (192.168.1.111).
Step 4 Verify whether Snort can actually see the traffic:
On the Snort machine, we will leave Snort running and open another terminal.
Command to run:
sudo tcpdump -ni enp0s8 host 192.168.1.113 and host 192.168.1.111 

This is only a visibility test. It does not modify anything.
Then, from Kali, run the same scan again:
sudo nmap -Pn -sS -p 135,139,445 192.168.1.111

<img width="526" height="27" alt="image" src="https://github.com/user-attachments/assets/a8b4208c-b9a5-4d25-96ba-6158d8aa2626" />  <img width="597" height="238" alt="image" src="https://github.com/user-attachments/assets/9230dee2-a770-4a40-93d1-eb4c3599e874" />  

Fig 4.6.1j output is an indication that the post are closed.

Then run tcpdump on snort vm:
student@student-VirtualBox:~$ sudo tcpdump -ni enp0s8 host 192.168.1.113 and host 192.168.1.111
Tcpdump output:
tcpdump: verbose output suppressed, use -v[v]... for full protocol decode
listening on enp0s8, link-type EN10MB (Ethernet), snapshot length 262144 bytes
13:27:20.703296 ARP, Request who-has 192.168.1.111 tell 192.168.1.113, length 46
The displayed result means that Snort machine's enp0s8 interface can see traffic associated with Kali (192.168.1.113) attempting to resolve the MAC address of Windows (192.168.1.111).
In other words, the Snort machine is seeing at least the Layer-2 ARP activity associated with the Kali to Windows communication, but it has not yet demonstrated that the actual TCP SYN packets are visible.
We will leave the tcpdump running, then from kali we run this command:
sudo nmap -Pn -sS -p 135,139,445 192.168.1.111 (The tcp syn scan displays same result as in Fig 4.6.1j).
View the tcpdump output again:
Tcpdump out:
tcpdump: verbose output suppressed, use -v[v]... for full protocol decode
listening on enp0s8, link-type EN10MB (Ethernet), snapshot length 262144 bytes
13:27:20.703296 ARP, Request who-has 192.168.1.111 tell 192.168.1.113, length 46
13:34:52.913370 ARP, Request who-has 192.168.1.111 tell 192.168.1.113, length 46
13:37:58.399624 ARP, Request who-has 192.168.1.111 tell 192.168.1.113, length 46
13:40:34.861407 ARP, Request who-has 192.168.1.111 tell 192.168.1.113, length 46
From the output, tcpdump captured only ARP requests. This means that Snort sensor is seeing Layer-2 ARP requests associated with the Kali-to-Windows communication, but the TCP scan traffic itself is not visible on the Snort sensor's enp0s8 interface.
Step 5 Verify the physical/virtual network placement
Now we need to establish how the VMs are connected:
On the snort VM we run the following command:
ip addr: 

<img width="233" height="27" alt="image" src="https://github.com/user-attachments/assets/3506d61d-4464-4462-8068-53603ff1245b" /> <img width="408" height="139" alt="image" src="https://github.com/user-attachments/assets/3ac9d52d-2299-4ecb-8394-032c8779127a" />

Fig 4.6.1k shows the interface of snort is enp0s8
On Kali we run the command: 
ip addr:

<img width="233" height="27" alt="image" src="https://github.com/user-attachments/assets/c0ec7687-8c3a-420f-b0a1-30c45f1fd7ce" />  <img width="462" height="174" alt="image" src="https://github.com/user-attachments/assets/7e33cff5-fc38-4dbc-b66a-a18a3467d081" />

The both output shows that snort is directly connected to 192.168.1.0/24 subnet as kali.

Observation
Since Kali and Windows are communicating directly at Layer 2, the unicast TCP frames are normally delivered directly between their virtual NICs.
The Snort VM will not automatically see those unicast frames simply because it shares the same subnet.
That's likely why tcpdump saw the ARP broadcast but not the TCP SYN packets.
What we deduce from the observation is that the reason why snort sees layer 2 traffic only, and not seeing the TCP traffic between Kali and Windows 11 machine, is because of the placement of Snort IDS. This is to say that Snort VM is not positioned to passively observe the direct Kali-to-Windows unicast traffic on this virtual switched network.
Remark:
The experimental results demonstrate that incorporating an IDS into a defence-in-depth architecture can increase network security visibility by providing an additional monitoring layer. In the experimental environment, Snort was able to observe Layer-2 broadcast activity, including ARP requests associated with reconnaissance attempts. However, the experiment also demonstrated that IDS visibility is dependent on sensor placement and network architecture; Snort did not automatically observe direct unicast TCP traffic exchanged between hosts on the same virtual network.

Recommended Architecture will be: 

<img width="315" height="389" alt="image" src="https://github.com/user-attachments/assets/b2a1e826-d667-4877-8ca9-ed88dc488f58" />  <img width="257" height="27" alt="image" src="https://github.com/user-attachments/assets/8397893c-bbdb-4677-ab6b-034d4195b35d" />

Scenario 4 - pfSense UTM Effectiveness
pfSense UTM – Network and perimeter traffic control 
Establish pfSense baseline
Before proceeding we need to first establish that the Kali machine can reach the destination through the pfSense gateway. 
We are trying confirm that traffic from pfSense is routed default via 192.168.1.1 which means that pfSense is kali gateway.

On kali run: iproute

<img width="464" height="27" alt="image" src="https://github.com/user-attachments/assets/3b725c6b-8933-4ee9-8ce3-89f10583046c" />  <img width="445" height="138" alt="image" src="https://github.com/user-attachments/assets/3614b177-3343-4002-8aa1-6e60edcecd84" />

This experiment validates pfSense’s ability to enforce network-level policy on gateway-bound traffic. 
Practical
Current configuration:
pfSense: 192.168.1.1
Kali:    192.168.1.113
Windows: 192.168.1.111
Network: 192.168.1.0/24
Step 1 – Create the pfSense blocking rule
Now we will create a controlled firewall rule.
In pfSense:
Firewall → Rules
Select the interface where Kali's traffic enters pfSense — most likely LAN in your current configuration.
Add a rule with:
Action:       Block
Interface:    LAN
Address Family: IPv4
Protocol:     ICMP
Source:       Single host
Source IP:    192.168.1.113
Destination:  Any

<img width="499" height="186" alt="image" src="https://github.com/user-attachments/assets/555e8054-5d58-47a5-9a8f-0101c4857d97" />  <img width="359" height="27" alt="image" src="https://github.com/user-attachments/assets/089c3905-e2c7-4ace-b527-080e418aa418" />

Step 2 – Check kali egress traffic
We will ping google.com ip address
On Kali ru:
Ping -c 4 8.8.8.8

<img width="502" height="199" alt="image" src="https://github.com/user-attachments/assets/00ad0d4d-6d69-478a-9c00-d2ffe2730b07" />  <img width="272" height="27" alt="image" src="https://github.com/user-attachments/assets/58e0bd58-94a2-497b-b97a-8d60acd0f4a3" /> 

Figure 4.6.1p: The failed ping attempt to google.com confirms that pfSense successfully enforced the outbound traffic blocking rule for the Kali host.
Step 3 Reverse the Rule to allow egress traffic
In pfSense:
Firewall → Rules
Select the interface where Kali's traffic enters pfSense — most likely LAN in your current configuration.
Add a rule with:
Action:       Pass
Interface:    LAN
Address Family: IPv4
Protocol:     ICMP
Source:       Single host
Source IP:    192.168.1.113
Destination:  Any

<img width="517" height="211" alt="image" src="https://github.com/user-attachments/assets/5574939c-187b-432c-aaac-f794993bdb92" />  <img width="375" height="32" alt="image" src="https://github.com/user-attachments/assets/c1553c3d-67a3-4c44-a696-a5a54198e790" /> 

Step 4 – Check kali egress traffic
We will ping google.com ip address
On Kali run:
Ping -c 4 8.8.8.8

<img width="585" height="150" alt="image" src="https://github.com/user-attachments/assets/2c0b52f0-7b54-4459-963c-36c0cba2ca10" />  <img width="272" height="27" alt="image" src="https://github.com/user-attachments/assets/73c7d474-81ca-40cf-b086-14f18b1e2364" />

Figure 4.6.1r: The successful ping to google.com confirms that pfSense successfully enforced the outbound traffic allowing rule for the Kali host.
Remark
This experiment validates pfSense’s ability to enforce network-level policy on gateway-bound traffic. By Blocking and allowing outbound egress from Kali, we prove that pfSense effectively controls and restricts traffic attempting to traverse the gateway.
Scenario 5 - Snort IDS Detection and Alert Generation
Objective:
Assess Snort's ability to detect and generate alerts for suspicious network activity.
The key distinction is:
•	Scenario 2: Can Snort observe TCP port/service detection? 
•	Scenario 3: Can Snort observe reconnaissance/scanning activity? 
•	Scenario 5: Can Snort actively identify traffic as suspicious and generate an IDS alert?
So this time, we need an activity that matches a Snort detection rule, rather than simply producing traffic that Snort can see. The important question is whether Snort can actually see the traffic generated by Kali.
Snort IDS Detection and Alert Generation, we will work with:
•	Interface: enp0s8 
•	Snort configuration: /usr/local/etc/snort/snort.lua 
•	Alert mode: alert_fast 
•	Snort IP: 192.168.1.110 
•	Kali: 192.168.1.113 
•	Windows: 192.168.1.111

Step 1 - Verify snort current configuration
On Snort run this command:
Sudo snort -i enp0s8 -c /usr/local/etc/snort/snort.lua -A alert_fast

<img width="177" height="28" alt="image" src="https://github.com/user-attachments/assets/4ecffafb-164a-4e33-b896-4884181399b8" /> <img width="447" height="258" alt="image" src="https://github.com/user-attachments/assets/e88fa546-7545-4454-90bf-3935f1238174" />

Leave it running.
Then, from Kali, generate the controlled traffic:
ping -c 4 192.168.1.111 #observe snort for alert
From the observation snort did not produce any alert.
Next we will verify packet visibility.
Run tcpdump on Snort:
sudo tcpdump -ni enp0s8 host 192.168.1.113 and host 192.168.1.111
What are proving is snort saying I observed this traffic from Kali and it matches a suspicious-activity detection rule.
Therefore, our test should have two independent observations:
Windows defender Blocks Kali, and Snort Detects/alerts on Kali’s traffic
Tcpdump display result:
tcpdump: verbose output suppressed, use -v[v]... for full protocol decode
listening on enp0s8, link-type EN10MB (Ethernet), snapshot length 262144 bytes
ARP, Request who-has 192.168.1.111 tell 192.168.1.113
This output means tcpdump is running correctly and listening on enp0s8, this proves that the Snort VM is now seeing Layer 2 traffic associated with the Kali to Windows communication.
Leave tcpdump running and run this command:
ping -c 4 192.168.1.111  #and look at tcpdump, it should show display ICMP echo request
The tcpdump is not show ICMP echo request. This means that Snort VM is not receiving the direct Kali to Windows unicast traffic, the reason Snort is not generating an alert.
For our Scenario 5 experiment, the ideal situation is:
1.	ARP succeeds - proving Layer 2 connectivity. 
2.	ICMP request reaches Windows - proving the test traffic exists. 
3.	Windows Firewall blocks the ICMP/IP traffic - demonstrating endpoint enforcement. 
4.	Snort sees the traffic - demonstrating IDS visibility. 
5.	Snort generates an alert - demonstrating detection. 
I checked windows 11 ip configuration and notice the ip address is automatic ip address assigning (APIPA). Then I restarted Windows 11.
On Kali ping 192.168.1.111 #and check tcpdump on snort vm


<img width="329" height="27" alt="image" src="https://github.com/user-attachments/assets/856068c1-5d21-45f3-aa65-4d1bbdf95ff9" />  <img width="604" height="213" alt="image" src="https://github.com/user-attachments/assets/87b03ca3-bb5c-4c3f-becf-908174429a75" />

Fig 4.6.5.2, illustrate network packet capture via tcpdump on the Snort sensor confirmed that ICMP echo request packets originating from the Kali endpoint (192.168.1.113) were successfully received at the Snort monitoring interface (enp0s8) bound for the Windows 11 target (192.168.1.111). This validates Layer 2/3 reachability and demonstrates full packet visibility at the IDS inspection point.
As shown in Figure 4.6.5.1, Snort did not generate an alert when Kali pinged the Windows 11 target. This indicates that Snort's active rule set is not currently configured to trigger alerts for this ICMP traffic.
Step 2 - Configure Snort rule to generate an alert:
Press Control + C to stop the running Snort
Run this command:
sudo grep -n "ips =" /usr/local/etc/snort/snort.lua
IPS output: 188:ips =
This confirms that the active snort.lua contains the ips configuration at line 188.
Run the following command to list the rule files available within the Snort installation directory:
sudo find /usr/local/etc/snort -type f -name "*.rules" –print
Rule Installation Output:
usr/local/etc/snort/sensitive_data.rules
/usr/local/etc/snort/file_magic.rules
/usr/local/etc/snort/lua/sensitive_data.rules
/usr/local/etc/snort/lua/file_magic.rules
This confirms that the current installation has rule files, but none of those are appropriate for Scenario 5 custom ICMP detection test.
Validate the original snort configuration
Run this command:
Sudo snort -T -c /usr/local/etc/snort/snort.lua     # -T means test


<img width="271" height="27" alt="image" src="https://github.com/user-attachments/assets/c1c84586-c567-45dc-b59a-5c93411ab455" />  <img width="503" height="91" alt="image" src="https://github.com/user-attachments/assets/a13bf79b-5444-4c3c-9dc6-f0785b21237b" />

Figure 4.6.5.3 verifies that the Snort configuration file is valid and free of syntax errors.
Step 3 - Create a Dedicated Rule for Scenario 5
Run this command:
sudo nano /usr/local/etc/snort/scenario5.rules
put this inside the nano file: alert icmp 192.168.1.113 any -> 192.168.1.111 any (msg:"SCENARIO 5 - ICMP activity from Kali to Windows"; sid:1000001; rev:1;)
This means:
•	alert - generate an IDS alert 
•	icmp - inspect ICMP traffic 
•	192.168.1.113 - Kali/source 
•	192.168.1.111 - Windows/destination 
•	msg - identify the experiment 
•	sid:1000001 - our locally defined signature ID 
•	rev:1 - rule revision
Now we will stop the current Snort process and start Snort with Scenario 5 rule:
Command to run:
sudo snort -i enp0s8 -c /usr/local/etc/snort/snort.lua -R /usr/local/etc/snort/scenario5.rules -A alert_fast
From Kali:
ping -c 4 192.168.1.111
Remember, Windows firewall is still configured to reject traffic from: Kali 192.168.1.113, we actually don't need Windows to reply. We only need the ICMP echo requests to be generated and visible to Snort.
Step 4 – Watch Snot
Snort has generated an alert: 

<img width="250" height="27" alt="image" src="https://github.com/user-attachments/assets/0ecb8d0a-5146-48ea-97d5-d6858811c9c6" />  <img width="511" height="310" alt="image" src="https://github.com/user-attachments/assets/e84e9efb-18d5-4ab2-948a-a365743025b6" />

Figure 4.6.5.4 shows Snort can observe network traffic and, when a configured detection signature matches the traffic, generate an IDS alert independently of the endpoint's firewall enforcement.

Scenario 5 gives us three separate pieces of evidence

Test stage	Result	Evidence
Packet visibility	Successful	tcpdump captured ICMP
Detection	Successful	Snort SID 1000001 matched
Alert generation	Successful	4 Snort alerts generated

Snort SID means signature.
Remark:
Scenario 5 demonstrated that, when correctly positioned and configured with an appropriate detection signature, Snort (IDS) can observe network traffic, match predefined suspicious activity, and generate IDS alerts identifying the source, destination, protocol and timestamp.
Scenario 6 - pfSense UTM Traffic Filtering and Blocking
Objective:
To evaluate the ability of pfSense (UTM) to enforce network level traffic filtering and blocking policies on traffic traversing the gateway.
Security Layer Evaluated: pfSense UTM
To evaluate the ability of pfSense to enforce network-level traffic filtering and blocking policies on traffic traversing the gateway.
Experimentation:
Step 1 - Established the Baseline
Test 1 - Baseline: Prove that Kali can access HTTPS through pfSense.
On Kali, run:
ping -c 4 8.8.8.8
Then test HTTPS:
curl -I --connect-timeout 10 https://microsoft.com

<img width="250" height="28" alt="image" src="https://github.com/user-attachments/assets/2d7084cd-bccb-4866-b971-3b904bab6547" /> <img width="481" height="213" alt="image" src="https://github.com/user-attachments/assets/e8cd2af7-8bf0-49fb-8a96-33ff22c20d30" /> <img width="761" height="308" alt="image" src="https://github.com/user-attachments/assets/abf93985-799b-4078-b477-dbf1480de585" />  <img width="250" height="27" alt="image" src="https://github.com/user-attachments/assets/8ef8402f-c423-4c8e-977f-21863272dd43" />

The baseline test and HTTPS connection were verified as successful, as demonstrated in Figures 4.6.6.1 and 4.6.6.2 respectively.
Step 2 - Create the pfSense TCP/443 block rule
Create a new firewall rule to block HTTPS traffic from Kali
Field	Setting
Action	Block
Interface	LAN
Address Family	IPv4
Protocol	TCP
Source	Single host
Source address	192.168.1.113
Destination	Any
Destination Port	HTTPS (443)
Description	SCENARIO 6 - Block Kali HTTPS Traffic

<img width="584" height="160" alt="image" src="https://github.com/user-attachments/assets/a98405f0-0116-4ee9-a57e-0366cae5e58e" /> <img width="864" height="144" alt="image" src="https://github.com/user-attachments/assets/b069cdd5-e89e-433c-8b0f-a40ab5627cbf" /> <img width="890" height="66" alt="image" src="https://github.com/user-attachments/assets/2d61b2f2-52f9-442d-9fce-d2a7940f81a4" /> <img width="878" height="154" alt="image" src="https://github.com/user-attachments/assets/b1d3747e-00eb-4f16-bd13-12933c1c1db7" /> <img width="911" height="55" alt="image" src="https://github.com/user-attachments/assets/f80bd96f-0aac-494b-9642-49789d2a4e5f" /> <img width="395" height="33" alt="image" src="https://github.com/user-attachments/assets/9bf8e44b-43a4-4df1-a23a-fc53ae86e5f9" />

Step 3 – Test the Block
From Kali:
curl -I --connect-timeout 10 https://example.com

<img width="467" height="80" alt="image" src="https://github.com/user-attachments/assets/4ee9c0ff-eb11-423d-8d69-894f3a9ec78a" />  <img width="268" height="33" alt="image" src="https://github.com/user-attachments/assets/e8228b0c-ff13-4f6f-ba6e-39b9a27b965d" />

Step 3 – Restore Connectivity
The firewall block rule will now be removed.

<img width="395" height="33" alt="image" src="https://github.com/user-attachments/assets/c3e52526-e1a5-4507-a70b-533aaf9105c2" /> <img width="554" height="187" alt="image" src="https://github.com/user-attachments/assets/a0ac4ec6-4cae-476d-97d9-578b1a6ef936" /> <img width="891" height="172" alt="image" src="https://github.com/user-attachments/assets/598e5a2a-49f3-4894-acf2-76bef216d2c3" /> <img width="903" height="92" alt="image" src="https://github.com/user-attachments/assets/695bf586-58cb-4f3f-bd55-cee54b915273" /> <img width="881" height="130" alt="image" src="https://github.com/user-attachments/assets/1370537c-eabd-499c-8aa7-30c264c8444b" />

Step 4 – Test the Unblock Rule
From Kali run: 
curl -I --connect-timeout 10 https://microsoft.com

<img width="598" height="242" alt="image" src="https://github.com/user-attachments/assets/84299584-e99f-480c-92b1-7d43489c3fd6" /> <img width="411" height="33" alt="image" src="https://github.com/user-attachments/assets/47a6e060-5f28-4138-b426-c21ad8241a5f" />

Remark:
The experiment successfully demonstrated the effectiveness of UTM as a network-level traffic enforcement control. pfSense (UTM) successfully identified and blocked TCP traffic destined for port 443 originating from the Kali Linux attacker/test host (192.168.1.113), preventing Kali from accessing HTTPS services through the gateway. Upon removal of the blocking rule, HTTPS connectivity from Kali was successfully restored, confirming that the observed disruption was attributable to the pfSense (UTM) firewall policy. The results demonstrate that UTM can enforce granular, policy-based traffic filtering on gateway-bound traffic, providing an additional layer of defence beyond endpoint-based controls.



























 






































 

