# Incident Response Report – SSH Brute-Force Attack Detection

## 1. Incident Overview

- **Incident Name:** SSH Brute-Force Attack
- **Project:** SOC Environment – Brute-Force Attack Detection
- **SIEM:** Splunk Enterprise
- **Target:** Windows 10 Machine
- **Attack Source:** Parrot Security OS
- **Severity:** Medium 
- **Status:** Investigated/Resolved

## 2. Incident Description

An SSH brute-force attack was simulated in an isolated SOC lab environment.

The attacker machine repeatedly attempted to authenticate to the Windows 10 target using different usernames and passwords.

Windows OpenSSH authentication logs were collected through the Splunk Universal Forwarder and forwarded to Splunk Enterprise for monitoring and investigation.

The activity generated multiple failed authentication events, followed by a successful login using a valid test credential.

## 3. Detection

Splunk Enterprise was used to identify and investigate repeated SSH authentication failures.

The investigation focused on:

- Repeated failed SSH login attempts
- Source IP address of the attacker
- Targeted usernames
- Target machine
- Authentication timestamps
- Successful authentication following failed attempts

OpenSSH Operational logs were used as the primary evidence for SSH authentication activity.

Windows Security Event ID 4625 represents a failed Windows logon and was reviewed separately where available.

## 4. Investigation

The SOC analyst investigated the collected authentication events in Splunk to determine whether the activity represented a possible brute-force attack.

The following information was examined:

| Investigation Item | Details |
|---|---|
| Attack Type | SSH Brute-Force Attack |
| Source IP | `10.254.200.181` |
| Target IP | `10.254.200.237` |
| Attacker Machine | Parrot Security OS |
| Target Machine | Windows 10 |
| Authentication | SSH |
| Log Source | OpenSSH/Operational |
| SIEM | Splunk Enterprise |
| Evidence | Splunk authentication logs |

Multiple failed authentication attempts from the same source IP were observed.

Several usernames were targeted during the simulation. A successful SSH authentication event was also identified for the test account.

## 5. Correlation

Authentication events were correlated in Splunk to understand the sequence of activity.

**Attack sequence:**

```text
Multiple Failed SSH Login Attempts
              ↓
Attacker Source IP Identified
              ↓
Targeted Usernames Investigated
              ↓
Successful SSH Login Identified
              ↓
Authentication Activity Correlated
              ↓
Suspicious Activity Assessed
```

This correlation helped identify repeated authentication failures and determine whether a successful login occurred during the simulated attack.

## 6. Response Actions

After identifying the suspicious activity, the following response actions were considered:

- Identify and block the suspicious source IP.
- Review the targeted user accounts.
- Reset test account credentials where necessary.
- Review successful authentication activity.
- Monitor further SSH connection attempts.

**Actions performed in this lab:**

- Identified the simulated attacker's IP address.
- Reviewed failed and successful SSH authentication events.



## 7. Evidence

The following evidence was collected during the investigation:

- VirtualBox lab environment setup
- Attacker IP identification
- SSH brute-force attack simulation
- Windows OpenSSH failed authentication events
- Splunk OpenSSH log collection
- Source IP and targeted username analysis
- Successful SSH authentication event
- Authentication correlation results
- Splunk monitoring dashboard
- Windows authentication event evidence, where available

Screenshots are included in the project repository.

## 8. Incident Conclusion

The simulated SSH brute-force activity generated multiple failed authentication events on the Windows 10 target.

The authentication logs were successfully collected and analyzed using Splunk Enterprise.

The attacker source IP and targeted usernames were identified, and a successful SSH authentication event was investigated.

This project demonstrates a basic SOC investigation workflow:

```text
Attack Simulation
       ↓
Log Collection
       ↓
SIEM Detection
       ↓
Investigation
       ↓
Event Correlation
       ↓
Incident Response
       ↓
Documentation
```

## 9. Lessons Learned

This project provided practical experience in:

- Monitoring SSH authentication logs
- Detecting repeated failed login attempts
- Identifying suspicious source IP addresses
- Investigating targeted usernames
- Correlating failed and successful authentication events
- Using Splunk SPL for security investigations
- Creating SIEM dashboards
- Documenting security incidents

## 10. Final Status

| Activity | Status |
|---|---|
| Incident | Brute-Force Login Attack |
| Attack Simulation | Completed |
| Log Collection | Completed |
| Detection | Successful |
| Investigation | Completed |
| Correlation | Completed |
| Evidence Collection | Completed |
| Incident Documentation | Completed |




