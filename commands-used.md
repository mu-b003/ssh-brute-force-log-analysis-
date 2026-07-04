# Commands Used

This document lists the Linux commands used during the SSH brute-force attack simulation and authentication log analysis.

| Command                                                                              | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `ip a`                                                                               | Display network interfaces and identify the target IP address.                       |
| `sudo systemctl status ssh`                                                          | Verify that the SSH service is running and listening for connections.                |
| `touch passwords.txt`                                                                | Create a password wordlist file.                                                     |
| `nano passwords.txt`                                                                 | Edit the password wordlist.                                                          |
| `hydra -t 4 -l developer -P passwords.txt ssh://<TARGET_IP>`                         | Simulate an SSH brute-force attack using Hydra.                                      |
| `sudo grep "Failed password" /var/log/auth.log`                                      | Display failed SSH login attempts from the authentication log.                       |
| `sudo grep "Failed password" /var/log/auth.log \| awk '{print $1, $2, $3, $(NF-3)}'` | Extract the timestamp, process name, and source IP address from failed login events. |

## Summary

The commands above were used to:

* Verify the SSH service.
* Identify the target IP address.
* Create a password wordlist.
* Simulate an SSH brute-force attack.
* Analyze authentication logs.
* Identify failed login attempts and the attack source.

All activities were performed inside a controlled virtual laboratory for educational and defensive cybersecurity purposes.
