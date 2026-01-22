# Identification
<!-- SANS Incident Response – Expert-Level Identification Phase -->

---

## 1. Scope & Purpose

The **Identification** phase determines whether observed activity represents a **true security incident**, and if so:

- What happened
- Who or what is affected
- How severe the incident is
- Whether containment must begin immediately

At an expert level, identification is **not alert review** —  
it is **evidence-based incident confirmation and initial scoping**.

Poor identification leads to:
- False positives escalating to outages
- Delayed containment of real attacks
- Evidence loss due to premature actions

---

## 2. What “Identification” Means at Expert Level

An incident is considered **identified** only when:

- Malicious or unauthorized activity is confirmed
- Evidence supports the conclusion (not assumptions)
- Initial scope is defined (hosts, users, cloud resources)
- Severity and business impact are assessed
- A containment recommendation is documented

Identification **ends when a decision is made**, not when an alert fires.

---

## 3. Minimum vs Mature Identification Capability

### 3.1 Minimum Required (Non-Negotiable)

If these are missing, identification will be unreliable:

- Centralized log visibility (SIEM or equivalent)
- Endpoint security telemetry
- Identity authentication logs
- Ability to query endpoints remotely
- IOC enrichment capability
- Basic timeline construction

---

### 3.2 Mature SOC / DFIR Capability

These enable fast, confident identification:

- Cross-source correlation (endpoint + identity + cloud)
- Memory capture for active compromise
- Threat intelligence platforms
- Automated triage workflows
- Detection engineering feedback loops
- Cloud and SaaS forensic visibility

---

## 4. Identification Workflow (REAL WORLD)

### Step 1: Alert Intake & Context
- Receive alert from SIEM, EDR, cloud, SaaS, or user report
- Identify detection source and confidence
- Determine if alert is behavioral, signature-based, or anomaly-based

### Step 2: Evidence Validation
- Validate alert against raw logs
- Check for false positives
- Confirm malicious indicators (process, user, API, network)

### Step 3: Initial Scoping
- Identify affected hosts, identities, workloads
- Determine time window of activity
- Look for lateral movement or persistence

### Step 4: Severity & Impact Assessment
- Data exposure?
- Privilege escalation?
- Business-critical systems involved?
- Regulatory or legal implications?

### Step 5: Decision Point
- Escalate to containment
- Continue monitoring
- Close as false positive

Every step must be **evidence-driven**.

---

## 5. Evidence Sources & Log Paths (PRIORITIZED)

### 5.1 Tier 1 – Incident Confirmation

These answer **did something malicious occur**:

#### Windows
- Security.evtx  
  `C:\Windows\System32\winevt\Logs\Security.evtx`
- Sysmon  
  `Microsoft-Windows-Sysmon/Operational.evtx`
- PowerShell  
  `Microsoft-Windows-PowerShell/Operational.evtx`

#### Linux
- Authentication  
  `/var/log/auth.log` or `/var/log/secure`
- Auditd  
  `/var/log/audit/audit.log`

#### Identity
- Entra ID Sign-In Logs
- Okta System Logs
- VPN authentication logs

---

### 5.2 Tier 2 – Scope Expansion

These answer **how far did it spread**:

#### Endpoint Artifacts
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

### 5.3 Tier 3 – Advanced Confirmation

Used for stealthy or high-impact attacks:

- Memory images
- Disk snapshots
- PCAPs
- Cloud API activity logs
- Email message traces
- SaaS audit logs

---

## 6. Attack Type → Identification Evidence Mapping

| Incident Type | Primary Evidence |
|--------------|------------------|
| Ransomware | EDR telemetry, Prefetch, SRUM, memory |
| Identity Abuse | Sign-in logs, token activity, audit logs |
| Cloud Breach | CloudTrail, IAM, API calls |
| Insider Threat | File access logs, email, DLP |
| Malware | Memory, execution artifacts |
| APT | Timeline + identity + network |

This prevents **random or incomplete investigations**.

---

## 7. Tooling – Capability-Based (Expert View)

> Tools represent **capabilities**, not brand dependency.  
> Use approved equivalents where required.

---

### 7.1 Detection & Correlation

- Sigma  
  https://github.com/SigmaHQ/sigma
- Splunk Enterprise Security  
  https://www.splunk.com/
- Elastic Security  
  https://www.elastic.co/security
- IBM QRadar  
  https://www.ibm.com/security/qradar
- Graylog  
  https://www.graylog.org/

Purpose: Validate alerts and correlate signals.

---

### 7.2 Endpoint & Live Triage

- Velociraptor  
  https://github.com/Velocidex/velociraptor
- GRR Rapid Response  
  https://github.com/google/grr
- KAPE  
  https://www.kroll.com/kape
- osquery  
  https://github.com/osquery/osquery
- FleetDM  
  https://github.com/fleetdm/fleet
- Redline  
  https://www.fireeye.com/services/freeware/redline.html

Purpose: Rapid scoping without destroying evidence.

---

### 7.3 Timeline & Log Analysis

- Plaso / log2timeline  
  https://github.com/log2timeline/plaso
- Timesketch  
  https://github.com/google/timesketch
- Hayabusa  
  https://github.com/Yamato-Security/hayabusa
- Chainsaw  
  https://github.com/countercept/chainsaw
- Eric Zimmerman Tools  
  https://ericzimmerman.github.io/

Purpose: Understand attacker sequence of actions.

---

### 7.4 Threat Intelligence & IOC Enrichment

- MISP  
  https://github.com/MISP/MISP
- OpenCTI  
  https://www.opencti.io/
- IntelMQ  
  https://github.com/certtools/intelmq
- VirusTotal  
  https://www.virustotal.com/
- AbuseIPDB  
  https://www.abuseipdb.com/
- URLhaus  
  https://urlhaus.abuse.ch/

Purpose: Validate indicators and identify campaigns.

---

### 7.5 Decoding & Rapid Analysis

- CyberChef  
  https://gchq.github.io/CyberChef/
- FLOSS  
  https://github.com/mandiant/flare-floss
- bstrings  
  https://github.com/EricZimmerman/bstrings
- Unfurl  
  https://github.com/obsidianforensics/unfurl
- Didier Stevens Tools  
  https://blog.didierstevens.com/programs/

---

## 8. Common Identification Failures (FIELD EXPERIENCE)

- Treating alerts as incidents without validation
- Ignoring identity telemetry
- Over-reliance on one data source
- Delaying evidence preservation
- Premature containment actions
- Poor documentation of decisions

---

## 9. Output of an Expert-Level Identification Phase

Identification is complete when you have:

- Confirmed incident classification
- Initial scope of compromise
- Severity and impact assessment
- Preserved critical evidence
- Clear containment recommendation
- Executive-ready summary
- Technical investigation notes

---

## Final Expert Note

Identification is the **most dangerous phase** of incident response.

If done poorly:
- Containment fails
- Evidence is lost
- Business impact increases

If done well:
- Everything downstream becomes easier.

The goal is **confidence**, not speed.
