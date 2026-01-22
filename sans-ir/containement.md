# Containment
<!-- SANS Incident Response – Containment Phase -->

---

## 1. Scope & Purpose

The **Containment** phase focuses on **limiting attacker activity, spread, and impact** while preserving evidence required for forensic investigation, legal action, and regulatory response.

Containment aims to:
- Stop or slow attacker operations
- Prevent lateral movement and privilege escalation
- Limit data exfiltration and service disruption
- Preserve volatile and non-volatile evidence
- Stabilize the environment before eradication

Containment is a **risk-based decision phase** where technical actions directly affect business operations and evidentiary integrity.

---

## 2. Process Alignment

### SANS Incident Response Phases
- Preparation
- Identification
- Containment ✅
- Eradication
- Recovery
- Lessons Learned

---

### Digital Forensics Phases (Applicable)
- Preservation
- Collection

Containment actions may alter system state; evidence preservation must be prioritized before irreversible changes.

---

## 3. Containment Strategy

### Short-Term (Immediate) Containment
- Network isolation of compromised hosts
- Account disablement and token revocation
- Blocking malicious IPs, domains, URLs, and hashes
- Suspending cloud workloads or API keys
- Restricting outbound traffic and data flows

### Long-Term (Strategic) Containment
- Network segmentation and zero-trust enforcement
- Conditional access and identity hardening
- EDR policy-based containment
- Monitoring-based containment (watch, alert, trap)
- Temporary business process changes

Containment may be **partial or staged** to avoid tipping off attackers prematurely.

---

## 4. Containment Decision Factors

Containment decisions must consider:
- Incident severity and scope
- Attacker objectives and tradecraft
- Risk of evidence destruction
- Business criticality of affected systems
- Legal, regulatory, and insurance requirements
- Availability of compensating controls

All containment actions should be **documented, approved, and reversible where possible**.

---

## 5. Evidence Sources (Containment Phase)

Evidence to preserve or collect includes:

- Memory images of compromised systems
- Disk images or snapshots
- EDR telemetry and response logs
- Network packet captures
- Identity and authentication logs
- Cloud audit logs and runtime state
- Firewall, proxy, and DNS logs
- Backup metadata and snapshot history

Evidence should be acquired **before containment actions that alter state**.

---

## 6. Tooling

> The tools referenced below represent commonly used DFIR containment capabilities.  
> This list is **not exhaustive** and **not limited** to the tools mentioned.  
> Equivalent tools may be used depending on environment, policy, and investigator judgment.

---

### Open-Source Tools

#### Endpoint Containment & Live Response
- **Velociraptor** – https://github.com/Velocidex/velociraptor  
- **GRR Rapid Response** – https://github.com/google/grr  
- **osquery** – https://github.com/osquery/osquery  
- **KAPE** – https://www.kroll.com/en/services/cyber-risk/incident-response-litigation-support/kape  
- **DFIR-ORC** – https://dfir-orc.github.io/  

---

#### Network Containment & Monitoring
- **Zeek** – https://zeek.org/  
- **Suricata** – https://suricata.io/  
- **Snort** – https://www.snort.org/  
- **tcpdump** – https://www.tcpdump.org/  
- **Wireshark** – https://www.wireshark.org/  

---

#### Identity & Access Containment
- **Azure Conditional Access** – https://learn.microsoft.com/entra/identity/conditional-access/  
- **Microsoft Entra ID Sign-In Logs** – https://learn.microsoft.com/entra/identity/monitoring-health/  
- **AWS IAM / SCPs** – https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html  
- **Okta Policies & System Logs** – https://help.okta.com/  
- **Google Workspace Admin Controls** – https://support.google.com/a/

---

#### Cloud & SaaS Containment
- **AWS GuardDuty** – https://aws.amazon.com/guardduty/  
- **AWS Detective** – https://aws.amazon.com/detective/  
- **Azure Defender for Cloud** – https://learn.microsoft.com/azure/defender-for-cloud/  
- **GCP Security Command Center** – https://cloud.google.com/security-command-center  
- **CloudTrail / Azure Activity Logs / GCP Audit Logs**

---

#### Container & Runtime Containment
- **Falco** – https://falco.org/  
- **Kubernetes Audit Logs** – https://kubernetes.io/docs/tasks/debug/debug-cluster/audit/  
- **Sysdig Inspect (Community)** – https://github.com/draios/sysdig  
- **Docker Explorer** – https://github.com/google/docker-explorer  

---

#### IOC Validation & Blocking
- **MISP** – https://github.com/MISP/MISP  
- **OpenCTI** – https://www.opencti.io/  
- **VirusTotal** – https://www.virustotal.com/  
- **AbuseIPDB** – https://www.abuseipdb.com/  
- **URLhaus** – https://urlhaus.abuse.ch/  

---

### Commercial / Enterprise Tools

#### EDR / XDR
- **CrowdStrike Falcon**
- **Microsoft Defender for Endpoint**
- **SentinelOne Singularity**
- **Palo Alto Cortex XDR**
- **Sophos Intercept X**

---

#### Network & Perimeter Security
- **Palo Alto Networks Firewalls**
- **Fortinet FortiGate**
- **Cisco Secure Firewall**
- **Zscaler Internet Access**
- **Cloudflare Gateway / WAF**

---

#### Email & Collaboration Containment
- **Microsoft Defender for Office 365**
- **Proofpoint**
- **Mimecast**
- **Google Workspace Security Center**

---

## 7. Categorization of Tools

Containment tooling supports:
- Host isolation and response
- Identity and access restriction
- Network segmentation and blocking
- Cloud workload suspension
- Monitoring attacker behavior
- Evidence preservation
- Business continuity controls

---

## 8. Blogs, Research & References

### DFIR & Incident Response
- https://thedfirreport.com/
- https://thisweekin4n6.com/
- https://www.sans.org/blog/?focus-area=digital-forensics
- https://www.mandiant.com/resources/blog
- https://www.crowdstrike.com/blog/
- https://www.microsoft.com/security/blog/

---

### Incident Handling & Playbooks
- https://www.cisa.gov/incident-response-playbooks
- https://www.nist.gov/cyberframework
- https://www.enisa.europa.eu/topics/incident-response

---

### Cloud & Identity Research
- https://unit42.paloaltonetworks.com/
- https://securitylabs.verizon.com/
- https://cloud.google.com/blog/topics/security

---

## 9. Practical DFIR Usage

Containment is used to:
- Halt attacker activity
- Reduce blast radius
- Preserve evidence for root cause analysis
- Stabilize business operations
- Enable safe eradication

### Typical Scenarios
- Active ransomware encryption
- Ongoing data exfiltration
- Identity compromise and lateral movement
- Cloud workload abuse
- Insider threat escalation

---

## 10. Common Mistakes & Pitfalls

- Containing too aggressively and destroying evidence
- Delaying containment due to fear of disruption
- Ignoring identity and cloud attack paths
- Failing to monitor attacker reaction
- Assuming containment equals remediation
- Poor documentation of actions taken

---

## 11. Output & Reporting

Effective containment produces:
- Controlled and reduced incident scope
- Preserved forensic evidence
- Documented containment actions
- Business impact assessment
- Risk-informed eradication plan
- Clear executive and technical updates

---

## Notes

- Preserve evidence before irreversible containment actions
- Document approvals and decisions
- Coordinate with legal, HR, and leadership
- Expect attacker behavior to change post-containment
- Containment is temporary; eradication follows
