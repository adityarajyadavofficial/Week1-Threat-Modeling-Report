# Virtual Threat Modeling and Vulnerability Assessment

**Week 1 Task – Cybersecurity Internship (YuvaIntern)**
**Author:** Aditya Raj

## Overview
This project simulates a threat modeling and vulnerability assessment exercise on an isolated virtual lab network. A Kali Linux machine was used to assess a deliberately vulnerable Metasploitable 2 server hosting DVWA and other insecure services.

## Lab Setup
| Component | Details |
|---|---|
| Hypervisor | Oracle VirtualBox (host-only network, 192.168.56.0/24) |
| Attacker | Kali Linux – 192.168.56.101 |
| Target | Metasploitable 2 – 192.168.56.102 |

![Lab Architecture](images/fig1.png)

## Methodology
1. Scope definition and lab setup
2. Reconnaissance (Nmap)
3. Threat modeling using **STRIDE** on a data flow diagram
4. Vulnerability scanning (Nmap NSE, Nikto, OpenVAS, enum4linux)
5. Manual verification
6. Risk scoring (Likelihood × Impact, 5×5 matrix)
7. Prioritised mitigation plan

![Methodology](images/fig3.png)

## Key Findings
| Rating | Count |
|---|---|
| Critical | 5 |
| High | 3 |
| Medium | 4 |

Major issues: vsftpd 2.3.4 backdoor, UnrealIRCd backdoor, Samba usermap_script injection, open root bind shell (port 1524), PHP-CGI argument injection, default credentials, and MySQL root without password.

![Risk Heat Map](images/fig4.png)

![STRIDE Data Flow Diagram](images/fig2.png)

## Tools Used
Nmap, Nikto, OpenVAS/Greenbone, enum4linux, Metasploit (proof-of-concept only), Burp Suite

## Report
- 📄 [View report (PDF)](Week1_Threat_Modeling_Report_Aditya_Raj.pdf) – opens directly in the browser
- 📝 [Download report (DOCX)](Week1_Threat_Modeling_Report_Aditya_Raj.docx)

## Repository Structure
```
├── README.md
├── Week1_Threat_Modeling_Report_Aditya_Raj.pdf
├── Week1_Threat_Modeling_Report_Aditya_Raj.docx
└── images/   (diagrams and charts)
```

## Disclaimer
All testing was performed only on intentionally vulnerable virtual machines in an isolated network, for educational purposes.
