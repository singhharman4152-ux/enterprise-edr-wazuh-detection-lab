# Enterprise EDR & SIEM Deployment with Wazuh and Windows 11

- **Security Analyst:** Harmandeep Singh
- **Focus Area:** Endpoint Detection & Response (EDR), SIEM Telemetry, Vulnerability Management (VMDR)
- **Target Roles:** Tier-1 SOC Analyst | Vulnerability Management Analyst | Cyber Security Specialist

## 1. Executive Summary
Deployed an on-premises, enterprise-grade Security Information and Event Management (SIEM) and Endpoint Detection & Response (EDR) platform utilizing Wazuh 4.14 inside a virtualized hypervisor environment (Bridged networking). Enrolled a production Windows 11 endpoint agent to stream live encrypted telemetry over port 1514. Conducted automated host vulnerability assessments against the National Vulnerability Database (NVD), audited endpoint configuration against CIS Benchmarks, and mapped suspicious events to the MITRE ATT&CK matrix.

## 2. Lab Architecture & Telemetry Pipeline

```text
  [ Monitored Host: Windows 11 ] ──(Encrypted Agent Port 1514)──> [ Wazuh SIEM Server: Ubuntu / OVA ]
   • Host: Harmandeep-Win11 (192.168.43.64)                        • IP: 192.168.43.217 (Bridged)
   • Windows Security Logs & Sysmon                               • Wazuh Indexer & Analysis Engine
   • Installed Software Inventory                                 • MITRE ATT&CK Correlation
                                                                               │
                                                                               ▼
                                                                [ Wazuh Web SOC Dashboard ]
                                                                 • Live Threat Hunting Console
                                                                 • Vulnerability Prioritization
                                                                 • CIS Hardening Benchmarks

## 3. Real Telemetry & Key Findings

### Automated Vulnerability Management (VMDR Integration)
- Evaluated the host package ecosystem against known Common Vulnerabilities and Exposures (CVEs).
- **Findings:**
  - **6 Critical**, **81 High**, **55 Medium**, and **9 Low** severity vulnerabilities identified.
  - Primary vulnerable packages identified: `GitPython` (30 CVEs), `aiohttp` (24 CVEs), `pillow` (19 CVEs), `torch` (13 CVEs), and `Python 3.12.9`.
- **SOC Action:** Prioritized patch cycles for high-exploitability packages based on TruRisk and CVSS scores, staging package updates to remediate known remote code execution (RCE) vectors.

### Security Configuration Assessment (CIS Benchmark Audit)
- Audited Windows 11 host against **CIS Microsoft Windows 11 Enterprise Benchmark v3.0.0**.
- **Results:** 122 rules passed, 351 recommendations failed (Compliance Score: 25%).
- **Remediation Plan:** Hardened local security policies, enforced account lockout thresholds, disabled insecure legacy protocols (LLMNR, NetBIOS), and enabled UAC maximum elevation prompts.

### MITRE ATT&CK & Compliance Mapping
- Actively classified endpoint events against the **MITRE ATT&CK framework**, flagging anomalous activity under the **Defense Evasion** tactic.
- Continuous regulatory mapping against **PCI DSS** standards (Sections 2.2, 10.6.1, and 10.2.6) for audit preparedness.

## 4. Skills Demonstrated
- Hypervisor Networking (VirtualBox Bridged Mode, IPv4 Addressing)
- Wazuh SIEM & EDR Deployment, Agent Enrollment via PowerShell
- Vulnerability Assessment, CVE Identification, and Patch Prioritization
- CIS Benchmark Auditing and Windows OS Hardening
- MITRE ATT&CK Tactic Mapping & SOC Alert Triage
