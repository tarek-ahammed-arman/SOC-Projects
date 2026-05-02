# Brute-Force Detection and Account Lockout Analysis Using Wazuh SIEM

## Overview
This project demonstrates how authentication security events are monitored and analyzed using Wazuh SIEM. It focuses on detecting brute-force login attempts, evaluating account lockout behavior, and validating system response using Windows authentication logs in a controlled environment.

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
Wazuh successfully detected repeated failed login attempts followed by an automatic account lockout. Post-incident analysis confirmed that no successful authentication occurred after the lockout, indicating effective enforcement of access control mechanisms. This exercise validated the reliability of authentication monitoring and security control behavior in a simulated environment.
