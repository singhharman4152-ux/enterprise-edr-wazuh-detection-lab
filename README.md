---

## 3. Real Telemetry & Key Findings

### 1. Automated Vulnerability Management (VMDR Integration)
- Evaluated the host package ecosystem against known Common Vulnerabilities and Exposures (CVEs).
- **Findings:**
  - **6 Critical**, **81 High**, **55 Medium**, and **9 Low** severity vulnerabilities identified.
  - Primary vulnerable packages identified: `GitPython` (30 CVEs), `aiohttp` (24 CVEs), `pillow` (19 CVEs), `torch` (13 CVEs), and `Python 3.12.9`.
- **SOC Action:** Prioritized patch cycles for high-exploitability packages based on TruRisk and CVSS scores, staging package updates to remediate known remote code execution (RCE) vectors.

### 2. Security Configuration Assessment (CIS Benchmark Audit)
- Audited Windows 11 host against **CIS Microsoft Windows 11 Enterprise Benchmark v3.0.0**.
- **Results:** 122 rules passed, 351 recommendations failed (Compliance Score: 25%).
- **Remediation Plan:** Hardened local security policies, enforced account lockout thresholds, disabled insecure legacy protocols (LLMNR, NetBIOS), and enabled UAC maximum elevation prompts.

### 3. MITRE ATT&CK & Compliance Mapping
- Actively classified endpoint events against the **MITRE ATT&CK framework**, flagging anomalous activity under the **Defense Evasion** tactic.
- Continuous regulatory mapping against **PCI DSS** standards (Sections 2.2, 10.6.1, and 10.2.6) for audit preparedness.

---

## 4. Skills Demonstrated
- Hypervisor Networking (VirtualBox Bridged Mode, IPv4 Addressing)
- Wazuh SIEM & EDR Deployment, Agent Enrollment via PowerShell
- Vulnerability Assessment, CVE Identification, and Patch Prioritization
- CIS Benchmark Auditing and Windows OS Hardening
- MITRE ATT&CK Tactic Mapping & SOC Alert Triage
