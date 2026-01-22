# Identification
<!-- SANS Incident Response – Identification Phase -->

---

## 1. Scope & Purpose

The **Identification** phase focuses on detecting, validating, and scoping potential security incidents.  
Its objective is to determine whether an observed event constitutes a true security incident and to establish the **initial scope, severity, and impact**.

This phase ensures that:
- False positives are reduced quickly
- True incidents are confirmed with evidence
- Initial forensic data is preserved
- Response actions are proportional and informed
- SOC alerts transition cleanly into DFIR investigations

Identification is the **decision-making phase** that determines whether containment and eradication actions are required.

---

## 2. Process Alignment

### SANS Incident Response Phases
- Preparation
- Identification ✅
- Containment
- Eradication
- Recovery
- Lessons Learned

---

### Digital Forensics Phases (Applicable)
- Identification
- Preservation
- Collection

Evidence preservation begins immediately during this phase, even before containment.

---

## 3. Identification Activities

### Alert Intake & Triage
- Receive alerts from SIEM, EDR, XDR, SOAR, cloud-native services, or user reports
- Validate alerts and remove false positives
- Correlate signals across multiple telemetry sources
- Assess alert confidence and fidelity

### Incident Confirmation
- Determine presence of malicious or unauthorized activity
- Identify affected systems, users, cloud resources, or applications
- Map observed behavior to known attacker techniques
- Assign incident category and severity

### Initial Scoping
- Identify impacted hosts, identities, and workloads
- Establish an initial timeline (high-level)
- Identify potential lateral movement or privilege escalation
- Extract and validate indicators of compromise (IOCs)
- Preserve volatile and cloud-native evidence

---

## 4. Evidence Sources (Identification Phase)

Common evidence reviewed during identification includes:

- Endpoint telemetry and EDR alerts
- SIEM correlations and raw logs
- Network logs (firewall, proxy, VPN, DNS)
- Authentication and identity logs
- Cloud audit and activity logs
- Email and collaboration platform logs
- Memory artifacts (if active compromise suspected)
- Threat intelligence feeds and reputation data
- User-reported artifacts (emails, files, URLs)

Evidence collection should be **minimally invasive but forensically sound**.

---

## 5. Tooling

> The tools referenced below represent commonly used DFIR capabilities for incident identification.  
> This list is **not exhaustive** and is **not limited** to the tools mentioned here.  
> Equivalent or alternative tools may be used based on organizational standards, environment, and investigator preference.

---

### Open-Source Tools

#### Detection & Alert Analysis
- **Sigma** – https://github.com/SigmaHQ/sigma  
  Generic detection rules across SIEM platforms.
- **Zeek** – https://zeek.org/  
  Network traffic and protocol analysis.
- **Suricata** – https://suricata.io/  
  Network-based threat detection.
- **YARA** – https://virustotal.github.io/yara/  
  Identification of malicious files and artifacts.

---

#### Endpoint & Live Triage
- **Velociraptor** – https://github.com/Velocidex/velociraptor  
  Live endpoint queries and artifact collection.
- **GRR Rapid Response** – https://github.com/google/grr  
  Remote live forensics and endpoint triage.
- **osquery** – https://github.com/osquery/osquery  
  Endpoint state inspection using SQL queries.
- **KAPE** – https://www.kroll.com/en/services/cyber-risk/incident-response-litigation-support/kape  
  Rapid triage and artifact acquisition.

---

#### Identity & Authentication Analysis
- **Azure Entra ID Sign-In Logs** – https://learn.microsoft.com/entra/identity/monitoring-health/  
- **Okta System Logs** – https://developer.okta.com/docs/reference/api/system-log/  
- **Auth0 Logs** – https://auth0.com/docs/logs  

Used to identify token abuse, OAuth misuse, impossible travel, and MFA fatigue attacks.

---

#### Email & Collaboration Investigation
- **Microsoft 365 Defender Explorer** – https://learn.microsoft.com/microsoft-365/security/  
- **Google Workspace Audit Logs** – https://support.google.com/a/answer/4579579  
- **Unfurl** – https://github.com/obsidianforensics/unfurl  

Used for phishing, BEC, and malicious attachment analysis.

---

#### Threat Intelligence & Enrichment
- **MISP** – https://github.com/MISP/MISP  
- **IntelMQ** – https://github.com/certtools/intelmq  
- **OpenCTI** – https://www.opencti.io/  
- **VirusTotal** – https://www.virustotal.com/  
- **AbuseIPDB** – https://www.abuseipdb.com/  
- **URLhaus** – https://urlhaus.abuse.ch/  

Used for IOC validation, enrichment, and campaign context.

---

#### Cloud & Container Identification
- **AWS GuardDuty** – https://aws.amazon.com/guardduty/  
- **AWS Detective** – https://aws.amazon.com/detective/  
- **Azure Defender for Cloud** – https://learn.microsoft.com/azure/defender-for-cloud/  
- **GCP Security Command Center** – https://cloud.google.com/security-command-center  
- **Falco** – https://falco.org/  
- **Kubernetes Audit Logs** – https://kubernetes.io/docs/tasks/debug/debug-cluster/audit/

---

#### Rapid Triage Utilities
- **CyberChef** – https://gchq.github.io/CyberChef/  
- **FLARE FLOSS** – https://github.com/mandiant/flare-floss  
- **Strings / Bstrings** – https://github.com/EricZimmerman/bstrings  

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

## 6. Categorization of Tools

Identification-phase tools support:
- Alert validation and triage
- Cross-source correlation
- Endpoint, identity, and cloud scoping
- IOC extraction and enrichment
- Threat classification and prioritization
- Early forensic preservation

---

## 7. Blogs, Research & References

### DFIR & Detection Research
- https://thedfirreport.com/
- https://thisweekin4n6.com/
- https://www.sans.org/blog/?focus-area=digital-forensics
- https://www.microsoft.com/security/blog/
- https://securityaffairs.co/wordpress/

---

### Threat Intelligence & Frameworks
- https://attack.mitre.org/
- https://aboutdfir.com/
- https://www.dfir.training/
- https://www.forensicfocus.com/

---

### Standards & Guidance
- NIST SP 800-61 – https://csrc.nist.gov/publications/detail/sp/800-61/rev-2/final
- ISO/IEC 27035 – https://www.iso.org/standard/44379.html

---

## 8. Practical DFIR Usage

The Identification phase is used to:
- Confirm true security incidents
- Reduce false positives and alert fatigue
- Prioritize response actions
- Preserve volatile and cloud-native evidence
- Avoid premature containment actions

### Typical Scenarios
- Ransomware precursors
- Cloud account compromise
- Identity abuse and MFA bypass
- Malware execution alerts
- Insider threat indicators
- Web application exploitation

---

## 9. Common Mistakes & Pitfalls

- Treating alerts as confirmed incidents without validation
- Delaying evidence preservation
- Overreliance on a single telemetry source
- Ignoring identity and cloud attack paths
- Escalating incidents without scoping
- Containing too early and destroying evidence

---

## 10. Output & Reporting

Effective identification produces:
- Confirmed incident classification
- Initial scope of compromise
- Severity and impact assessment
- Preserved volatile and cloud evidence
- Initial IOC set
- Clear handoff to containment phase
- Executive and technical situation reports

---

## Notes

- Identification decisions must be evidence-driven
- Preserve evidence before containment
- Expect scope to expand as investigation progresses
- Identification quality directly impacts containment success
