
# 🛡️ SOC Home Lab Overview

### Overview
This repository documents my hands-on Security Operations Center (SOC) home lab, designed to simulate real-world Tier I SOC workflows. 
The lab focuses on endpoint monitoring, log collection, and network traffic analysis, using tools commonly employed in SOC environments.

### Objectives
- Collect and analyze endpoint logs using Sysmon and Windows Event Logs
- Monitor Windows and Linux endpoints with Wazuh SIEM
- Capture and analyze network activity with Wireshark
- Validate log forwarding, configuration, and baseline security controls
- Simulate SOC tasks such as alert triage, false positive filtering, and basic incident response

### Lab Architecture
Components Used:
- Wazuh Manager – Central log collection and monitoring
- Windows Agent – Endpoint monitoring via Sysmon
- Kali Linux – For test traffic generation and vulnerability assessment
- Wireshark – Network packet capture and analysis
- VMware Workstation Pro 17 – Virtualization for multi-OS lab setup


### Setup Summary
- Installed Wazuh Manager on Ubuntu and configured it to receive logs from agents
- Deployed Wazuh Agent on Windows endpoint
- Configured Sysmon to capture process creation, network connections, and DNS events
- Validated log forwarding and monitored events in the Wazuh dashboard
- Used Wireshark to inspect network traffic and verify event triggers

### Future Enhancements
- Integrate Elastic Stack (Elasticsearch + Kibana) for advanced log visualization and dashboarding
- Incorporate Suricata IDS for deeper network intrusion detection
- Expand log analysis and alert investigation workflows
- Add automation scripts for alert triage and reporting

### Tools Used
SIEM-Wazuh, Endpoint Monitoring- Sysmon, Packet Capture- Wireshark, OS- Windows 11, Linux, Ubuntu, VM- VM pro workstation17, Scripting -Bash.



