# SOC Incident Report – SSH Success After Failed Logins

## Incident Overview
Multiple failed SSH authentication attempts were detected from an external source, followed by a successful SSH login. This pattern is indicative of a potential credential compromise via brute-force or password guessing.

## Incident Type
SSH Brute Force – Success After Failure

## Severity
High

## Affected Asset
- System: Ubuntu Linux Server (Lab Environment)
- Service: SSH (sshd)
- Log Source: /var/log/auth.log

## Detection
The incident was identified by correlating failed SSH authentication events with a subsequent successful login from the same source within a short time window.

## Indicators of Compromise (IOCs)
- Source IP: 185.220.101.5
- Events:
  - Multiple `Failed password` attempts
  - Followed by `Accepted password`
- Targeted User: sameh

## Timeline Summary
- T0: Multiple failed SSH login attempts detected
- T0 + minutes: Successful SSH login from same source
- T0 + analysis: Incident escalated

## Investigation Summary
- SSH authentication logs were reviewed for failed and successful login events.
- Events were correlated by source IP and timestamp.
- The same source IP was responsible for both failed and successful authentication.
- This confirms successful access following repeated authentication attempts.

## Impact Assessment
- Confidentiality: Potentially impacted
- Integrity: Potentially impacted
- Availability: Not impacted

## Response Actions
- User account flagged for investigation
- Source IP recommended for immediate blocking
- Password reset recommended
- SSH logs preserved for forensic review

## Automated Response (SOAR Concept)
If detected in production:
- Block source IP for 24 hours
- Disable affected user account
- Force credential reset
- Generate critical SOC alert
- Notify incident response team

## Root Cause Analysis
The most likely cause is weak or reused credentials that were successfully guessed after multiple attempts.

## Recommendations
- Disable password-based SSH authentication
- Enforce SSH key-based authentication
- Enable rate limiting / fail2ban
- Implement automated detection and response for success-after-failure patterns

## MITRE ATT&CK Mapping
- Tactic: Credential Access
- Technique: T1110 – Brute Force

## Conclusion
This incident represents a confirmed SSH compromise scenario where access was achieved after repeated authentication failures. Immediate containment and remediation actions are required.

