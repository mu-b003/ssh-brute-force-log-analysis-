# SSH Brute Force Attack Detection and Log Analysis

## Executive Summary

This project demonstrates how a Security Operations Center (SOC) analyst can detect and investigate an SSH brute-force attack in a controlled virtual laboratory. The attack was simulated from a Kali Linux machine against an Ubuntu system running an OpenSSH server. After the attack simulation, authentication logs were analyzed to identify failed login attempts, determine the attack source, and understand the attack pattern. The project follows a basic SOC Level 1 investigation workflow using standard Linux command-line tools.

---

# Project Objectives

The objectives of this project were to:

* Configure and verify the SSH service on the target machine.
* Simulate an SSH brute-force attack in a controlled environment.
* Analyze Linux authentication logs.
* Identify the attacking IP address.
* Investigate failed authentication attempts.
* Demonstrate fundamental SOC Level 1 log analysis techniques.

---

# Lab Environment

| Component        | Description        |
| ---------------- | ------------------ |
| Attacker Machine | Kali Linux 2026    |
| Target Machine   | Ubuntu Linux       |
| Virtualization   | VMware Workstation |
| Service          | OpenSSH Server     |
| Attack Tool      | Hydra              |
| Log File         | /var/log/auth.log  |

---

# Network Configuration

The target machine's network configuration was verified using:

```bash
ip a
```

This command displayed the active network interface and confirmed the IP address of the Ubuntu virtual machine.

**Screenshot Placeholder**

*(Insert screenshot: 02-ip-address.png)*

---

# SSH Service Verification

Before launching the attack, the SSH service was verified using:

```bash
sudo systemctl status ssh
```

The output confirmed that:

* The SSH server was active.
* The service was running correctly.
* The server was listening on port 22.
* The system was ready to receive SSH connections.

**Screenshot Placeholder**

*(Insert screenshot: 01-ssh-status.png)*

---

# Attack Simulation

The brute-force attack was simulated from the Kali Linux machine using Hydra.

The command used was:

```bash
hydra -t 4 -l developer -P passwords.txt ssh://<TARGET_IP>
```

Where:

* **developer** is the target username.
* **passwords.txt** contains multiple password candidates.
* **Hydra** attempts each password against the SSH service.

The attack generated multiple failed authentication attempts that were later recorded inside the authentication log.

**Screenshot Placeholder**

*(Insert screenshot: 03-hydra-attack.png)*

---

# Log Analysis

The authentication log was examined using:

```bash
sudo grep "Failed password" /var/log/auth.log
```

The log entries contained:

* Timestamp
* Hostname
* SSH process ID
* Username
* Source IP address
* Source port
* SSH protocol version

Example log entry:

```
Failed password for developer from 192.168.xxx.xxx port xxxxx ssh2
```

From these entries it was possible to determine:

* The targeted account.
* The attacking IP address.
* The exact time of each login attempt.
* The repeated nature of the attack.

**Screenshot Placeholder**

*(Insert screenshot: 04-failed-password-log.png)*

---

# Analysis Findings

The investigation revealed the following:

* Multiple failed SSH authentication attempts were detected.
* All attempts targeted the same user account.
* The attack originated from a single IP address.
* Authentication attempts occurred within a very short period.
* No successful login was observed during the investigation.

These characteristics are consistent with an automated SSH brute-force attack.

---

# Skills Demonstrated

During this project, the following cybersecurity skills were demonstrated:

* Linux administration
* SSH service verification
* Authentication log analysis
* Linux command-line investigation
* Basic incident investigation
* Hydra attack simulation
* Security event identification
* SOC Level 1 workflow

---

# Recommendations

To reduce the risk of SSH brute-force attacks, the following security controls are recommended:

* Use strong and unique passwords.
* Disable password authentication and use SSH keys.
* Enable Fail2Ban or similar intrusion prevention tools.
* Restrict SSH access using firewall rules.
* Limit login attempts.
* Enable Multi-Factor Authentication (MFA) where possible.
* Continuously monitor authentication logs.

---

# Conclusion

This project successfully demonstrated the detection and investigation of an SSH brute-force attack within a controlled virtual environment. By analyzing Linux authentication logs, it was possible to identify repeated failed login attempts, determine the attack source, and understand the attack behavior. The project reflects common tasks performed by SOC Level 1 analysts during authentication log investigations and highlights the importance of continuous monitoring, log analysis, and proactive security controls to defend Linux systems against unauthorized access attempts.
