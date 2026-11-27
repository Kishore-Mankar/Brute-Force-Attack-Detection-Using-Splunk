# Brute-Force Attack Detection using Splunk

## Objective

Detect and investigate repeated SSH authentication failures using Splunk in a simulated SOC environment.

## Tools Used

- Splunk Enterprise
- Splunk Universal Forwarder
- Kali Linux
- Parrot Security OS
- Windows 10
- Sysmon
- OpenSSH


## Attack Flow

```text
Attacker (Parrot OS)
        |
        ↓
SSH Brute-Force Attempts
        |
        ↓
Windows 10 (Target)
        |
        ↓
Authentication Logs
        |
        ↓
Splunk Enterprise (SIEM)
        |
        ↓
Detection & Investigation
        |
        ↓
Incident Response
```

## Key Detection

Detected repeated failed SSH authentication attempts from the same source IP using Splunk searches.

Identified:
- Attacker IP
- Target IP
- Multiple targeted usernames
- Failed and successful SSH login events

## Incident Response

- Identified the suspicious source IP.
- Investigated authentication events.
- Reviewed the successful login activity.
- Correlating login activity.
- Documenting recommended response actions.

## Evidence

Screenshots and the incident response report are included in this repository

