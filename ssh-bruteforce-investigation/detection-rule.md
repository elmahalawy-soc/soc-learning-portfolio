# SIEM Detection Rule – SSH Brute Force

## Rule Name
SSH Brute Force – Multiple Failed Logins

## Description
Detects potential SSH brute-force attacks by identifying multiple failed authentication attempts within a short time window.

## Data Source
- Linux authentication logs (`auth.log`)
- Service: sshd

## Detection Logic
Trigger an alert if:
- More than 5 failed SSH login attempts
- Occur within 10 minutes
- From the same source IP or against the same host

## Severity
Medium

## MITRE ATT&CK
- T1110 – Brute Force

## Analyst Response
- Review failed and successful logins
- Check for success after failure
- Escalate if compromise is suspected

