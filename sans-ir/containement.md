# Containment
<!-- SANS Incident Response – Expert-Level Containment Phase -->

---

## 1. Scope & Purpose

The **Containment** phase focuses on **stopping or limiting attacker activity** while preserving evidence required for forensic investigation, legal action, and recovery.

At an expert level, containment is:
- A **risk-based decision**, not a reflex action
- A balance between **business continuity and forensic integrity**
- A phase where **bad decisions cause permanent damage**

Containment does **not** mean eradication.  
Containment is temporary control to **buy time safely**.

---

## 2. What “Containment” Means at Expert Level

An incident is considered **contained** when:

- Attacker activity is stopped or significantly limited
- Lateral movement and data exfiltration are prevented
- Compromised identities or systems are controlled
- Evidence required for investigation is preserved
- Business risk is reduced to an acceptable level

Containment ends **only when the attacker can no longer operate freely**.

---

## 3. Minimum vs Mature Containment Capability

### 3.1 Minimum Required (Non-Negotiable)

If these are missing, containment will be dangerous or ineffective:

- Ability to isolate endpoints remotely
- Ability to disable accounts and revoke sessions
- Network-level blocking (firewall, proxy, DNS)
- Cloud resource control (stop, snapshot, restrict)
- Documentation and approval authority
- Evidence preservation before destructive actions

---

### 3.2 Mature SOC / DFIR Capability

These allow **controlled and stealthy containment**:

- EDR/XDR isolation with forensic telemetry
- Conditional access and identity-based containment
- Network segmentation and zero-trust controls
- Monitoring-based containment (observe attacker behavior)
- Automated containment workflows
- Legal, HR, and executive coordination

---

## 4. Containment Strategy (EXPERT THINKING)

### 4.1 Short-Term (Immediate) Containment

Used when there is **active risk**:

- Isolate compromised endpoints
- Disable or restrict compromised user accounts
- Revoke tokens, sessions, and API keys
- Block known malicious IPs, domains, hashes
- Restrict outbound traffic to prevent exfiltration

⚠️ These actions may **destroy volatile evidence** if done incorrectly.

---

### 4.2 Long-Term (Strategic) Containment

Used when attacker presence is confirmed but controlled:

- Network segmentation
- Conditional access enforcement
- EDR-based process blocking
- Temporary firewall and proxy rules
- Monitoring attacker behavior (watch, alert, log)

This approach is often used in **APT and insider threat cases**.

---

## 5. Evidence Preservation Before Containment (CRITICAL)

Before executing irreversible containment actions, preserve:

- Memory images (if active compromise)
- Disk snapshots or forensic images
- EDR telemetry and response logs
- Cloud resource states and audit logs
- Network captures (if available)
- Identity and authentication logs

If evidence is destroyed during containment, **root cause analysis may fail**.

---

## 6. Containment Decision Matrix (EXPERT TOOL)

| Scenario | Containment Priority | Notes |
|--------|----------------------|-------|
| Active ransomware | Immediate isolation | Evidence second to impact |
| Data exfiltration | Block outbound traffic | Preserve logs |
| Identity compromise | Revoke tokens first | Avoid tipping attacker |
| Cloud abuse | Restrict IAM | Snapshot resources |
| Insider threat | Silent monitoring | Legal coordination |
| APT | Strategic containment | Observe tactics |

This matrix prevents **panic-driven decisions**.

---

## 7. Attack Type → Containment Mapping

| Incident Type | Primary Containment Actions |
|--------------|-----------------------------|
| Ransomware | Endpoint isolation, process kill |
| Identity Abuse | Token revocation, MFA enforcement |
| Cloud Breach | IAM restriction, workload suspension |
| Insider Threat | Access restriction, monitoring |
| Malware | Network isolation, C2 blocking |
| APT | Segmentation, long-term monitoring |

---

## 8. Tooling – Capability-Based (Expert View)

> Tools represent **capabilities**, not brand dependency.  
> Use approved equivalents where required.

---

### 8.1 Endpoint Containment & Response

- Velociraptor  
  https://github.com/Velocidex/velociraptor
- GRR Rapid Response  
  https://github.com/google/grr
- CrowdStrike Falcon (Host Isolation)  
  https://www.crowdstrike.com/
- Microsoft Defender for Endpoint  
  https://learn.microsoft.com/defender-endpoint/
- SentinelOne Singularity  
  https://www.sentinelone.com/

Purpose: Stop endpoint-based attacker activity.

---

### 8.2 Identity & Access Containment

- Entra ID Conditional Access  
  https://learn.microsoft.com/entra/identity/conditional-access/
- Okta Policies  
  https://help.okta.com/
- AWS IAM & SCPs  
  https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html
- Azure RBAC  
  https://learn.microsoft.com/azure/role-based-access-control/

Purpose: Cut attacker access without touching endpoints.

---

### 8.3 Network & Perimeter Containment

- Palo Alto Networks Firewalls  
  https://www.paloaltonetworks.com/
- Fortinet FortiGate  
  https://www.fortinet.com/products/next-generation-firewall
- Cisco Secure Firewall  
  https://www.cisco.com/
- Zscaler  
  https://www.zscaler.com/
- Cloudflare Gateway  
  https://www.cloudflare.com/

Purpose: Prevent lateral movement and exfiltration.

---

### 8.4 Cloud & SaaS Containment

- AWS GuardDuty / Detective  
  https://aws.amazon.com/
- Azure Defender for Cloud  
  https://learn.microsoft.com/azure/defender-for-cloud/
- GCP Security Command Center  
  https://cloud.google.com/security-command-center
- Microsoft 365 Defender  
  https://learn.microsoft.com/microsoft-365/security/

Purpose: Control cloud-native attack paths.

---

## 9. Common Containment Failures (FIELD EXPERIENCE)

- Isolating systems before memory capture
- Disabling accounts without preserving logs
- Over-blocking and breaking business operations
- Tipping attackers prematurely
- Poor communication with leadership
- Treating containment as eradication

---

## 10. Output of an Expert-Level Containment Phase

Containment is successful when:

- Attacker activity is halted or controlled
- Evidence is preserved
- Business risk is stabilized
- Actions are documented and approved
- Environment is ready for eradication
- Stakeholders are informed clearly

---

## Final Expert Note

Containment is the **most dangerous phase** of incident response.

Move too slowly — attackers continue.  
Move too fast — evidence is destroyed.

Expert containment is about **control, not panic**.
