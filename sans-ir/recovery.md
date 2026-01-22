# Recovery
<!-- SANS Incident Response – Expert-Level Recovery Phase -->

---

## 1. Scope & Purpose

The **Recovery** phase focuses on **safely restoring systems, services, and business operations** after eradication, while ensuring the environment is **secure, monitored, and resilient** against re-compromise.

At an expert level, recovery is:
- Not simply restoring backups
- Not “bringing systems back online quickly”
- Not assuming eradication was perfect

Recovery is about **controlled reintroduction of risk**, with continuous validation.

---

## 2. What “Recovery” Means at Expert Level

An environment is considered **recovered** only when:

- Systems are restored from trusted sources
- Business operations are functioning normally
- Security controls are re-enabled and validated
- Monitoring is heightened
- No signs of attacker persistence or re-entry exist
- Stakeholders are confident in system integrity

Recovery ends **only when confidence is restored**, not when uptime returns.

---

## 3. Minimum vs Mature Recovery Capability

### 3.1 Minimum Required (Non-Negotiable)

If these are missing, recovery is unsafe:

- Verified clean backups or gold images
- Ability to rebuild systems (not just restore)
- Credential reset and validation
- Security controls re-enabled
- Monitoring during restoration
- Clear recovery approval authority

---

### 3.2 Mature SOC / DFIR Capability

These enable resilient and confident recovery:

- Immutable backups
- Staged / phased recovery plans
- Infrastructure-as-Code restoration
- Recovery validation testing
- Threat hunting during recovery
- Executive and regulatory coordination

---

## 4. Recovery Strategy (EXPERT THINKING)

### 4.1 Phased Recovery (RECOMMENDED)

Recovery should occur in stages:

1. **Critical security infrastructure** (identity, logging, EDR)
2. **Core business services**
3. **User-facing systems**
4. **Non-critical and legacy systems**

This reduces blast radius if re-compromise occurs.

---

### 4.2 Restore vs Rebuild Decision

| Scenario | Recommended Action |
|--------|--------------------|
| Ransomware | Rebuild from gold image |
| Identity compromise | Rebuild + credential reset |
| Cloud breach | Rebuild resources |
| Insider threat | Controlled restore + monitoring |
| APT | Full rebuild and segmentation |

If trust is lost, **rebuild is always safer than restore**.

---

## 5. Pre-Recovery Validation (CRITICAL CHECKPOINT)

Before restoring systems:

- Confirm eradication is complete
- Validate no active attacker activity
- Verify integrity of backups
- Confirm credentials and secrets are rotated
- Ensure logging and monitoring are enabled
- Obtain formal recovery approval

Skipping this step causes **reinfection loops**.

---

## 6. Recovery Execution Workflow (REAL WORLD)

### Step 1: Restore Core Security Services
- Identity platforms
- SIEM and logging
- EDR/XDR platforms
- Network security controls

Without security visibility, recovery is blind.

---

### Step 2: Restore Systems & Services
- Restore or rebuild systems in priority order
- Apply patches and hardening
- Reconfigure security controls
- Validate application integrity

---

### Step 3: Credential & Access Validation
- Validate password resets
- Confirm token and session revocation
- Review privileged access
- Enforce MFA and conditional access

---

### Step 4: Heightened Monitoring
- Enable increased alerting thresholds
- Monitor for known IOCs
- Hunt for re-entry attempts
- Track anomalous behavior

---

### Step 5: Business Validation
- Confirm application functionality
- Validate data integrity
- Confirm user access
- Obtain business sign-off

---

## 7. Tooling – Capability-Based (Expert View)

> Tools represent **capabilities**, not brand dependency.  
> Use approved equivalents where required.

---

### 7.1 Backup & Restoration

- Veeam  
  https://www.veeam.com/
- Commvault  
  https://www.commvault.com/
- Rubrik  
  https://www.rubrik.com/
- Cohesity  
  https://www.cohesity.com/
- Native cloud backups  
  (AWS Backup, Azure Backup, GCP Backup)

Purpose: Restore from known-good sources.

---

### 7.2 Endpoint & Post-Recovery Validation

- Velociraptor  
  https://github.com/Velocidex/velociraptor
- Microsoft Defender for Endpoint  
  https://learn.microsoft.com/defender-endpoint/
- CrowdStrike Falcon  
  https://www.crowdstrike.com/
- SentinelOne Singularity  
  https://www.sentinelone.com/

Purpose: Validate systems remain clean post-restore.

---

### 7.3 Configuration & Hardening

- CIS Benchmarks  
  https://www.cisecurity.org/cis-benchmarks
- Ansible  
  https://www.ansible.com/
- Terraform  
  https://www.terraform.io/
- AWS CloudFormation  
  https://docs.aws.amazon.com/cloudformation/
- Azure Bicep  
  https://learn.microsoft.com/azure/azure-resource-manager/bicep/

Purpose: Prevent reintroduction of vulnerabilities.

---

### 7.4 Monitoring & Threat Hunting

- SIEM platforms (Splunk, Elastic, QRadar)
- Sigma rules  
  https://github.com/SigmaHQ/sigma
- Threat hunting queries
- Custom detections from incident learnings

Purpose: Detect attacker return attempts early.

---

## 8. Recovery-Specific Risks (FIELD EXPERIENCE)

- Restoring infected backups
- Re-enabling compromised accounts
- Bringing systems online without monitoring
- Skipping validation due to business pressure
- Not coordinating with legal and compliance
- Declaring recovery too early

---

## 9. Output of an Expert-Level Recovery Phase

Recovery is complete when:

- Systems are fully operational
- Security controls are active and validated
- Monitoring is stable
- No malicious activity is detected
- Business stakeholders sign off
- Organization is ready for lessons learned

---

## Final Expert Note

Recovery is **not the end of the incident**.

It is the phase where:
- Attackers attempt re-entry
- Business pressure is highest
- Mistakes are most costly

Expert recovery is **slow, deliberate, and validated** —  
because trust, once lost, is expensive to rebuild.
