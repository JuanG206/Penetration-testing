# Penetration Test on Metasploitable using Kali Linux

## Overview
This repository contains documentation and artifacts from a penetration test performed on a **Metasploitable** virtual machine using **Kali Linux**. The purpose of this project is to demonstrate penetration testing techniques, vulnerability exploitation, and privilege escalation.

## Objectives
- Identify open ports and running services using **Nmap**.
- Discover vulnerabilities in exposed services.
- Exploit a vulnerable **Apache 2.2.8** service running on **port 80**.
- Escalate privileges from an unprivileged user to **root**.
- Document findings and security best practices.

## Environment Setup
- **Virtual Machines:**
  - **Kali Linux (Attacker)** – `192.168.56.101` (example IP)
  - **Metasploitable (Target)** – `192.168.56.102` (example IP)
- **Virtualization Software:** GNOME Boxes
- **Network Configuration:** Bridge network (VMs could communicate but were isolated from the host machine)

## Tools Used
- **Nmap** – Port scanning and service enumeration
- **Metasploit Framework** – Exploitation and privilege escalation
- **Searchsploit** – Identifying known vulnerabilities
- **Linpeas** – Privilege escalation analysis

## Project Files
- **Report.md** – Detailed penetration testing report
- **scan_results.txt** – Nmap scan output
- **exploit_script.rc** – Automated Metasploit script
- **privilege_escalation_findings.txt** – Linpeas output for privilege escalation
- **/screenshots/** – Folder containing proof of exploitation (add manually)
- **references.txt** – List of tools, documentation, and resources

## Disclaimer
This project is for **educational purposes only**. It was conducted in a controlled environment, and the techniques demonstrated should never be used without proper authorization.

## Author
Juan Gerardo Carvajal Corpus


