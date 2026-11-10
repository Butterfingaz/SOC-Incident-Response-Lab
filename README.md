# SOC-Incident-Response-Lab
Linux Endpoint Audit &amp; Programmatic Log Triage Project

## 1. Project Overview
This project demonstrates defensive security operations, log analysis, and threat hunting inside a Linux sandbox environment. To simulate a real-world incident response triaging workflow, an authentication brute-force logging attack vector was simulated, and system metrics were gathered programmatically via native log analysis tracking to isolate malicious indicators of compromise (IoCs).

## 2. Infrastructure Architecture
* **Testing Platform:** Ubuntu Linux (VirtualBox Sandbox Environment)
* **Log Collection Engine:** Native Linux Syslog Management Architecture
* **Analysis Focus:** Core Security Telemetry Parsing

## 3. Threat Hunting Walkthrough
To simulate an authentication brute-force attempt, a high-severity log injection entry was executed:
```bash
sudo logger -t sshd "Failed password for root from 198.51.100.42 port 4321 ssh2"
```

System log registries were parsed natively via terminal pipelines to map out security events tracking the rogue endpoint footprint structure:
```bash
sudo grep "198.51.100.42" /var/log/auth.log
```

### 📊 Threat Hunt Telemetry Evidence Log

1. <img width="883" height="249" alt="brute-force attack log" src="https://github.com/user-attachments/assets/b70cd7d9-01d8-4597-876c-73b869956b87" />

2. <img width="881" height="177" alt="output matching those log" src="https://github.com/user-attachments/assets/742e1240-1346-4d06-9fdc-31d9dbbe0b77" />




The triage workflow successfully isolated and returned the tracking footprint, mapping the attack metrics directly to the **MITRE ATT&CK Framework under T1110 (Brute Force)** credential access tactics.
