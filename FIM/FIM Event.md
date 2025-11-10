# Observation 1 – Registry Key Deletion (Nov 1, 2025)

**Observation Date & Time:**  
Nov 1, 2025 — 23:05 UTC 

**Source:**
  
- Wazuh Syscheck (File Integrity Monitoring)  
- Windows Event Logs  
- Task Scheduler  
- Sysmon Logs  

---

## Event Description
A registry key deletion was reported by **Wazuh Syscheck** during its scheduled scan.  
The deletion occurred between the **creation** and **termination** of the `svchost.exe` process (23:05–23:25).

## Process 
Attribute  - Process, User, creation, Termination time 
Details    - svchost.exe, SYSTEM/Admin, 23:05, 23:25


## Correlation & Timeline Analysis

Time (UTC)  - 23:05                            23:05–23:25                     23:25                             After 23:25 
Source      - Sysmon                            -                              Sysmon                           Wazuh Syscheck    
Observation - svchost.exe process created  System processes running   svchost.exe` process terminated       Registry key deletion reported

**Summary:**  
- Syscheck detected the registry deletion **after** it occurred.  
- Sysmon did not log registry activity → likely due to missing registry key configuration.  
- No relevant entries in Windows Event Logs or Wazuh Agent logs.


## Investigation Steps Taken
- Reviewed **Wazuh Manager agent logs** for Syscheck and FIM events.  
- Checked **Windows System** and **Security** logs.  
- Inspected **Task Scheduler** logs for automated activity.  
- Reviewed **Sysmon logs** on the agent.  
- Verified the legitimacy of `svchost.exe` process (Microsoft-signed system process).  


## Analysis & Findings
- Event aligns with **normal system maintenance or Windows update** activity.  
- Registry deletion performed under **SYSTEM/Admin** context by a **legitimate process**.  
- Sysmon did not log the event → due to **limited registry key coverage** in the current configuration.


## Conclusion & Recommendations
**Conclusion:**  
- Registry key deletion is **benign** and **system-generated**.  
- No evidence of compromise or suspicious behavior.

## Insights & Lessons Learned

### Multi-Source Correlation
- Correlating Wazuh, Sysmon, and Event Logs helped confirm the activity’s legitimacy.  
 **Takeaway:** Cross-validating multiple data sources is key for accurate triage and false-positive reduction.