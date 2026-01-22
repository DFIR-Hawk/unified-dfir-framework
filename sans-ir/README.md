# SANS Incident Response Lifecycle
<!-- Incident Response aligned to SANS methodology -->

---

## 1. Scope & Purpose

This section of the Unified DFIR Framework implements the **SANS Incident Response (IR) lifecycle** as a structured and repeatable approach for handling cybersecurity incidents.

The purpose of this module is to:
- Establish a standardized incident handling process
- Enable coordinated response across SOC, DFIR, IT, Cloud, and Management teams
- Reduce attacker dwell time and business impact
- Ensure forensic readiness and evidentiary integrity throughout response

This lifecycle applies to **on-premise, cloud, hybrid, identity-centric, and SaaS environments**.

---

## 2. Process Alignment

### SANS Incident Response Phases

- Preparation  
- Identification  
- Containment  
- Eradication  
- Recovery  
- Lessons Learned  

Each phase is documented individually and should be executed iteratively as incidents evolve.

---

### Digital Forensics Phases (Embedded)

Although IR is operational in nature, forensic discipline is enforced across all phases:

- Identification  
- Preservation  
- Collection  
- Examination  
- Analysis  
- Reporting  

Forensics is treated as an **integral component of incident response**, not a post-incident activity.

---

## 3. Evidence Sources

Depending on the incident type and phase, relevant evidence includes:

- Endpoint logs and artifacts
- Memory captures
- Network traffic and telemetry
- EDR and SIEM data
- Identity and authentication logs
- Cloud audit and control plane logs
- SaaS application logs
- Email and collaboration platform data
- Backup and snapshot metadata
- Threat intelligence indicators

Evidence handling guidance is expanded within each phase document.

---

## 4. Tooling

### Open-Source Tools (not limited to)

#### Preparation & Readiness
- **Atomic Red Team** – Adversary emulation for preparedness testing.
- **CALDERA** – Automated adversary simulation platform.

#### Identification & Triage
- **Sigma** – Generic detection rule format for SIEMs.
- **Zeek** – Network protocol and traffic analysis.
- **YARA** – Pattern-based detection of malware and artifacts.

#### Containment & Response Support
- **Velociraptor** – Endpoint visibility and live response.
- **GRR Rapid Response** – Enterprise live forensics and response.

---

### Commercial / Enterprise Tools (not limited to)

#### EDR / XDR Platforms
- **CrowdStrike Falcon** – Endpoint detection and response.
- **Microsoft Defender** – Endpoint, identity, and cloud telemetry.

#### SIEM / SOAR
- **Splunk** – Log aggregation, correlation, and investigations.
- **Elastic Security** – Detection, hunting, and response workflows.

#### Case Management
- **TheHive** – Incident response case tracking and collaboration.
- **ServiceNow Security Operations** – Enterprise IR orchestration.

---

## 5. Categorization of Tools

Tools referenced in this module support the following functions:

- Incident readiness and simulation
- Detection and alert triage
- Evidence acquisition and live response
- Containment and remediation actions
- Correlation and timeline analysis
- Documentation and reporting
- Post-incident detection improvement

---

## 6. Blogs, Research & References (not limited to)

### Vendor Research
- SANS Internet Storm Center  
  Practical incident handling guidance and threat analysis.
- Microsoft Security Blog  
  Identity, cloud, and endpoint attack insights.

### Independent Research
- The DFIR Report  
  Real-world intrusion timelines and case studies.
- Krebs on Security  
  Incident analysis and attacker ecosystem research.

### Standards & Frameworks
- NIST SP 800-61 – Computer Security Incident Handling Guide
- MITRE ATT&CK – Adversary tactics and techniques framework
- ISO/IEC 27035 – Information security incident management

---

## 7. Practical DFIR Usage

The SANS IR lifecycle is used to:

- Validate and scope security incidents
- Coordinate containment actions
- Guide forensic evidence handling
- Support decision-making during crises
- Enable structured post-incident reviews

### Common Scenarios
- Ransomware and extortion incidents
- Cloud and identity compromise
- Insider threat investigations
- APT intrusions
- Supply chain attacks
- Regulatory and compliance incidents

---

## 8. Common Mistakes & Pitfalls

- Treating IR as a purely technical activity
- Delaying containment due to lack of preparation
- Failing to preserve volatile evidence
- Over-containing and disrupting business unnecessarily
- Incomplete documentation and reporting
- Skipping lessons learned and detection improvements

---

## 9. Output & Reporting

Effective execution of this lifecycle produces:

- Confirmed incident classification
- Defined scope of compromise
- Attack timelines and impact assessment
- Preserved forensic evidence
- Containment and remediation records
- Executive and technical reports
- Detection and control improvement actions

Outputs from each phase directly inform subsequent response and prevention efforts.

---

## Notes

- Always maintain chain-of-custody for evidentiary material
- Coordinate with legal, HR, and communications teams when required
- Ensure compliance with privacy and regulatory obligations
- Assume incidents may escalate or expand during investigation
