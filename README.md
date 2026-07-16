
<!-- PROJECT SHIELD -->
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][in/shivamkumar-dce-cybersecurity]

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/your-username/SOC-Lab-with-Wazuh">
    <img src="images/logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">🛡️ Enterprise SOC Lab — Powered by Wazuh SIEM</h3>

  <p align="center">
    A complete Security Operations Center lab for threat detection, intelligence enrichment, and automated response.
   
  </p>
</div>

---

## 📑 Table of Contents

- [Project Overview](#-project-overview)
- [Project Objectives](#-project-objectives)
- [SOC Architecture](#-soc-architecture)
- [Technology Stack](#-technology-stack)
- [Repository Structure](#-repository-structure)
- [Detection Modules](#-detection-modules)
- [Project Workflow](#-project-workflow)
- [Documentation](#-documentation)
- [Skills Demonstrated](#-skills-demonstrated)
- [Future Enhancements](#-future-enhancements)
- [Disclaimer](#-disclaimer)
- [Author](#-author)

---

## 📖 Project Overview

This project demonstrates the design and implementation of a **fully functional Security Operations Center (SOC) laboratory**, using **Wazuh** as the centralized SIEM (Security Information and Event Management) platform.

The goal was to build an end-to-end SOC capable of continuous endpoint monitoring, cyber threat detection, security event correlation, threat intelligence enrichment, and automated incident response — all orchestrated through **n8n** as a lightweight SOAR (Security Orchestration, Automation and Response) engine.

Multiple open-source security technologies were integrated into a single, cohesive lab environment, offering hands-on experience in detection engineering, log analysis, incident response, and security automation.

---

## 🎯 Project Objectives

- Deploy an enterprise-grade SIEM using Wazuh (Manager + Agent architecture)
- Monitor endpoint activity on a Linux host (Ubuntu Agent)
- Detect file integrity violations (FIM – File Integrity Monitoring)
- Detect network-based intrusions using Suricata IDS
- Identify malicious command executions via Auditd
- Detect SSH brute‑force attacks and trigger active response
- Integrate VirusTotal threat intelligence for hash and IP enrichment
- Detect phishing indicators from email headers and URLs
- Automate alert processing, enrichment, and notification using n8n SOAR
- Deliver enriched, actionable alerts directly to a Telegram channel

---

## 🏗️ SOC Architecture

```
                    ┌──────────────────────────────┐
                    │       Ubuntu Agent           │
                    │   (Monitored Endpoint)       │
                    └──────────────┬───────────────┘
                                   │
                            Wazuh Agent
                                   │
                                   ▼
                    ┌──────────────────────────────┐
                    │       Wazuh Manager          │
                    └──────────────┬───────────────┘
                                   │
        ┌──────────────────────────┼──────────────────────────┐
        │                          │                          │
        ▼                          ▼                          ▼
 File Integrity             Suricata IDS             Auditd Monitoring
 Monitoring

        ▼                          ▼                          ▼

 Vulnerability Detection    SSH Detection          Phishing Detection

                                   │
                                   ▼
                       VirusTotal Threat Intelligence

                                   │
                                   ▼
                             n8n SOAR Automation

                                   │
                                   ▼
                           Telegram Alert Notification
```

---

## ⚙️ Technology Stack

| Category               | Technologies                                   |
|------------------------|------------------------------------------------|
| SIEM                   | Wazuh (Manager + Agent)                        |
| Operating System       | Ubuntu Server 22.04.5 LTS                      |
| Monitored Endpoint     | Ubuntu (Wazuh Agent)                           |
| Intrusion Detection    | Suricata                                       |
| Command Auditing       | Auditd                                         |
| Threat Intelligence    | VirusTotal API                                 |
| SOAR / Automation      | n8n (Docker deployment)                        |
| Container Runtime      | Docker, Docker Compose                         |
| Notifications          | Telegram Bot API                               |
| Virtualization / Host  | WSL 2 (Windows Subsystem for Linux)            |

---

## 📂 Repository Structure

```
SOC-Lab-with-Wazuh
│
├── Setup
│   └── SOC-Lab-Setup.docx
│
├── Attacks
│   ├── 01-File-Integrity-Monitoring.docx
│   ├── 02-Network-Intrusion-Detection.docx
│   ├── 03-Vulnerability-Detection.docx
│   ├── 04-Malicious-Command-Detection.docx
│   ├── 05-SSH-Brute-Force-Detection.docx
│   ├── 06-VirusTotal-Integration.docx
│   └── 07-Phishing-Mail-Detection.docx
│
├── Automation
│   └── n8n-SOAR-Automation.docx
│
└── README.md
```

---

## 🚨 Detection Modules

| Module                                       | Status |
|----------------------------------------------|:------:|
| SOC Infrastructure Setup                     | ✅     |
| File Integrity Monitoring (FIM)              | ✅     |
| Network Intrusion Detection (Suricata)       | ✅     |
| Vulnerability Detection                      | ✅     |
| Malicious Command Detection (Auditd)         | ✅     |
| SSH Brute‑Force Detection & Active Response  | ✅     |
| VirusTotal Threat Intelligence Integration   | ✅     |
| Phishing Mail Detection                      | ✅     |
| n8n SOAR Automation & Telegram Alerting      | ✅     |

---

## 🔄 Project Workflow

SOC Infrastructure Setup
            │
            ▼
File Integrity Monitoring
            │
            ▼
Network Intrusion Detection (Suricata)
            │
            ▼
Vulnerability Detection
            │
            ▼
Malicious Command Detection (Auditd)
            │
            ▼
SSH Brute‑Force Detection & Active Response
            │
            ▼
VirusTotal Threat Intelligence Integration
            │
            ▼
Phishing Mail Detection
            │
            ▼
n8n SOAR Automation & Telegram Notification

---

## 📚 Documentation

All detailed implementation guides are available in the corresponding `.docx` files within the repository. Below is a quick overview.

### 🏗️ Setup
- **SOC Lab Infrastructure Setup** – Step-by-step deployment of Wazuh Manager, Agent, Suricata, Auditd, and n8n.

### 🛡️ Detection Modules
- **File Integrity Monitoring** – Detecting unauthorized changes to critical files and directories.
- **Network Intrusion Detection** – Analyzing network traffic for malicious patterns with Suricata.
- **Vulnerability Detection** – Identifying known vulnerabilities on the monitored endpoint.
- **Malicious Command Detection** – Capturing and alerting on suspicious shell commands using Auditd.
- **SSH Brute‑Force Detection** – Real‑time detection of brute‑force login attempts with automatic IP blocking.
- **VirusTotal Integration** – Enriching file hashes and IPs with external threat intelligence.
- **Phishing Mail Detection** – Spotting phishing indicators in email headers, domains, and URLs.

### 🤖 Automation
- **n8n SOAR Integration** – Automating alert parsing, enrichment, and delivery.
- **VirusTotal Enrichment** – Automatically querying VirusTotal for indicators found in alerts.
- **Telegram Alerting** – Sending enriched, human-readable alerts to a Telegram channel.

**Each document includes:**
- Architecture and objective
- Detailed configuration
- Commands used
- Detection logic and rule description
- Screenshots
- Proof of concept (attack simulation)
- SOC analyst interpretation
- Troubleshooting tips
- Conclusion

---

## 💡 Security Capabilities Demonstrated

- Enterprise SIEM deployment (Wazuh)
- Continuous endpoint monitoring (Linux)
- File integrity monitoring (FIM)
- Network intrusion detection (Suricata)
- Vulnerability assessment
- Log analysis and correlation
- Threat intelligence enrichment (VirusTotal)
- Incident response and active response actions
- Detection engineering (custom Wazuh rules & decoders)
- Security automation and orchestration (n8n SOAR)

---

## 🛠 Skills Demonstrated

- Security Operations Center (SOC) design & implementation
- Wazuh SIEM administration & rule customization
- Detection engineering (MITRE ATT&CK mapping)
- Linux system administration and hardening
- Threat hunting and incident response
- Threat intelligence integration and enrichment
- Containerization with Docker
- Network security monitoring
- SOAR automation (n8n workflow design)
- MITRE ATT&CK framework application

---

## 📈 Future Enhancements

- Integration with Microsoft Defender for Endpoint
- Multi-channel notifications (Slack, Microsoft Teams)
- Case management with TheHive
- Extended threat intelligence via MISP
- Support for Sigma rules and YARA scans
- AI-driven alert prioritization and noise reduction
- Automated incident ticket creation (Jira, ServiceNow)
- Dashboarding and reporting with Grafana

---

## ⚠️ Disclaimer

This project was built **exclusively for educational and research purposes** within a **fully isolated lab environment**.  
All attack simulations were executed only on systems that I own and control.  
No production infrastructure, third-party services, or unauthorized systems were targeted.  
Sensitive credentials (API keys, passwords, tokens) have been either removed or replaced with placeholders prior to publication.

---

## 👤 Author

**Shivam Kumar**  
[![LinkedIn][linkedin-shield]][in/shivamkumar-dce-cybersecurity]  
[![GitHub][github-shield]][https://github.com/iamkrshivam]

---

⭐ If you found this project useful, consider giving it a star!

<!-- MARKDOWN LINKS & IMAGES -->
[license-shield]: https://img.shields.io/github/license/your-username/SOC-Lab-with-Wazuh.svg?style=for-the-badge
[license-url]: https://github.com/your-username/SOC-Lab-with-Wazuh/blob/main/LICENSE
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/your-profile
[github-shield]: https://img.shields.io/badge/-GitHub-black.svg?style=for-the-badge&logo=github&colorB=555
[github-url]: https://github.com/your-username
```
