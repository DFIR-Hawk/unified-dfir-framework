# Preparation
<!-- SANS Incident Response – Preparation Phase -->

---

## 1. Scope & Purpose

The **Preparation** phase establishes the organizational, technical, and forensic readiness required to respond to security incidents in a timely, controlled, and defensible manner.

This phase ensures that:
- Security incidents can be detected, investigated, and contained rapidly
- Evidence can be preserved in a forensically sound way
- Roles, responsibilities, and escalation paths are predefined
- Legal, regulatory, and business constraints are understood before an incident occurs

Preparation is the **most critical phase** of the incident response lifecycle. Weak preparation almost always results in delayed response, evidence loss, and increased business impact.

---

## 2. Process Alignment

### SANS Incident Response Phases
- Preparation ✅
- Identification
- Containment
- Eradication
- Recovery
- Lessons Learned

---

### Digital Forensics Phases (Applicable)
- Identification
- Preservation
- Collection
- Reporting

The Preparation phase focuses on **forensic readiness**, ensuring evidence sources, tools, and procedures are available when needed.

---

## 3. Preparation Activities

### Organizational Readiness
- Maintain and review the Incident Response Plan (IRP)
- Define incident severity levels and classification criteria
- Establish internal and external escalation workflows
- Define decision authority for containment and shutdown actions
- Maintain updated contact lists (IR, SOC, IT, Legal, HR, PR, Vendors)

### Technical Readiness
- Centralize logging across endpoint, network, cloud, identity, and SaaS
- Ensure log retention meets investigative and regulatory requirements
- Enable time synchronization (NTP) across all systems
- Pre-stage secure evidence storage locations
- Validate EDR, SIEM, and cloud audit logging coverage

### Forensic Readiness
- Define evidence acquisition standards and SOPs
- Pre-test collection scripts and tooling
- Establish chain-of-custody procedures
- Validate investigator access and permissions
- Ensure capability to acquire volatile data (memory, containers, cloud state)

---

## 4. Evidence Sources (Preparation Phase)

Preparation ensures availability and integrity of the following evidence sources:

- Endpoint telemetry and audit logs
- Memory acquisition capability
- Network logs (firewall, proxy, VPN, DNS)
- Identity and authentication logs
- Cloud audit and control plane logs
- SaaS application and API logs
- Email and collaboration platform logs
- Backup, snapshot, and recovery metadata
- Threat intelligence feeds and IOC repositories

---

## 5. Tooling

> The tools referenced below represent commonly used DFIR capabilities for preparation and readiness.  
> This list is **not exhaustive** and is **not limited** to the tools mentioned here.  
> Equivalent or alternative tools may be used based on organizational standards, environment, legal constraints, and investigator preference.

---

### Open-Source Tools

#### Readiness, Validation & Simulation
- **Atomic Red Team** – https://github.com/redcanaryco/atomic-red-team  
  Adversary technique simulations for detection and response validation.
- **MITRE CALDERA** – https://github.com/mitre/caldera  
  Automated adversary emulation for IR readiness testing.

---

#### Endpoint Visibility & Live Response
- **Velociraptor** – https://github.com/Velocidex/velociraptor  
  Endpoint DFIR at scale using VQL.
- **GRR Rapid Response** – https://github.com/google/grr  
  Remote live forensics and response.
- **osquery** – https://github.com/osquery/osquery  
  Endpoint state visibility using SQL-based queries.
- **KAPE** – https://www.kroll.com/en/services/cyber-risk/incident-response-litigation-support/kape  
  Rapid triage and artifact collection.

---

#### Memory & Volatile Data
- **WinPMEM** – https://github.com/Velocidex/WinPmem  
  Windows physical memory acquisition.
- **LiME** – https://github.com/504ensicsLabs/LiME  
  Linux memory acquisition.
- **AVML** – https://github.com/microsoft/avml  
  Linux and cloud memory acquisition.

---

#### Network & Detection Readiness
- **Zeek** – https://zeek.org/  
  Network protocol analysis and monitoring.
- **Suricata** – https://suricata.io/  
  Network threat detection engine.
- **Sigma** – https://github.com/SigmaHQ/sigma  
  Generic SIEM detection rule format.
- **YARA** – https://virustotal.github.io/yara/  
  Pattern-based malware and artifact detection.

---

#### Timeline & Investigation Support
- **Plaso / log2timeline** – https://github.com/log2timeline/plaso  
  Timeline generation across multiple data sources.
- **Timesketch** – https://github.com/google/timesketch  
  Collaborative forensic timeline analysis.

---

### Commercial / Enterprise Tools

#### EDR / XDR
- **CrowdStrike Falcon** – https://www.crowdstrike.com/
- **Microsoft Defender for Endpoint** – https://learn.microsoft.com/defender-endpoint/
- **SentinelOne Singularity** – https://www.sentinelone.com/

---

#### SIEM / SOAR
- **Splunk Enterprise Security** – https://www.splunk.com/
- **Elastic Security** – https://www.elastic.co/security
- **IBM QRadar** – https://www.ibm.com/security/security-intelligence/qradar

---

#### Case Management & Orchestration
- **TheHive** – https://thehive-project.org/
- **ServiceNow Security Operations** – https://www.servicenow.com/products/security-operations.html

---

## 6. Categorization of Tools

Preparation-phase tools support:
- Incident readiness testing
- Detection and logging validation
- Evidence acquisition readiness
- Memory and volatile data capture
- Centralized telemetry
- Case tracking and documentation

---

## 7. Blogs, Research & References

### DFIR & IR Blogs
- https://thedfirreport.com/
- https://thisweekin4n6.com/
- https://dfirdiva.com/
- https://www.sans.org/blog/?focus-area=digital-forensics
- https://www.microsoft.com/security/blog/

---

### Community & Knowledge Bases
- https://aboutdfir.com/
- https://www.dfir.training/
- https://www.forensicfocus.com/
- https://github.com/ForensicArtifacts/artifacts

---

### Standards & Guidelines
- NIST SP 800-61 – https://csrc.nist.gov/publications/detail/sp/800-61/rev-2/final
- ISO/IEC 27035 – https://www.iso.org/standard/44379.html
- ISO/IEC 27037 – https://www.iso.org/standard/44381.html

---

## 8. Practical DFIR Usage

The Preparation phase enables teams to:
- Detect incidents earlier
- Avoid delays caused by access or tooling gaps
- Preserve volatile and cloud-native evidence
- Respond effectively under pressure
- Meet regulatory and legal obligations

### Typical Scenarios
- Ransomware readiness assessments
- Cloud IR preparedness reviews
- Identity compromise readiness
- SOC maturity improvement
- Audit and compliance preparation

---

## 9. Common Mistakes & Pitfalls

- Treating preparation as a one-time activity
- Insufficient log retention
- No tested memory acquisition capability
- Unclear escalation authority
- Missing legal and compliance alignment
- Lack of readiness during off-hours incidents

---

## 10. Output & Reporting

Effective preparation results in:
- A tested Incident Response Plan
- Verified logging and telemetry coverage
- Ready-to-use evidence collection tooling
- Clear escalation and communication paths
- Faster and more accurate incident identification
- Reduced response friction

---

## Notes

- Preparation must be reviewed and tested regularly
- Conduct tabletop and adversary simulation exercises
- Update tooling as environments evolve
- Assume incidents will occur outside business hours
- Preparation gaps are usually exposed during real incidents
