Configuration Assessment - Finding #2

Scan Date: 25 Oct 2025
Rule ID: 26102
Check Name: Ensure 'Universal Plug and Play (UPnP)' is Disabled
Command Used: services.msc / sc query upnphost
Result: Failed

Description

This rule checks whether Universal Plug and Play (UPnP) is disabled on Windows systems.
UPnP allows automatic discovery and communication between network devices without authentication. While useful in home networks, it poses a significant security risk in enterprise environments by enabling unauthorized network device discovery and potential exploitation.

Rationale

Universal Plug and Play (UPnP) is a real security risk — it allows automatic discovery and attachment to network devices.

Evidence (From Wazuh Dashboard)
Failed policy check detected on 24 Oct 2025
Policy: Disable Universal Plug and Play (UPnP) Service
Severity: Medium
Agent: LAPTOP
Status: Failed (before remediation)

Recommended Configuration

Disable the UPnP Device Host service on system service.

Validation

After applying the configuration, restart the system or agent.
Re-run the compliance scan to verify that Rule 26010 changes from Failed to Passed.

Evidence
EID-26102-Before (Failed result)
EID-26102-After (passed result)

Insight

The failure indicates that Universal Plug and Play (UPnP) is still enabled on the system. UPnP allows devices to automatically discover and connect to each other over the network without user authentication or control.