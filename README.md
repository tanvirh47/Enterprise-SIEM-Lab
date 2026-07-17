# Enterprise SIEM Lab using Wazuh

## Overview

This project demonstrates the deployment of a Security Information and Event Management (SIEM) lab using **Wazuh**, **Sysmon**, **Windows Server 2022**, **Ubuntu Server 24.04**, and **Kali Linux** in a VMware Workstation environment.

The objective of the lab was to simulate common attack scenarios, collect endpoint telemetry, create custom detection rules, and monitor security events through the Wazuh Dashboard.

---

## Objectives

* Deploy a Wazuh SIEM environment.
* Integrate Windows endpoint monitoring using the Wazuh Agent.
* Configure Sysmon for enhanced Windows telemetry.
* Develop custom Wazuh detection rules.
* Simulate real-world attack scenarios.
* Map detections to the MITRE ATT&CK framework.

---

## Lab Architecture

```text
                   VMware Workstation

        Kali Linux                 Windows Server 2022
        (Attacker)                 (Protected Endpoint)
             |                             |
             | SSH / PowerShell            |
             |                             |
             +-----------------------------+
                           |
                           |
                     Ubuntu Server 24.04
                     Wazuh Manager
                     Wazuh Dashboard
```

---

## Technologies Used

* Wazuh 4.14
* Ubuntu Server 24.04 LTS
* Windows Server 2022
* Kali Linux
* Sysmon
* VMware Workstation
* OpenSSH
* PowerShell

---

## Detection Scenarios

### 1. PowerShell Encoded Command Detection

A custom Wazuh rule was created to detect PowerShell commands containing encoded command execution (`-enc`).

**Rule ID:** 100001

**MITRE ATT&CK:** T1059.001 – PowerShell

---

### 2. SSH Brute Force Detection

Multiple failed SSH login attempts were generated from the Kali Linux machine against the Ubuntu server.

Wazuh successfully detected:

* Failed login attempts
* Non-existent user authentication
* SSH brute-force behavior

Example Wazuh rules triggered:

* Rule 5710
* Rule 5712
* Rule 2502
* Rule 5503

---

### 3. Credential Dumping Indicator Detection

A custom Wazuh rule was developed to identify command-line indicators commonly associated with credential dumping techniques.

**Rule ID:** 100002

**MITRE ATT&CK:** T1003 – OS Credential Dumping

---

## Skills Demonstrated

* SIEM Deployment
* Security Monitoring
* Windows Endpoint Monitoring
* Sysmon Integration
* Custom Wazuh Rule Development
* Threat Detection
* Log Analysis
* MITRE ATT&CK Mapping
* Linux System Administration
* VMware Lab Virtualization

---

## Screenshots

The `screenshots/` directory (and supporting documentation) contains evidence of:

* Wazuh Dashboard
* Windows Agent Registration
* Sysmon Event Collection
* Custom PowerShell Detection
* SSH Brute Force Detection
* Credential Dumping Indicator Detection

---

## Future Improvements

* Active Directory integration
* Linux endpoint monitoring
* Email alerting
* File Integrity Monitoring expansion
* Sigma rule conversion
* Automated incident response

---

## Disclaimer

This project was built in an isolated VMware Workstation lab for educational and defensive cybersecurity purposes. All attack simulations were conducted within a controlled environment.
