# Reporting Phase – Digital Forensics

## Purpose

The Reporting phase formally **documents forensic findings, scope, impact, and limitations**
in a manner that is **accurate, defensible, and audience-appropriate**.

A forensic report is not a summary of tools used.
It is a **legal, executive, and technical record of truth**.

Failures in reporting commonly result in:
- Executive misinterpretation
- Regulatory non-compliance
- Legal challenges to credibility
- Loss of investigative trust

Reporting begins **only after Analysis is complete**.

---

## When Reporting Is Triggered

Reporting is required when:

- An investigation reaches analytical conclusion
- Executive or board-level briefing is required
- Legal, HR, or Compliance requests documentation
- Regulatory notification is required
- Evidence may be used in litigation or law enforcement

> **If analysis is uncertain, the report must say so explicitly.**

---

## Core Objectives

The Reporting phase ensures:

1. Findings are **fact-based and evidence-supported**
2. Scope and impact are **clearly articulated**
3. Confidence levels and limitations are **explicit**
4. Reports are **audience-appropriate**
5. Documentation is **legally defensible**

---

## Reporting Principles (Expert Level)

### Facts Over Opinions
Reports must clearly distinguish between:
- **Observed facts**
- **Derived conclusions**
- **Unproven or inconclusive hypotheses**

### Transparency Over Certainty
Unknowns, gaps, and limitations must be **explicitly stated**.

### Audience Matters
A single investigation may require:
- Executive report
- Technical forensic report
- Legal or regulatory report

---

# Professional DFIR Report – Standard Structure

> This structure is accepted across **Big4 DFIR**, **IR retainers**, **cyber-insurance**, and **court-assisted investigations**.

---

## 1. Cover Page
- Report Title
- Incident Reference / Case ID
- Organization / Client Name
- Classification (Confidential / Legal Privileged)
- Prepared By
- Date of Issue
- Report Version

---

## 2. Document Control
- Version History
- Authors
- Reviewers
- Approval Authority
- Distribution List

---

## 3. Executive Summary
- High-level incident overview
- Key dates and timeline summary
- Business impact
- Affected systems or data (high level)
- Current status
- Key recommendations

> This section must be **non-technical** and concise.

---

## 4. Incident Background
- Detection source
- Date and time of detection
- Initial alert or trigger
- Incident classification
- Key stakeholders

---

## 5. Scope of Investigation
- Systems and endpoints examined
- Identities and accounts reviewed
- Data types in scope
- Time period covered
- Explicit exclusions
- Constraints and assumptions

---

## 6. Investigation Methodology
- Identification approach
- Preservation controls
- Collection methods
- Examination techniques
- Analysis methodology
- Standards followed (SANS, NIST, ISO)

> This section **defends how the investigation was performed**.

---

## 7. Evidence Handling & Chain of Custody
- Evidence acquisition summary
- Hashing methodology
- Chain of custody overview
- Evidence storage controls
- Integrity verification results

---

## 8. Timeline of Events
- Chronological reconstruction
- Key attacker actions
- System and identity activity
- Evidence references
- Confidence levels

---

## 9. Findings

Each finding must include:
- Description
- Supporting evidence
- Confidence level

Typical finding categories:
- Initial Access
- Persistence
- Privilege Escalation
- Lateral Movement
- Command and Control
- Data Access / Exfiltration
- Malware or Tools Identified
- Cloud or Identity Abuse (if applicable)

---

## 10. Scope & Impact Assessment
- Affected systems
- Affected identities
- Data exposure assessment
- Business and operational impact
- Regulatory exposure

---

## 11. Attribution & Threat Context (If Applicable)
- Observed TTPs
- MITRE ATT&CK mapping
- Threat actor or malware family (with confidence level)
- Alternative hypotheses considered

> Attribution is optional and must be confidence-scored.

---

## 12. Limitations & Uncertainties
- Logging gaps
- Retention limitations
- Systems not examined
- Inconclusive findings
- Assumptions made

> This section **protects the investigation legally**.

---

## 13. Conclusions
- Summary of confirmed facts
- Overall assessment
- Known vs unknown elements
- Residual risk statement

---

## 14. Recommendations
Clearly separated from findings:
- Immediate containment actions
- Remediation steps
- Detection and monitoring improvements
- Policy or control enhancements
- Long-term security improvements

---

## 15. Lessons Learned (Optional)
- What worked well
- What failed
- Process gaps identified
- Improvement actions

---

## 16. Appendices
- Evidence inventory
- Hash values
- Detailed timelines
- Tool versions
- Screenshots and logs
- Supporting artifacts

---

## 17. Glossary (Optional)
- Acronyms
- Technical definitions

---

## 18. Legal Disclaimer
- Intended use of the report
- Limitations of liability
- Jurisdictional considerations

---

## Evidence Referencing Best Practices

Each referenced artifact should include:
- Evidence ID
- Source system
- Timestamp (with timezone)
- Hash value
- Collection method

Example:
> Evidence E-014: Windows Security Event 4624 from DC-01, collected via DFIR-ORC, SHA-256 verified.

---

## Tools Supporting Reporting

### Case Management & Documentation
- TheHive – https://thehive-project.org
- DFIRTrack – https://github.com/dfirtrack/dfirtrack
- FIR – https://github.com/certsocietegenerale/FIR
- RTIR – https://bestpractical.com/rtir/

### Timeline & Visualization
- Timesketch – https://github.com/google/timesketch
- Plaso – https://github.com/log2timeline/plaso

### Reporting & Collaboration
- Markdown + Git (version control)
- Confluence / SharePoint (controlled access)
- PDF (hashed and signed for legal use)

---

## Common Reporting Failures (Observed in Incidents)

- Mixing facts with opinions
- Over-technical executive summaries
- Missing scope exclusions
- No confidence statements
- Weak evidence referencing
- Untracked report revisions

---

## Report Integrity & Version Control

- Maintain version history
- Track authors and reviewers
- Hash final reports
- Restrict access to drafts and finals

---

## Authoritative Blogs & References

- AboutDFIR – https://aboutdfir.com
- DFIR.blog – https://dfir.blog
- The DFIR Report – https://thedfirreport.com
- SANS DFIR Reading Room – https://www.sans.org/digital-forensics/
- Forensic Focus – https://www.forensicfocus.com
- Mandiant Blog – https://www.mandiant.com/resources/blog

---

## Relationship to Other Phases

- **Analysis** produces findings
- **Reporting** formalizes truth
- **Lessons Learned** improve defenses
- **Legal** relies on report accuracy

---

## Key Takeaway

> **A forensic report must survive executives, regulators, and courtrooms.**

Strong reporting:
- Protects investigators
- Enables informed decisions
- Withstands legal challenge
- Preserves organizational trust
