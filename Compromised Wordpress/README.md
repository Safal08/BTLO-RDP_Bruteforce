**Author:** Safal

**Date:** 2025-11-07

**Tools:** LINUX CLI, use of grep, cut, uniq and sort command

Vulnerability to wordpress

The attacker used enumeration tools and multiple IPs, attempted SQLi/XSS and command execution payloads, abused an iThemes “hide backend” token to reach wp-login.php, exploited a vulnerable plugin (Simple File List) for arbitrary file upload, and ultimately uploaded a webshell to achieve a reverse TCP shell.

Challenge URL: https://blueteamlabs.online/home/challenge/log-analysis-compromised-wordpress-ce000f5b59

**Incident Summary**

Reconnaissance: Enumeration of the website using tools like WPScan.

Access Attempt: Login through wp-login.php using an admin token.

Exploitation: Code injection to extract system and user data.

Privilege Escalation: Exploiting the Simple File List plugin to upload arbitrary files.

Post-Exploitation: Uploading and executing a webshell for remote access.
