# Identification Phase – Digital Forensics

## Purpose

The Identification phase determines **what evidence exists, where it resides, and what must be preserved first** to support a defensible forensic investigation.

This phase is **decision-critical**. Errors made during identification commonly result in:
- Loss of volatile or short-retention evidence
- Incomplete incident scoping
- Legal and regulatory exposure
- Irrecoverable investigative gaps

Identification always precedes evidence collection and often occurs while the incident is still active.

---

## When Identification Is Triggered

Identification begins when:

- A SOC alert is escalated beyond routine triage
- Incident Response confirms a suspected compromise
- Ransomware, insider activity, or data exposure is suspected
- Legal, HR, or Compliance requests forensic validation
- Cloud, identity, or SaaS abuse is suspected
- Regulatory or law-enforcement involvement is possible

> **Assume litigation from the first minute.**

---

## Core Objectives

The Identification phase answers four fundamental questions:

1. **What systems, identities, and data may be impacted?**
2. **Which evidence sources are relevant and time-sensitive?**
3. **What evidence must be preserved immediately?**
4. **What investigative hypotheses guide next actions?**

---

## Practical Identification Workflow (Real-World)

### 1. Establish Investigation Context

Before interacting with systems, determine:
- Incident type (ransomware, BEC, insider threat, APT, cloud abuse)
- Detection source (EDR, SIEM, IAM, user report)
- Business criticality and operational impact
- Legal, privacy, and regulatory sensitivity

This context drives **evidence prioritization and scope control**.

---

### 2. Identify Evidence Domains

#### Endpoint Evidence
- Disk artifacts (NTFS, EXT4, APFS)
- Volatile memory (RAM)
- EDR telemetry
- Local event logs and execution artifacts

#### Identity Evidence
- Authentication and sign-in logs
- OAuth consent and token activity
- MFA events and bypass attempts
- Privileged account usage

#### Network Evidence
- Firewall and proxy logs
- VPN authentication logs
- DNS and DHCP logs
- Packet capture data (if available)

#### Cloud & SaaS Evidence
- Control plane audit logs
- API activity
- Object storage access logs
- Email and collaboration audit logs

#### Backup & DR Evidence
- Backup deletion or modification attempts
- Snapshot tampering
- Restore point integrity

---

### 3. Apply Order of Volatility (OV)

1. CPU registers and running processes  
2. Memory (RAM)  
3. Network connections  
4. Temporary files  
5. Disk data  
6. Backups and archives  

---

### 4. Hypothesis-Driven Identification

Expert investigators form **initial hypotheses**, such as:
- Credential theft → lateral movement
- OAuth abuse without endpoint malware
- Insider staging prior to exfiltration
- Ransomware via unmanaged endpoint

Evidence identification aligns to **proving or disproving these hypotheses**.

---

## Evidence Identification Checklist

- Suspected infected endpoints
- Privileged/admin workstations
- Jump servers and bastion hosts
- Compromised user and service accounts
- Cloud roles, tokens, and API keys
- Identity providers and email platforms

---

## Tools Used During Identification

### Endpoint & Live Evidence Identification

**Open Source**
- Velociraptor – https://github.com/Velocidex/velociraptor  
- GRR Rapid Response – https://github.com/google/grr  
- osquery – https://osquery.io  
- FleetDM – https://github.com/fleetdm/fleet  
- DFIR ORC – https://dfir-orc.github.io  
- KAPE – https://www.kroll.com/en/services/cyber-risk/incident-response-litigation-support/kape  
- Eric Zimmerman Toolset – https://ericzimmerman.github.io  

---

### Memory & Volatile Evidence Identification

**Open Source**
- Volatility 3 – https://github.com/volatilityfoundation/volatility3  
- Rekall – http://www.rekall-forensic.com  
- MemProcFS – https://github.com/ufrisk/MemProcFS  

**Commercial**
- Magnet RAM Capture / AXIOM – https://www.magnetforensics.com  
- Belkasoft RAM Capturer – https://belkasoft.com/ram-capturer  

---

### Network & Log Evidence Identification

- Plaso / log2timeline – https://github.com/log2timeline/plaso  
- Timesketch – https://github.com/google/timesketch  
- Wireshark – https://www.wireshark.org  
- NetworkMiner – https://www.netresec.com/?page=NetworkMiner  

---

### Cloud & SaaS Evidence Identification

**Open Source**
- ScoutSuite – https://github.com/nccgroup/ScoutSuite  
- Prowler – https://github.com/prowler-cloud/prowler  
- Turbinia – https://github.com/google/turbinia  

**Platform-Native Sources**
- AWS CloudTrail / GuardDuty
- Microsoft Entra ID, Purview, Unified Audit Logs
- Google Workspace Audit Logs
- SaaS provider security audit logs

---

### Identity & Authentication Evidence Sources

- Entra ID / Azure AD sign-in logs
- Okta system logs
- AD Security events (4624, 4769, 4776)
- MFA provider logs
- OAuth consent, token issuance, and refresh logs

---

### Mobile & Device Forensics (Identification Context)

These tools are commonly used **to identify scope and available evidence**, especially in:
- Insider investigations
- Corporate mobile misuse
- Law-enforcement-assisted cases

**Commercial Platforms**
- Cellebrite UFED – https://www.cellebrite.com  
- Oxygen Forensic Detective – https://www.oxygen-forensic.com  
- Magnet AXIOM Mobile – https://www.magnetforensics.com  
- Belkasoft Evidence Center – https://belkasoft.com  

---

## Common Identification Failures

- Collecting before preservation decisions
- Ignoring identity and SaaS logs
- Over-collecting without hypotheses
- Missing short-retention cloud evidence
- Late legal engagement

---

## Outputs of the Identification Phase

- Defined systems, identities, and data in scope
- Prioritized volatile vs persistent evidence
- Evidence acquisition plan
- Documented hypotheses and assumptions
- Logged investigator actions and access

---

## Authoritative Blogs & Research (Expert-Level)

### Core DFIR Practitioner Blogs
- AboutDFIR – https://aboutdfir.com  
- DFIR.blog – https://dfir.blog  
- The DFIR Report – https://thedfirreport.com  
- This Week in 4n6 – https://thisweekin4n6.wordpress.com  
- SANS Digital Forensics Blog – https://www.sans.org/blog/?focus-area=digital-forensics  
- Forensic Focus – https://www.forensicfocus.com  

### Research & Threat Investigation
- Mandiant Blog – https://www.mandiant.com/resources/blog  
- CrowdStrike Blog – https://www.crowdstrike.com/blog  
- Elastic Security Labs – https://www.elastic.co/security-labs  
- NCC Group Research – https://research.nccgroup.com  
- Trail of Bits – https://blog.trailofbits.com  

### Artifact & Evidence Research
- ForensicArtifacts – https://github.com/ForensicArtifacts/artifacts  
- DFIR Artifact Knowledge Base – https://github.com/ForensicArtifacts/artifacts-kb  
- Windows Event Log Attack Samples – https://github.com/sbousseaden/EVTX-ATTACK-SAMPLES  

---

## Recommended Books

- *Incident Response & Computer Forensics* – Mandia, Prosise  
- *The Art of Memory Forensics* – Ligh et al.  
- *Practical Memory Forensics* – Ostrovskaya & Skulkin  
- *Intelligence-Driven Incident Response* – Roberts & Brown  
- *The Practice of Network Security Monitoring* – Bejtlich  

---

## Key Takeaway

Identification is **not tool execution**.  
It is **analytical decision-making under uncertainty**.

Strong identification preserves truth, reduces scope errors,
and separates **experienced DFIR professionals from tool operators**.
