# SOC Brute-Force Detection and Account Lockout Using Wazuh

## Overview
This project demonstrates how a SOC analyst detects a brute-force login attempt and verifies that the attack was blocked using account lockout controls. Wazuh SIEM was used to monitor Windows authentication logs and confirm that no successful logins occurred for the locked account.

## Lab Environment
- SIEM: Wazuh 4.7.5
- SIEM Host: Ubuntu 22.04 LTS
- Log Source: Windows 11 Pro
- Agent: Wazuh Agent
- Virtualization: VMware Fusion

## Objectives
- Detect multiple failed login attempts
- Identify account lockout events
- Verify defensive response effectiveness
- Analyze post-lockout authentication behavior
- Create a SOC-style incident report

## Tools Used
- Wazuh SIEM for security monitoring
- Windows Security Event Logs
- PowerShell for login testing
- VMware for virtual lab setup

## Project Outcome
Wazuh successfully detected repeated login failures followed by an automatic account lockout. Post-incident analysis confirmed that the locked user did not successfully authenticate again, while only SYSTEM logon events were observed. This validated that the security control worked as expected.
