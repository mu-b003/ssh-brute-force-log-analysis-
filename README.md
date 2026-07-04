# SSH Brute Force Log Analysis

## Overview

This project demonstrates the detection and analysis of an SSH brute-force attack in a controlled virtual lab environment. The attack was simulated from a Kali Linux machine targeting an Ubuntu system running an OpenSSH server. After the attack, Linux authentication logs were analyzed to identify failed login attempts and investigate the attack activity using standard command-line tools.

---

## Objectives

* Verify the SSH service on the target machine.
* Simulate an SSH brute-force attack using Hydra.
* Analyze Linux authentication logs.
* Identify failed login attempts and the attack source.
* Demonstrate a basic SOC Level 1 investigation workflow.

---

## Lab Environment

| Component      | Details             |
| -------------- | ------------------- |
| Attacker       | Kali Linux 2026     |
| Target         | Ubuntu Linux        |
| Virtualization | VMware Workstation  |
| Service        | OpenSSH Server      |
| Attack Tool    | Hydra               |
| Log File       | `/var/log/auth.log` |

---

## Tools Used

* Hydra
* OpenSSH
* Linux Terminal
* grep
* awk
* systemctl
* ip

---

## Project Workflow

1. Verify the SSH service.
2. Identify the target IP address.
3. Prepare a password wordlist.
4. Simulate an SSH brute-force attack using Hydra.
5. Analyze authentication logs.
6. Identify the attack source and failed login attempts.
7. Document findings and recommendations.

---

## Repository Structure

```text
ssh-brute-force-log-analysis/
│
├── README.md
├── LICENSE
├── DISCLAIMER.md
│
├── report/
│   └── SSH_Brute_Force_Log_Analysis_Report.pdf
│
├── evidence/
│   ├── 01-ssh-status.png
│   ├── 02-ip-address.png
│   ├── 03-hydra-attack.png
│   ├── 04-failed-password-log.png
│   └── 05-log-analysis.png
│
└── commands-used.md
```

---

## Evidence

The repository includes screenshots showing:

* SSH service verification.
* Network configuration.
* Hydra attack execution.
* Authentication log analysis.
* Investigation results.

---

## Key Findings

* Multiple failed SSH login attempts were detected.
* The attack targeted a single user account.
* All attempts originated from one source IP address.
* The activity matched the behavior of an automated brute-force attack.
* No successful authentication was identified during the investigation.

---

## Report

The complete technical report is available in the **report** directory.

---

## Disclaimer

This project was conducted entirely in a controlled virtual laboratory for educational and defensive cybersecurity purposes only. No unauthorized systems were targeted.

---

## License

This project is licensed under the MIT License.
