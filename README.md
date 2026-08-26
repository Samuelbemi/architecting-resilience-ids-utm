# Architecting Resilience: IDS and UTM in Windows Enterprise Defence-in-Depth

## Research Project

This repository contains the research, practical implementation, experimental methodology, technical configurations, evidence, results, and supporting materials for:

**Architecting Resilience: A Practical Evaluation of Intrusion Detection Systems (IDS) and Unified Threat Management (UTM) in Windows Enterprise Defence-in-Depth**

## Research Overview

This research investigates the practical application and effectiveness of layered security controls for Windows enterprise environments.

The study evaluates the complementary roles of an Intrusion Detection System (IDS) and Unified Threat Management (UTM) platform within a defence-in-depth security architecture.

A controlled virtualised laboratory is used to implement and evaluate:

* **Kali Linux** — controlled test/attacker platform
* **Windows 11 Pro** — Windows enterprise case-study endpoint
* **Snort** — Intrusion Detection System (IDS)
* **pfSense** — Unified Threat Management (UTM) platform
* **VirtualBox** — virtualised experimental environment

Controlled security-testing scenarios are conducted to evaluate network visibility, intrusion detection, traffic filtering, prevention, and the effectiveness of combining multiple security controls.

## Research Objectives

The research aims to:

1. Design and implement a practical defence-in-depth architecture for a Windows enterprise environment.
2. Deploy Snort as a network-based Intrusion Detection System.
3. Deploy pfSense as a Unified Threat Management platform.
4. Use Kali Linux as a controlled test and attacker platform.
5. Conduct controlled security-testing scenarios against the Windows case-study endpoint.
6. Evaluate the detection and prevention capabilities of the implemented security controls.
7. Compare the practical roles and capabilities of IDS and UTM technologies.
8. Evaluate the effectiveness and limitations of combining multiple security controls as part of a defence-in-depth architecture.
9. Develop practical recommendations for organisations operating Windows enterprise environments.

## Experimental Environment

The laboratory consists of a Windows 11 Pro case-study endpoint, Kali Linux test/attacker machine, Snort IDS, and pfSense UTM platform operating within a controlled virtualised environment.

The network architecture, system configurations, experimental scenarios, evidence, and results will be documented throughout the research.

## Experimental Scenarios

The research includes controlled scenarios covering:

* Baseline ICMP connectivity and network visibility
* TCP port and service detection
* Network scanning and reconnaissance
* Windows Firewall protection and controlled testing
* Snort IDS detection and alert generation
* pfSense UTM traffic filtering and blocking


## Author

**Samuel Bemi**

Cybersecurity Professional | Cybersecurity Researcher
MSc Computing | CompTIA Security+ | CEH | MCSE | MCSA | CCNA

## Responsible Testing

All security testing documented in this repository is conducted within a controlled laboratory environment against systems owned or explicitly authorised for testing. The research is intended for legitimate cybersecurity research, security evaluation, and educational purposes.
