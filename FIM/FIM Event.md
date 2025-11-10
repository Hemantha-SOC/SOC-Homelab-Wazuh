Observation ID / Title: Observation 1 – Registry Key Deletion (Nov 1, 2025)

Observation Date & Time: Nov 1, 2025, ~23:05 UTC (~7 AM local time)

Source / Sensor: Wazuh Syscheck, Windows Event Logs, Task Scheduler, Sysmon logs

Event Description:

Registry key deletion reported by Wazuh Syscheck scheduled scan.

Deletion occurred between svchost.exe process creation and termination (23:05–23:25).

Sysmon logs on the agent do not record this registry deletion.

Process / User Context:

Process: svchost.exe

User: SYSTEM / Admin

Creation: 23:05

Termination: 23:25

Correlation & Timeline Analysis:

Scheduled Syscheck scan captured deletion after it occurred

Task Scheduler log at 14:41 unrelated

Sysmon logs captured process creation/termination, but not the registry deletion

No Wazuh agent logs or Windows Event Logs recorded the deletion

Investigation Steps Taken:

Reviewed Wazuh Manager agent logs

Reviewed Windows System / Security logs

Checked Task Scheduler logs

Checked Sysmon logs on agent

Confirmed process legitimacy (svchost.exe)

Analysis / Findings:

Event aligns with normal Windows system maintenance or update tasks

Admin/system context and svchost.exe process confirm non-malicious behavior

Missing Sysmon event likely due to configuration not monitoring this key

Conclusion / Recommendation:

Registry key deletion is benign, system-generated

No immediate action required

Optional: review Sysmon configuration to monitor additional registry keys for future analysis

Evidence / References:

Wazuh Syscheck screenshot

Sysmon logs for 23:05–23:25 (process creation/termination)

Task Scheduler logs