# Incident Report: Unauthorized Privilege Escalation

## 1. Incident Summary

Wazuh SIEM detected a series of suspicious authentication and account-related activities on a Windows 11 system. The incident started with multiple failed login attempts and later resulted in a successful login. Shortly after, a new user account was created and added to the local Administrators group, indicating a potential unauthorized privilege escalation.

## 2. Detection Source

* **SIEM:** Wazuh
* **Log Source:** Windows Security Event Channel
* **Agent Name:** windows-macbook

## 3. Timeline of Events

| Time                  | Event Description                        | Wazuh Rule ID |
| --------------------- | ---------------------------------------- | ------------- |
| Jan 22, 2026 22:06:54 | Multiple failed logon attempts detected  | 60122         |
| Jan 22, 2026 22:07:14 | Successful user logon recorded           | 60106         |
| Jan 22, 2026 22:23:09 | New local user account created           | 60109         |
| Jan 22, 2026 22:23:34 | User added to local Administrators group | 60154         |

## 4. Monitoring Context and Key Evidence

### Wazuh Dashboard Overview

![Wazuh Dashboard](screenshots/01-wazuh-dahsboard.png)

* Confirms the Wazuh SIEM is operational.
* Validates that alerts in this report are from a live monitored system.

### Active Agent

![Active Agent](screenshots/02-agents-view.png)

* Shows the Windows agent is active and reporting events.

### Logon Failure Events

![Logon Failure Events](screenshots/03-logon-failure.png)

Multiple failed authentication attempts were observed, consistent with password-guessing or unauthorized access attempts.

### Successful Logon Event

![Successful Logon Event](screenshots/04-logon-success.png)

A successful login occurred after several failed attempts, confirming valid credentials were eventually used.

### User Account Creation

![User Account Creation](screenshots/05-user-created.png)

A new local user account was created on the system, potentially enabling persistence for an attacker.

### Privilege Escalation Alert

![Privilege Escalation Alert](screenshots/06-privilege-escalation.png)

Wazuh generated an alert for privilege escalation activity.

### Privilege Escalation Details

![Privilege Escalation Details](screenshots/07-privilege-escalation-detailed.png)

The newly created user was added to the local Administrators group, a high-risk security event.

---

## 5. Incident Evidence and Analysis

Multiple failed authentication attempts were observed, followed by a successful login. A new local user account was then created and added to the local Administrators group.

The sequence of events indicates that valid credentials were obtained or used, followed by account creation and modification of local group membership. These activities are consistent with an attempt to establish elevated access on the Windows system.

---

## 6. MITRE ATT&CK Mapping

* **T1078 – Valid Accounts**
* **T1098 – Account Manipulation**
* **T1484 – Privilege Escalation (Local Group Membership Modification)**

---

## 7. Impact Assessment

The system was exposed to elevated privileges, which could allow an attacker to gain full administrative control. This may lead to system misuse, data exposure, or lateral movement within the environment.

---

## 8. Recommendations

* Enforce strong password policies and account lockout rules.
* Monitor and alert on changes to administrative group memberships.
* Enable real-time alerts for privilege escalation activities.
* Perform regular audits of local user accounts and permissions.

---

## 9. Conclusion

This incident demonstrates how Wazuh SIEM can correlate authentication failures, account creation, and privilege escalation events to identify potentially malicious activity on Windows endpoints. The visibility provided by centralized logging enables timely detection and response to privilege abuse scenarios.
