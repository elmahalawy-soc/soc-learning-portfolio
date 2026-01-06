# SSH Brute Force Investigation

This lab demonstrates how SSH authentication logs were analyzed to detect and investigate a brute-force attack attempt in a lab environment.

## Skills demonstrated
- Linux log analysis
- SSH authentication monitoring
- Brute-force detection logic
- SOC-style incident investigation

## Tools
- Ubuntu Linux
- auth.log
- awk / grep

# SSH Brute Force Investigation

This lab demonstrates how SSH authentication logs were analyzed to detect, investigate, and respond to brute-force attack scenarios using a SOC-style workflow.

## Scenarios Covered
1. **Unsuccessful SSH Brute-Force Attempt**
   - Multiple failed login attempts
   - No successful authentication
   - Medium severity
   - Monitoring and detection only

2. **SSH Success After Failed Logins**
   - Multiple failed login attempts followed by a successful login
   - High severity incident
   - Escalation and automated response considerations

## Skills Demonstrated
- Linux authentication log analysis
- SSH security monitoring
- Brute-force and credential compromise detection
- SIEM-style detection rule design
- SOC incident reporting and escalation logic
- SOAR / automation concepts

## Tools
- Ubuntu Linux
- auth.log
- awk / grep
