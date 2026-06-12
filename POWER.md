---
name: "cybersecurity-skills"
displayName: "CyberSecurity Skills"
description: "Expert methodology for offensive and defensive security: recon/OSINT, vulnerability assessment, exploit dev, reverse engineering, malware analysis, threat hunting, incident response, network/web/cloud security, SOC automation, log/SIEM analysis, cryptography, red team, and blue team hardening."
keywords: ["security", "cybersecurity", "infosec", "pentest", "pentesting", "recon", "osint", "subdomain", "vulnerability", "cve", "cvss", "exploit", "payload", "poc", "reverse-engineering", "binary", "disassembly", "malware", "yara", "threat-hunting", "ioc", "mitre", "att&ck", "incident-response", "forensics", "dfir", "pcap", "network-security", "ids", "ips", "suricata", "snort", "owasp", "xss", "sqli", "web-security", "api-security", "cloud-security", "aws", "azure", "gcp", "kubernetes", "docker", "iac", "soc", "csoc", "siem", "splunk", "sentinel", "sigma", "log-analysis", "tls", "ssl", "cryptography", "red-team", "c2", "blue-team", "hardening", "cis", "detection-engineering"]
author: "Adapted for Kiro from Masriyan/Claude-Code-CyberSecurity-Skill (MIT)"
---

# CyberSecurity Skills

A collection of 15 security workflows covering the full offensive-to-defensive spectrum.
Each domain has a dedicated steering file with methodology, ready-to-run commands, output
templates, and detection/hardening references. Adapted for Kiro from the
[Claude-Code-CyberSecurity-Skill](https://github.com/Masriyan/Claude-Code-CyberSecurity-Skill)
project (MIT License).

> **Authorization & ethics**: These workflows are for authorized security testing, research,
> CTF, and education only. The offensive workflows (`03-exploit-development`, `14-red-team-ops`)
> contain explicit authorization gates — confirm written scope/permission before assisting.
> Decline and explain when authorization is absent. The user is responsible for legal compliance.

# Onboarding

## Step 1: Optional tooling
The workflows are usable as pure guidance. For the bundled Python automation helpers in
`scripts/<domain>/`, ensure Python 3.10+ is available:
- Verify with: `python --version` (or `python3 --version`)
- Each domain lists its own `pip install ...` prerequisites at the top of its steering file.

## Step 2: Optional external tools
Some workflows are enhanced by external tools (install only what you need):
- `nmap`, `amass`, `theHarvester` (recon/network)
- `Ghidra` / `IDA Free`, `capstone`, `pwntools` (reverse engineering / exploit dev)
- `YARA`, `Volatility 3` (malware / forensics)
- `tshark` / `Wireshark`, `Suricata` / `Snort` (network)
- `Trivy`, `Checkov` / `tfsec` (cloud / IaC)
- `sigma-cli` (detection rule conversion)

# When to Load Steering Files

Load the steering file that matches the user's task:

- Reconnaissance, OSINT, subdomain enumeration, DNS analysis, tech fingerprinting → `01-recon-osint.md`
- Dependency/CVE auditing, config review, CVSS scoring, vulnerability reports → `02-vulnerability-scanner.md`
- PoC development, payload crafting, shellcode, exploitation research (authorized) → `03-exploit-development.md`
- Binary analysis, assembly interpretation, disassembly, firmware/protocol RE, CTF → `04-reverse-engineering.md`
- Static/dynamic malware analysis, YARA rules, sandboxing, IOC extraction → `05-malware-analysis.md`
- IOC correlation, MITRE ATT&CK mapping, hunt hypotheses, Sigma/SIEM hunting → `06-threat-hunting.md`
- Incident response playbooks, evidence collection, forensic timelines, memory forensics → `07-incident-response.md`
- PCAP analysis, IDS/IPS (Suricata/Snort) rules, firewall auditing, beaconing detection → `08-network-security.md`
- OWASP Top 10, injection/XSS/SSRF testing, API & JWT security, security headers → `09-web-security.md`
- AWS/Azure/GCP auditing, Docker/Kubernetes hardening, IaC scanning, cloud compliance → `10-cloud-security.md`
- SOC alert triage, playbook automation, escalation workflows, shift reports, KPIs → `11-csoc-automation.md`
- Log parsing, anomaly detection, SIEM queries (Splunk/KQL/EQL), Sigma, correlation → `12-log-analysis.md`
- TLS/SSL auditing, cipher/hash analysis, crypto code review, PQC guidance → `13-crypto-analysis.md`
- Red team engagement planning, C2 design, lateral movement, OPSEC, reporting (authorized) → `14-red-team-ops.md`
- System hardening (Linux/Windows), detection engineering, baselines, patch mgmt, CIS → `15-blue-team-defense.md`

# Notes

- Bundled automation scripts live under `scripts/<domain>/scripts/` and example walkthroughs under
  `scripts/<domain>/examples/`. Run them only against systems you are authorized to test.
- Steering files cross-reference each other by domain number (e.g., "→ Skill 09") to chain
  workflows (recon → vuln scan → web testing → reporting).
