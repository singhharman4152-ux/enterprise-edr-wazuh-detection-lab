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
