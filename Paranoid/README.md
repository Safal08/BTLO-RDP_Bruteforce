**Author:** Safal

**Date:** 2025-11-06

**Tools:** LINUX CLI

Linux SSH Brute Force & Sudoedit Privilege Escalation Incident

Challenge URL: https://blueteamlabs.online/home/challenge/paranoid-e5e164befb

**Incident Summary**

1. Initial Access:

The attacker performed a brute-force attack over SSH and successfully logged in as a valid user.

2. Privilege Escalation:

The attacker ran linpeas.sh to enumerate system vulnerabilities.

Exploited the sudoedit heap overflow (CVE-2021-3156 / Baron Samedit) to escalate privileges to root.

3. Post-Exploitation Actions:

Accessed sensitive files, including /etc/shadow.

Attempted to disable auditing (auditd) to cover tracks.

Deleted or modified local exploit files (e.g., evil binaries).

**The attacker runs**

sudoedit -s "AAAA...\" "\" "BBBB..."

The overly long or specially crafted strings overflow sudoedit’s memory and spawn a root shell.


**Takeways**
1. Analysis of linux audit entry log
2. Use of cut, grep, uniq and sort command to find the necessary artifacts.
