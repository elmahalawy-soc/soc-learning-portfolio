# SOC Incident Report – SSH Brute Force Attempt

## Incident Overview
Multiple failed SSH authentication attempts were detected against a Linux server. The activity was consistent with an automated brute-force attempt. No successful login was observed.

## Incident Type
SSH Brute-Force Attempt (Unsuccessful)

## Severity
Medium

## Affected Asset
- System: Ubuntu Linux Server (Lab Environment)
- Service: SSH (sshd)
- Log Source: /var/log/auth.log

## Detection
The incident was identified through analysis of Linux authentication logs. Repeated failed login attempts were observed within a short time window.

## Indicators of Compromise (IOCs)
- Source IPs:
  - 45.83.91.22
  - 185.220.101.5
- Event Type: Failed SSH authentication
- Targeted Users: root, admin

## Investigation Summary
- SSH logs were filtered for failed authentication attempts.
- External IP addresses were isolated.
- Login attempts were correlated by source and time.
- No successful authentication was detected after the failed attempts.

## Impact Assessment
- Confidentiality: Not impacted
- Integrity: Not impacted
- Availability: Not impacted

## Response Actions
- Activity monitored
- No IP blocking performed due to lack of successful authentication
- Detection logic documented for future automation

## Root Cause Analysis
The activity is consistent with automated internet-wide SSH scanning and brute-force attempts.

## Recommendations
- Implement rate limiting or fail2ban
- Disable password-based SSH authentication
- Enforce SSH key-based authentication
- Continue monitoring for repeated attempts

## MITRE ATT&CK Mapping
- Tactic: Credential Access
- Technique: T1110 – Brute Force

## Conclusion
This incident represents an unsuccessful SSH brute-force attempt. Existing controls prevented unauthorized access, and no compromise occurred.

