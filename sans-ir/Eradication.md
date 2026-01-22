# Eradication
<!-- SANS Incident Response – Expert-Level Eradication Phase -->

---

## 1. Scope & Purpose

The **Eradication** phase focuses on **completely removing the attacker’s presence** from the environment and eliminating the **root cause** of the incident.

At an expert level, eradication is:
- Not malware deletion
- Not system rebooting
- Not “closing the alert”

Eradication means **attackers cannot regain access using the same methods**.

If eradication is incomplete, **re-infection or re-compromise is inevitable**.

---

## 2. What “Eradication” Means at Expert Level

An incident is considered **eradicated** only when:

- All malicious artifacts are removed
- Persistence mechanisms are eliminated
- Compromised credentials are invalidated
- Vulnerabilities and misconfigurations are fixed
- Backdoors, implants, and access paths are closed
- Root cause is clearly identified and documented

Eradication ends **only when the attacker’s original access path is gone**.

---

## 3. Minimum vs Mature Eradication Capability

### 3.1 Minimum Required (Non-Negotiable)

If these are missing, eradication will fail:

- Confirmed root cause
- Full list of affected systems and identities
- Ability to reimage or rebuild systems
- Credential reset capability
- Patch and configuration management access
- Validation that malicious activity has stopped

---

### 3.2 Mature SOC / DFIR Capability

These enable confident, lasting eradication:

- Gold image re-deployment
- Infrastructure-as-Code remediation
- Automated credential rotation
- Cloud resource rebuild (not cleanup)
- Detection coverage validation
- Purple team confirmation of fix effectiveness

---

## 4. Eradication Strategy (EXPERT THINKING)

### 4.1 Artifact-Based Eradication (LOW CONFIDENCE)

Examples:
- Deleting malware files
- Killing processes
- Removing scheduled tasks

⚠️ **High risk of reinfection** if root cause is not addressed.

---

### 4.2 Root-Cause Eradication (REQUIRED)

Examples:
- Reimaging compromised endpoints
- Resetting and rotating credentials
- Removing vulnerable services or exposed ports
- Fixing IAM misconfigurations
- Rebuilding compromised cloud resources

Root-cause eradication is **destructive by design** — and that’s correct.

---

## 5. Root Cause Categories (What You Must Eliminate)

### 5.1 Endpoint-Based
- Malware persistence (services, autoruns, WMI)
- Local admin abuse
- Unpatched vulnerabilities
- Credential dumping artifacts

### 5.2 Identity-Based
- Compromised passwords
- OAuth token abuse
- API keys and secrets
- MFA bypass or fatigue vectors

### 5.3 Network-Based
- Exposed management ports
- Weak segmentation
- Legacy protocols (SMBv1, NTLM)
- Flat network architecture

### 5.4 Cloud-Based
- Over-privileged IAM roles
- Exposed storage buckets
- Compromised compute workloads
- Insecure CI/CD secrets

---

## 6. Attack Type → Eradication Mapping

| Incident Type | Eradication Actions |
|--------------|---------------------|
| Ransomware | Reimage systems, reset credentials |
| Identity Abuse | Rotate tokens, enforce MFA |
| Cloud Breach | Rebuild resources, fix IAM |
| Insider Threat | Remove access, HR/legal actions |
| Malware | Reimage, validate persistence |
| APT | Full environment hardening |

This prevents **partial eradication**.

---

## 7. Eradication Workflow (REAL WORLD)

### Step 1: Confirm Root Cause
- Validate initial access vector
- Identify persistence mechanisms
- Confirm attacker objectives

### Step 2: Prepare Remediation Plan
- Define systems to rebuild
- Define credentials to rotate
- Define configs to change
- Obtain approvals

### Step 3: Execute Eradication
- Reimage or rebuild systems
- Reset credentials and secrets
- Patch vulnerabilities
- Remove persistence

### Step 4: Validate Success
- Confirm no malicious activity
- Verify detections no longer fire
- Run post-eradication scans
- Monitor for re-entry attempts

---

## 8. Tooling – Capability-Based (Expert View)

> Tools represent **capabilities**, not brand dependency.  
> Use approved equivalents where required.

---

### 8.1 Endpoint Remediation & Validation

- Velociraptor  
  https://github.com/Velocidex/velociraptor
- GRR Rapid Response  
  https://github.com/google/grr
- Microsoft Defender for Endpoint  
  https://learn.microsoft.com/defender-endpoint/
- CrowdStrike Falcon  
  https://www.crowdstrike.com/
- SentinelOne Singularity  
  https://www.sentinelone.com/

Purpose: Validate clean state and enforce remediation.

---

### 8.2 Persistence Detection & Cleanup

- Autoruns  
  https://learn.microsoft.com/sysinternals/downloads/autoruns
- Sysmon  
  https://learn.microsoft.com/sysinternals/downloads/sysmon
- KAPE  
  https://www.kroll.com/kape
- Eric Zimmerman Tools  
  https://ericzimmerman.github.io/

Purpose: Ensure persistence is fully removed.

---

### 8.3 Credential & Secret Rotation

- Azure AD / Entra ID  
  https://learn.microsoft.com/entra/
- AWS IAM  
  https://docs.aws.amazon.com/IAM/latest/UserGuide/
- HashiCorp Vault  
  https://www.vaultproject.io/
- CyberArk  
  https://www.cyberark.com/

Purpose: Eliminate stolen credentials permanently.

---

### 8.4 Cloud & Infrastructure Rebuild

- Terraform  
  https://www.terraform.io/
- AWS CloudFormation  
  https://docs.aws.amazon.com/cloudformation/
- Azure ARM / Bicep  
  https://learn.microsoft.com/azure/azure-resource-manager/
- Kubernetes Rebuilds  
  https://kubernetes.io/docs/tasks/

Purpose: Rebuild instead of “cleaning” compromised infrastructure.

---

## 9. Common Eradication Failures (FIELD EXPERIENCE)

- Cleaning instead of rebuilding
- Not resetting credentials
- Ignoring identity attack paths
- Leaving persistence mechanisms
- Assuming containment = eradication
- Not validating eradication success

---

## 10. Output of an Expert-Level Eradication Phase

Eradication is complete when:

- Root cause is eliminated
- Systems are rebuilt or verified clean
- Credentials and secrets are rotated
- Vulnerabilities are fixed
- Attacker access paths are closed
- No malicious activity is observed

---

## Final Expert Note

Eradication is **where you win or lose the incident**.

If attackers return:
- Eradication failed
- Not detection
- Not containment

Expert eradication is **destructive, deliberate, and verified**.
