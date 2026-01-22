# Analysis Phase – Digital Forensics

## Purpose

The Analysis phase involves **interpreting examined forensic artifacts to reconstruct events,
determine scope and impact, and answer investigative questions** in a **defensible,
evidence-backed manner**.

Analysis is **not speculation** and **not tool output interpretation**.
It is the disciplined process of **correlating validated artifacts to establish facts**.

Failures during analysis commonly result in:
- Incorrect conclusions
- Scope underestimation or inflation
- False attribution
- Loss of executive, legal, or regulatory trust

Analysis begins **only after Examination is complete**.

---

## When Analysis Is Triggered

Analysis begins when:

- Artifacts are extracted and validated
- Timelines are prepared
- Evidence integrity is confirmed
- Investigation questions are defined
- Legal and reporting expectations are known

> **If artifacts are incomplete or integrity is uncertain, analysis must pause.**

---

## Core Objectives

The Analysis phase answers five critical questions:

1. **What happened?**
2. **When did it happen?**
3. **How did it happen?**
4. **What systems, identities, and data were impacted?**
5. **What is known, unknown, and unprovable?**

---

## Analysis Principles (Expert-Level)

### Evidence Over Assumptions
No conclusion is made without **corroborated artifacts from multiple sources**.

### Correlation Before Attribution
Determine *what occurred* before claiming *who was responsible*.

### Negative Evidence Matters
Absence of expected artifacts may indicate:
- Log deletion
- Anti-forensics
- Collection gaps

### Confidence Levels Are Mandatory
Each finding must state **High / Medium / Low confidence**.

---

## Practical Analysis Workflow

### 1. Define Investigation Questions

Analysis must be question-driven, not data-driven.

Examples:
- What was the initial access vector?
- Was lateral movement successful?
- Were credentials or tokens abused?
- Was data accessed, staged, or exfiltrated?
- Is persistence present?

---

### 2. Correlate Artifacts Across Evidence Sources

Correlation must span:
- Disk artifacts
- Memory artifacts
- Event and application logs
- Identity and authentication logs
- Network telemetry
- Cloud and SaaS audit logs

Single-source conclusions are **weak and legally risky**.

---

### 3. Timeline-Based Reconstruction

Timelines are the backbone of forensic analysis.

They are used to:
- Reconstruct attacker activity
- Identify dwell time
- Spot gaps and blind spots
- Validate or disprove hypotheses

Each timeline event should include:
- Timestamp (with timezone)
- Source artifact
- System or identity
- Confidence level

---

### 4. Scope & Impact Determination

#### Scope
- Affected systems
- Compromised identities
- Privilege escalation paths
- Persistence mechanisms

#### Impact
- Data accessed, modified, or exfiltrated
- Business and operational impact
- Regulatory exposure
- Recovery and containment implications

---

### 5. TTP Mapping & Behavioral Validation

Observed behavior should be mapped to:
- MITRE ATT&CK techniques
- Known ransomware playbooks
- Insider threat patterns
- Cloud-native abuse patterns

This improves:
- Attribution confidence
- Detection gap identification
- Defensive improvement planning

---

## Analysis by Investigation Type

### Malware / Ransomware (Forensic Perspective)

Focus on:
- Execution vectors
- Lateral movement
- Privilege escalation
- Encryption scope
- Backup and shadow copy tampering

Avoid assumptions based solely on:
- Ransom notes
- Filenames
- AV labels

---

### Credential & Identity Abuse

Analyze:
- Sign-in anomalies
- Token issuance and reuse
- MFA fatigue or bypass
- Privileged role escalation
- API key abuse

Identity artifacts often provide **cleaner attribution than malware**.

---

### Insider Threat Analysis

Focus on:
- Access outside role norms
- Data staging and compression
- Use of removable media or personal cloud storage
- Time-of-day anomalies
- Log tampering attempts

Intent must **never be assumed** — only actions proven.

---

### Cloud & SaaS Incident Analysis

Analyze:
- Control-plane activity
- API call sequences
- Permission and role changes
- Resource creation/deletion
- Data access and sharing events

Cloud attacks are often **non-malware-based**.

---

## Tools Commonly Used for Analysis (Expert Level)

### Timeline & Event Reconstruction

- **Timesketch** – Collaborative forensic timeline analysis  
  https://github.com/google/timesketch

- **Plaso (log2timeline)** – Artifact-to-timeline normalization  
  https://github.com/log2timeline/plaso

- **SuperTimeline (Eric Zimmerman)** – Windows-focused timeline correlation  
  https://ericzimmerman.github.io

- **APT-Hunter / APT-Hunter-MDE** – ATT&CK-aligned timeline analysis  
  https://github.com/ahmedkhlief/APT-Hunter

---

### Log & Telemetry Correlation Platforms

**Open Source**
- **Elastic Stack (ELK)** – Multi-source forensic log correlation  
  https://www.elastic.co

- **OpenSearch** – Open-source ELK alternative  
  https://opensearch.org

- **HELK** – Threat-hunting & ATT&CK-aligned correlation lab  
  https://github.com/Cyb3rWard0g/HELK

- **Sigma** – Detection logic validation and behavioral confirmation  
  https://github.com/SigmaHQ/sigma

**Commercial**
- **Splunk Enterprise / ES**  
  https://www.splunk.com

- **Microsoft Sentinel**  
  https://learn.microsoft.com/azure/sentinel/

---

### Memory & Process-Level Analysis

- **Volatility 3** – Memory artifact correlation  
  https://github.com/volatilityfoundation/volatility3

- **MemProcFS** – Memory as a virtual filesystem  
  https://github.com/ufrisk/MemProcFS

- **Rekall** – Advanced memory analysis  
  http://www.rekall-forensic.com

- **Redline** – Memory and host artifact analysis  
  https://www.mandiant.com/resources/redline

---

### Endpoint & Artifact Correlation

- **Velociraptor** – Artifact-driven retrospective analysis  
  https://github.com/Velocidex/velociraptor

- **KAPE + EZ Tools** – Artifact extraction feeding analysis pipelines  
  https://www.kroll.com/en/services/cyber-risk/incident-response-litigation-support/kape

- **Autopsy** – Open-source forensic analysis  
  https://www.sleuthkit.org

- **X-Ways Forensics** – High-performance forensic analysis  
  https://www.x-ways.net/forensics/

---

### Cloud, Identity & SaaS Analysis

- **Azure AD / Entra ID Sign-In Logs**
- **AWS CloudTrail + Athena**
- **GCP Cloud Audit Logs**

Supporting tools:
- **Prowler** – Cloud misuse and posture context  
  https://github.com/prowler-cloud/prowler

- **ScoutSuite** – Cloud configuration correlation  
  https://github.com/nccgroup/ScoutSuite

- **Steampipe** – SQL-based cloud investigations  
  https://github.com/turbot/steampipe

---

### Malware Context (Supporting Only)

- **CAPEv2 / Cuckoo** – Behavioral sandboxing  
  https://github.com/kevoreilly/CAPEv2

- **Any.Run** – Interactive malware behavior analysis  
  https://any.run

- **Ghidra** – Static reverse engineering context  
  https://ghidra-sre.org

---

### Threat Intelligence & TTP Mapping

- **MITRE ATT&CK Navigator**  
  https://attack.mitre.org

- **MISP** – Indicator correlation and enrichment  
  https://www.misp-project.org

- **OpenCTI** – Structured threat intelligence correlation  
  https://www.opencti.io

- **YARA** – Pattern-based artifact identification  
  https://virustotal.github.io/yara/

---

## Common Analysis Failures (Real Incidents)

- Early attribution without evidence
- Ignoring contradictory artifacts
- Over-trusting tool-generated output
- Missing identity and cloud evidence
- Failing to document uncertainty

---

## Documentation Requirements

Each analytical conclusion must include:
- Supporting evidence references
- Timeline correlation
- Confidence level
- Known gaps or limitations
- Alternative hypotheses considered

Uncertainty must be **explicitly documented**, never hidden.

---

## Outputs of the Analysis Phase

By the end of analysis, investigators must have:
- Reconstructed attack narrative
- Defined scope and impact
- Mapped attacker techniques
- Identified detection and control gaps
- Clear inputs for Reporting

---

## Authoritative Blogs & Research (Expert Level)

### Core DFIR Practitioner Blogs
- AboutDFIR – https://aboutdfir.com
- DFIR.blog – https://dfir.blog
- The DFIR Report – https://thedfirreport.com
- This Week in 4n6 – https://thisweekin4n6.wordpress.com
- Forensic Focus – https://www.forensicfocus.com

### Threat Research & Incident Writeups
- Mandiant Blog – https://www.mandiant.com/resources/blog
- CrowdStrike Intelligence – https://www.crowdstrike.com/blog
- Elastic Security Labs – https://www.elastic.co/security-labs
- NCC Group Research – https://research.nccgroup.com
- Trail of Bits – https://blog.trailofbits.com

### Artifact, Cloud & Identity Research
- Eric Zimmerman Blog – https://ericzimmerman.github.io
- ForensicArtifacts Repository – https://github.com/ForensicArtifacts/artifacts
- EVTX Attack Samples – https://github.com/sbousseaden/EVTX-ATTACK-SAMPLES
- Dirk-jan Mollema (Azure AD research) – https://dirkjanm.io
- InverseCos (Azure AD attacks) – https://www.inversecos.com

---

## Relationship to Other Phases

- **Examination** extracts artifacts
- **Analysis** interprets evidence
- **Reporting** communicates findings
- **Lessons Learned** drive improvements

Analysis is where **facts become defensible findings**.

---

## Key Takeaway

> **Analysis is not about being right quickly.  
> It is about being correct, provable, and defensible.**

Strong analysis withstands executive review, regulatory scrutiny,
and courtroom challenge.
