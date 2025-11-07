 
Configuration Assessment - Finding #1

Scan Date: 25 Oct 2025
Rule ID: 26000
Check Name: Ensure 'Enforce password history'
Command Used: net.exe accounts
Result: Failed

Description

This rule checks whether Windows enforces users to maintain password history, preventing reuse of recent passwords. Reusing passwords increases the risk of credential-based attacks.
 
Rationale

The system allows the user to use the same password, which is a likelihood for brute force attack.

Evidence (From Wazuh Dashboard)
Failed policy check detected on 24 Oct 2025
Policy: Enforce password history
Severity: Medium
Agent: LAPTOP
Status: Failed (before remediation)

Recommended Configuration

Set the recommended enforce password history to 24.

Validation

After applying the configuration, restart the agent and see the rule 26000 changed from failed to passed.

Evidence

EID-26000-Before (Failed result)
EID-26000-After (passed result)

Insight

This finding validates how Wazuh benchmarks local security policy settings against CIS guidelines.