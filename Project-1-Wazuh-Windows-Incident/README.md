# SOC Log Analysis Using Wazuh SIEM

## Overview
This project focuses on basic SOC analyst tasks using Wazuh SIEM. The goal was to collect and analyze Windows security logs to understand common security events such as failed logins, successful logins, user creation, and privilege escalation.

## Lab Environment
- SIEM: Wazuh 4.7.5
- SIEM Host: Ubuntu 22.04 LTS
- Log Source: Windows 11 Pro
- Agent: Wazuh Agent
- Virtualization: VMware Fusion

## Objectives
- Deploy and configure Wazuh SIEM
- Collect Windows Security Event logs
- Detect suspicious authentication activity
- Identify privilege escalation events
- Produce a SOC-style incident report

## Tools Used
- Wazuh SIEM for log collection and analysis
- Windows Event Channel for security logs
- VMware / VirtualBox for virtual machines
- PowerShell for basic Windows commands

## Project Outcome
The project successfully identified multiple security events, including a privilege escalation activity where a user was added to the local Administrators group. These events were analyzed using the Wazuh dashboard and mapped to relevant MITRE ATT&CK techniques, demonstrating real-world SOC monitoring skills.
