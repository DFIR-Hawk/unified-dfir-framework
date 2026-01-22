# Preservation Phase – Digital Forensics

## Purpose

The Preservation phase ensures that **identified evidence is protected from alteration, loss, contamination, or destruction** while maintaining **legal admissibility, integrity, and traceability**.

Preservation is the **foundation of forensic credibility**.  
If evidence is not preserved correctly, **all subsequent forensic work may be legally invalid**.

Preservation begins **immediately after Identification** and continues **until the investigation is formally closed**.

---

## When Preservation Is Triggered

Preservation must begin when:

- Evidence sources have been identified
- An incident is escalated beyond routine SOC triage
- Legal, HR, Compliance, or external counsel is engaged
- Ransomware, insider threat, fraud, or data breach is suspected
- Regulatory notification or law-enforcement involvement is possible

> **If evidence is not preserved, it effectively does not exist.**

---

## Core Objectives

The Preservation phase ensures:

1. **Evidence integrity** is maintained at all times  
2. **Chain of custody** is continuous and verifiable  
3. **Original data remains unchanged**  
4. **Unauthorized access or modification** is prevented  
5. **Legal and regulatory requirements** are satisfied  

---

## Key Preservation Principles (Field-Tested)

### Preserve Before You Analyze
No parsing, triage, or interpretation occurs **before preservation decisions are complete**.

### Minimal Impact
Preservation actions must:
- Minimize business disruption
- Avoid unnecessary system changes
- Prevent evidence contamination

### Full Traceability
Every action must be:
- Logged
- Time-stamped
- Attributable to a specific individual

### Assume Legal Scrutiny
Preservation must withstand:
- Internal audit
- Regulatory review
- Courtroom cross-examination

---

## Practical Preservation Workflow (Real-World)

### 1. Establish Legal & Organizational Authority

Before touching evidence:

- Confirm investigation authorization
- Identify jurisdiction and applicable laws
- Determine regulated data exposure (PII, PHI, financial, employee data)
- Engage legal or compliance teams when required
- Define scope boundaries clearly

This step determines **what can be preserved and how**.

---

### 2. Secure Evidence Sources

Common preservation actions include:

- Logical network isolation (preferred over powering off)
- Suspending log rotation and cleanup tasks
- Extending cloud/SaaS log retention
- Disabling automated backup deletion
- Restricting administrative access
- Preserving VM snapshots (with documentation)

> **Avoid powering off systems unless explicitly required.**

---

### 3. Preserve Volatile Evidence (Highest Priority)

Volatile data is **most likely to be lost** and often **most valuable**.

Examples:
- Running processes
- Active network connections
- Memory-resident malware
- Encryption keys (ransomware)
- In-memory credentials and tokens

Preservation techniques:
- Memory capture
- Live response acquisition
- Controlled VM snapshotting

---

### 4. Preserve Non-Volatile Evidence

Includes:
- Disk images
- Log files
- Registry hives
- Cloud audit logs
- SaaS access logs
- Backup sets and snapshots

Requirements:
- Read-only access
- No normalization or parsing
- Original timestamps preserved
- Metadata retained

---

## Chain of Custody (Mandatory)

Chain of custody records **every interaction with evidence**.

### Minimum Required Fields

- Evidence ID
- Description
- Date & time (with timezone)
- Collector name and role
- Hash values
- Storage location
- Access and transfer history

> **A broken chain of custody weakens or invalidates evidence.**

---

## Evidence Integrity Verification

### Hashing Standards

- Use cryptographic hashes (SHA-256 minimum)
- Hash evidence:
  - At acquisition
  - After transfer
  - Before analysis
- Store hashes securely and separately

Hash mismatches must be:
- Investigated immediately
- Documented clearly
- Escalated if unresolved

---

## Preservation in Cloud & SaaS Environments

Cloud evidence preservation requires special handling:

- Export logs in **original/native formats**
- Preserve metadata (actor IDs, IPs, timestamps)
- Document APIs and export methods used
- Capture tenant, subscription, and account context
- Record original log retention settings

Avoid:
- Rehydration before preservation
- Normalization prior to hashing
- Manual copy-paste exports

---

## Physical Device & Environmental Preservation

Some investigations involve **physical devices** vulnerable to **wireless access, remote wiping, or environmental damage**.

These controls are mandatory in:
- Mobile forensics
- Insider investigations
- Fraud cases
- Law-enforcement-assisted matters

---

### Device Isolation & RF Protection

Devices capable of wireless communication must be isolated to prevent:

- Remote wiping
- Remote tampering
- Data alteration via network connectivity

Approved methods:
- Enable airplane mode (only if device is unlocked and stable)
- Power down devices when encryption state allows
- Use **Faraday bags or RF-shielded containers**
- Remove SIM cards (documented and photographed)

---

### Mobile Device Preservation Considerations

Mobile devices require **case-by-case decisions**:

**Powered ON**
- Preserve volatile data
- Maintain battery charge
- Prevent network connectivity

**Powered OFF**
- Do not power on without forensic justification
- Prevent automatic OS updates or sync

Additional controls:
- Disable biometric unlock if legally permitted
- Prevent MDM-triggered remote wipes
- Preserve SIM, eSIM, and associated metadata

---

### Removable Media & Peripheral Preservation

Removable storage must be preserved using:

- Hardware write blockers
- Read-only mounting
- Immediate hashing
- Anti-static, labeled storage

Applies to:
- USB flash drives
- SD cards
- External HDD/SSD
- Cameras and IoT storage

---

### Environmental & Storage Controls

Preserved evidence must be stored:

- In temperature-controlled environments
- Away from moisture and magnetic fields
- With mobile battery levels maintained
- Using tamper-evident seals

Environmental degradation can result in **data loss or corruption**.

---

### Documentation & Scene Recording

Before evidence movement:

- Photograph devices in original state
- Record power status, screen state, cables, peripherals
- Document serial numbers, labels, visible damage
- Maintain time-stamped records

Photographic documentation strengthens **chain of custody and courtroom defensibility**.

---

## Tools Commonly Used for Preservation

### Disk & Image Preservation
- FTK Imager – Disk and memory imaging  
- Guymager – Linux disk imaging  
- dcfldd / dc3dd – Block-level imaging with hashing  
- X-Ways Forensics – Fast, reliable disk preservation  

---

### Memory & Volatile Evidence
- DumpIt  
- Magnet RAM Capture  
- Belkasoft RAM Capturer  
- AVML / LiME  

---

### Live Response & Artifact Preservation
- Velociraptor  
- DFIR ORC  
- KAPE (artifact staging only)  

---

### Enterprise & Mobile Evidence Platforms
- Magnet AXIOM / Magnet ACQUIRE  
- Belkasoft Evidence Center  
- EnCase Forensic  
- Cellebrite UFED  
- Oxygen Forensic Detective  

---

## Common Preservation Failures (Observed in Real Incidents)

- Logging into systems without documentation
- Running analysis tools before hashing
- Failing to capture volatile evidence
- Allowing routine admin activity to continue
- Missing short-retention cloud logs
- Weak or missing chain of custody records

---

## Outputs of the Preservation Phase

By the end of preservation, investigators must have:

- Evidence secured and isolated
- Hash values recorded and verified
- Chain of custody initiated and maintained
- Legal and compliance requirements addressed
- Clean handoff to the Collection phase

---

## Authoritative References (Preservation-Relevant)

- AboutDFIR – https://aboutdfir.com  
- DFIR.blog – https://dfir.blog  
- The DFIR Report – https://thedfirreport.com  
- SANS Digital Forensics – https://www.sans.org/digital-forensics/  
- This Week in 4n6 – https://thisweekin4n6.wordpress.com  
- Forensic Focus – https://www.forensicfocus.com  

---

## Relationship to Other Phases

- **Identification** determines *what* to preserve  
- **Preservation** protects *truth and integrity*  
- **Collection** acquires preserved evidence  
- **Analysis** depends entirely on preservation quality  

---

## Key Takeaway

> **You can recover from a wrong hypothesis.  
> You cannot recover from broken preservation.**

Strong preservation:
- Protects investigators
- Preserves truth
- Enables accountability
- Stands up in court
