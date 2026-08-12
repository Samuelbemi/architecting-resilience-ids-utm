# Experimental Scenarios

This directory contains the controlled security-testing scenarios conducted as part of the research.

The experiments are designed to evaluate the practical capabilities of Snort IDS, pfSense UTM, and Windows security controls within a defence-in-depth architecture.

All testing is conducted within the controlled laboratory environment documented in the `lab/` directory.

## Planned Experimental Scenarios

### Scenario 1 — Baseline ICMP Connectivity and Network Visibility

Establish baseline connectivity between the test/attacker machine and the Windows case-study endpoint and document the resulting network behaviour and visibility.

### Scenario 2 — TCP Port and Service Detection

Use controlled TCP scanning and service detection to identify exposed ports and services on the Windows case-study endpoint.

### Scenario 3 — Network Scanning and Reconnaissance

Conduct controlled network reconnaissance from Kali Linux and evaluate the visibility and detection capabilities of the security controls.

### Scenario 4 — Windows Firewall Protection and Controlled Bypass Testing

Evaluate Windows Firewall behaviour under controlled testing conditions and examine how endpoint firewall controls affect network accessibility and security visibility.

### Scenario 5 — Snort IDS Detection and Alert Generation

Generate controlled network activity and evaluate Snort's ability to identify, classify, and alert on relevant traffic.

### Scenario 6 — pfSense UTM Traffic Filtering and Blocking

Evaluate pfSense firewall and UTM controls by applying controlled filtering and blocking policies and observing their effect on test traffic.

### Scenario 7 — IDS and UTM Defence Validation

Evaluate the complementary operation of Snort IDS and pfSense UTM controls under controlled security-testing conditions.

### Scenario 8 — Defence-in-Depth Security Effectiveness Evaluation

Assess the overall effectiveness of the layered security architecture by analysing the combined contribution of Windows security controls, Snort IDS, and pfSense UTM.

## Experimental Evidence

Each scenario will document, where applicable:

* Objective
* Experimental environment
* Network conditions
* Test methodology
* Commands executed
* Expected behaviour
* Observed behaviour
* Snort alerts
* pfSense logs
* Windows responses
* Screenshots
* Results
* Analysis
* Security implications
* Scenario conclusion
