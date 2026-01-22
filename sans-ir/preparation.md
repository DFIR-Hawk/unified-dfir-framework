# Preparation
<!-- SANS Incident Response – Expert-Level Preparation Phase -->

---

## 1. Scope & Purpose

The Preparation phase establishes **forensic, technical, and operational readiness** required to investigate security incidents **without delay, evidence loss, or legal exposure**.

At an expert level, preparation is not about owning tools — it is about ensuring:
- The *right evidence exists*
- Investigators can access it immediately
- Actions are legally defensible
- Decisions can be made under pressure

Most failed DFIR engagements fail **before the incident begins**.

---

## 2. What “Prepared” Means (Expert Definition)

An organization is considered **DFIR-prepared** when:

- Logs are enabled, centralized, and retained
- Memory acquisition is possible on demand
- Cloud and identity audit logs are accessible
- IR authority and escalation paths are pre-approved
- Tooling is tested, documented, and available
- Evidence handling is legally defensible

Preparation is a **business capability**, not a SOC checklist.

---

## 3. Minimum vs Mature Preparation (CRITICAL)

### 3.1 Minimum Required (Non-Negotiable)

If these are missing, investigations will fail:

- Endpoint security logs (Windows / Linux)
- Centralized log storage (SIEM or equivalent)
- Cloud audit logs enabled
- Identity authentication logs
- Ability to isolate hosts and accounts
- One validated endpoint triage tool
- One memory acquisition method
- Incident Response Plan approved by leadership

---

### 3.2 Mature SOC / DFIR Capability

These enable deep investigations and faster containment:

- Endpoint telemetry (EDR/XDR)
- Network visibility (Zeek, Suricata, PCAP)
- Cloud workload telemetry
- SaaS audit logs
- Threat intelligence enrichment
- Timeline and correlation tooling
- Automated triage and containment workflows

---

## 4. Evidence & Log Readiness (PRIORITIZED)

### 4.1 Tier 1 – Always Collect First

These logs answer **who, what, when**:

#### Windows
- Security.evtx  
  `C:\Windows\System32\winevt\Logs\Security.evtx`
- Sysmon (if deployed)  
  `Microsoft-Windows-Sysmon/Operational.evtx`
- PowerShell  
  `Microsoft-Windows-PowerShell/Operational.evtx`

#### Linux
- `/var/log/auth.log` or `/var/log/secure`
- `/var/log/audit/audit.log`

#### Identity
- Entra ID / AD Sign-In Logs
- Okta System Logs
- VPN authentication logs

---

### 4.2 Tier 2 – Scope & Impact Analysis

These answer **how far and how bad**:

#### Windows Artifacts
- Prefetch – `C:\Windows\Prefetch\`
- Amcache – `Amcache.hve`
- Shimcache – SYSTEM hive
- SRUM – `SRUDB.dat`
- LNK files

#### Network
- Firewall logs
- DNS logs
- Proxy logs
- VPN logs

---

### 4.3 Tier 3 – Advanced / Deep Forensics

Used for APT, insider, or legal cases:

- Memory images
- Disk images
- PCAPs
- Cloud snapshots
- Email message traces
- SaaS API audit logs

---

## 5. Attack-Type → Evidence Mapping (EXPERT THINKING)

| Incident Type | Primary Evidence |
|---------------|------------------|
| Ransomware | EDR logs, Prefetch, SRUM, memory |
| Identity Abuse | Sign-in logs, token logs, audit logs |
| Cloud Breach | CloudTrail, IAM logs, API calls |
| Insider Threat | File access logs, email, DLP |
| Malware | Memory, execution artifacts, EDR |
| APT | Timeline + memory + network |

This mapping prevents **random evidence collection**.

---

## 6. Tooling – Capability-Based (Not Brand-Based)

> Tools represent **capabilities**.  
> Use equivalents if approved.

---

### 6.1 Endpoint & Live Response (MANDATORY)

- Velociraptor – https://github.com/Velocidex/velociraptor
- GRR – https://github.com/google/grr
- KAPE – https://www.kroll.com/kape
- DFIR-ORC – https://dfir-orc.github.io/
- FastIR – https://github.com/SekoiaLab/Fastir_Collector

Purpose: Immediate triage without waiting for disk images.

---

### 6.2 Memory Acquisition (EXPERT-LEVEL)

- WinPMEM – https://github.com/Velocidex/WinPmem
- LiME – https://github.com/504ensicsLabs/LiME
- AVML – https://github.com/microsoft/avml

Memory is **often the only place** credentials and malware exist.

---

### 6.3 Timeline & Artifact Analysis

- Plaso – https://github.com/log2timeline/plaso
- Timesketch – https://github.com/google/timesketch
- Hayabusa – https://github.com/Yamato-Security/hayabusa
- Chainsaw – https://github.com/countercept/chainsaw
- Eric Zimmerman Tools – https://ericzimmerman.github.io/

---

### 6.4 Network Visibility

- Zeek – https://zeek.org/
- Suricata – https://suricata.io/
- Arkime – https://arkime.com/
- Wireshark – https://www.wireshark.org/

---

## 7. Knowledge Bases (USED BY EXPERTS)

### Curated Repositories
- Awesome Incident Response  
  https://github.com/meirwah/awesome-incident-response
- ForensicsTools  
  https://github.com/mesquidar/ForensicsTools
- DFIR Artifacts  
  https://github.com/teamdfir/artifacts

---

### Research & Case Studies
- The DFIR Report – https://thedfirreport.com/
- SANS DFIR Blog – https://www.sans.org/blog/
- Mandiant Blog – https://www.mandiant.com/resources/blog
- Unit42 – https://unit42.paloaltonetworks.com/

---

## 8. Common Preparation Failures (FIELD EXPERIENCE)

- Logs enabled but not retained
- No memory capture approval
- Cloud logs disabled by default
- Tooling exists but is untested
- No after-hours access
- Legal engaged too late

---

## 9. Output of an Expert-Level Preparation Phase

- Immediate evidence availability
- Faster containment decisions
- Reduced attacker dwell time
- Legally defensible investigations
- Confident executive communication

---

## Final Expert Note

Preparation is not about **having tools**.  
It is about **removing friction when incidents occur**.

If investigators must ask for access, approval, or tools during an incident — preparation has failed.
