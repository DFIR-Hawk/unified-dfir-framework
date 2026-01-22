# Collection Phase – Digital Forensics

## Purpose

The Collection phase is the **forensically sound acquisition of preserved evidence**
while maintaining **integrity, chain of custody, and legal admissibility**.

Collection is where most DFIR mistakes occur — not due to lack of tools,
but due to **breaking preservation controls**.

Collection begins **only after Identification and Preservation are complete**.

---

## When Collection Is Triggered

Collection begins when:

- Evidence sources are identified and preserved
- Legal and organizational authorization is confirmed
- Chain of custody is initiated
- Business impact of acquisition is understood
- Collection objectives are documented

> **If preservation is incomplete, collection must stop.**

---

## Core Objectives

The Collection phase ensures:

1. Evidence is acquired **without modification**
2. Integrity is **verifiable and repeatable**
3. Chain of custody is **maintained**
4. Order of volatility is **respected**
5. Actions are **legally defensible**

---

## Key Collection Principles (Field-Tested)

### Collect What Is Necessary
Over-collection:
- Increases legal exposure
- Slows investigations
- Creates unnecessary data-handling risk

Collection must align with **investigation hypotheses**, not curiosity.

---

### Respect Order of Volatility

1. Memory (RAM)
2. Running processes and network connections
3. Temporary and volatile files
4. Disk data
5. Backups and archives

---

### Never Collect on Original Evidence

- Use read-only access
- Use hardware write blockers
- Use validated forensic tools
- Avoid native OS copy commands unless approved

---

## Practical Collection Workflow

### 1. Validate Preservation State

Before collecting:

- Confirm isolation of evidence
- Confirm legal authority
- Confirm chain of custody entries
- Confirm logging and time synchronization
- Confirm tool readiness and versions

---

### 2. Volatile Evidence Collection

Volatile evidence provides **context attackers attempt to erase**.

Examples:
- Memory dumps
- Running processes
- Active network connections
- Loaded drivers
- In-memory credentials and encryption keys

Guidelines:
- Collect volatile evidence first
- Record system time, uptime, and timezone
- Minimize commands executed
- Document every action

---

### 3. Non-Volatile Evidence Collection

Includes:
- Disk images
- Logical file collections
- Registry hives
- Application and security logs
- Cloud and SaaS audit logs

Guidelines:
- Prefer bit-for-bit imaging when feasible
- Use targeted logical collection for scoped cases
- Preserve timestamps and metadata
- Hash before and after acquisition

---

### 4. Integrity Validation

- Generate cryptographic hashes (SHA-256 minimum)
- Verify hashes after transfer
- Record values in chain of custody
- Investigate discrepancies immediately

---

### 5. Secure Storage of Collected Evidence

Collected evidence must be:
- Stored in access-controlled repositories
- Encrypted at rest
- Clearly labeled with evidence IDs
- Access-logged and audited

---

## Collection by Evidence Type

### Endpoint – Disk Collection

**Preferred**
- Full physical disk imaging
- Partition-level imaging
- Targeted artifact collection (KAPE-style)

**Avoid**
- Drag-and-drop copying
- Booting compromised OS for acquisition
- Cleanup or remediation tools during collection

---

### Endpoint – Memory Collection

Collect memory when:
- Ransomware or malware suspected
- Credential theft suspected
- Fileless or rootkit activity suspected

Document:
- OS version and kernel
- Uptime
- Tool name and version
- Hash of memory image

---

### Network & Log Collection

Collect:
- Firewall, proxy, and IDS logs
- VPN authentication logs
- DNS and DHCP logs
- Packet captures (when available)

Preserve:
- Native format
- Timezone context
- Log source metadata

---

### Cloud & SaaS Evidence Collection

Cloud collection must be:
- API-driven
- Logged
- Performed with least privilege

Collect:
- Cloud audit logs
- Identity sign-in logs
- API activity
- Object storage access logs
- Email and collaboration audit logs

Document:
- Tenant and subscription IDs
- Time ranges
- Tools or APIs used

---

### Mobile Device Collection

Collection depends on:
- Power state
- Encryption status
- Legal authorization
- Device ownership

Guidelines:
- Maintain RF isolation
- Use forensic-grade tools only
- Preserve original extraction formats
- Do not bypass locks without authorization

---

### Removable Media Collection

- Use hardware write blockers
- Image entire media where possible
- Hash immediately
- Preserve physical labels and markings

---

## Tools Commonly Used for Collection

### Disk & File Collection (Professional & Open Source)

- **FTK Imager** – Disk and memory imaging  
  https://accessdata.com

- **Guymager** – High-performance Linux disk imaging  
  https://guymager.sourceforge.io

- **dcfldd / dc3dd** – Enhanced dd with hashing  
  https://github.com/adulau/dcfldd

- **X-Ways Forensics** – Fast and efficient imaging & analysis  
  https://www.x-ways.net/forensics/

- **Autopsy / Sleuth Kit** – Open-source forensic platform  
  https://www.sleuthkit.org

---

### Memory & Volatile Evidence Collection

- **DumpIt** – Rapid Windows memory acquisition  
  https://www.comae.com/dumpit/

- **Magnet RAM Capture**  
  https://www.magnetforensics.com

- **Belkasoft RAM Capturer**  
  https://belkasoft.com/ram-capturer

- **AVML** – Linux memory acquisition  
  https://github.com/microsoft/avml

- **LiME** – Linux kernel memory extractor  
  https://github.com/504ensicsLabs/LiME

---

### Live Response & Targeted Collection

- **Velociraptor** – Fleet-scale live response and collection  
  https://github.com/Velocidex/velociraptor

- **DFIR ORC** – Windows forensic artifact collection  
  https://dfir-orc.github.io

- **KAPE** – Targeted artifact staging  
  https://www.kroll.com/en/services/cyber-risk/incident-response-litigation-support/kape

- **GRR Rapid Response**  
  https://github.com/google/grr

- **osquery / FleetDM**  
  https://osquery.io  
  https://github.com/fleetdm/fleet

---

### Cloud & SaaS Collection

- **AWS CloudTrail / GuardDuty**
- **Microsoft Entra ID / Purview Audit Logs**
- **Google Workspace Audit Logs**
- **Turbinia** – Scalable cloud forensic processing  
  https://github.com/google/turbinia

---

### Mobile Device Collection

- **Cellebrite UFED**  
  https://www.cellebrite.com

- **Magnet AXIOM Mobile**  
  https://www.magnetforensics.com

- **Oxygen Forensic Detective**  
  https://www.oxygen-forensic.com

---

## Common Collection Failures (Observed in Incidents)

- Collecting before preservation
- Skipping volatile evidence
- Using unvalidated tools
- Missing hash verification
- Poor documentation
- Collecting excessive unrelated data

---

## Documentation Requirements

Each collection action must record:

- Evidence ID
- Date & time (with timezone)
- Collector name and role
- Tool name and version
- Commands/actions executed
- Hash values
- Storage location

---

## Outputs of the Collection Phase

By the end of collection, investigators must have:

- Forensically acquired evidence
- Verified integrity
- Updated chain of custody
- Secure evidence storage
- Clean inputs for Examination

---

## Authoritative Blogs & Resources (Collection-Focused)

- AboutDFIR – https://aboutdfir.com  
- DFIR.blog – https://dfir.blog  
- The DFIR Report – https://thedfirreport.com  
- This Week in 4n6 – https://thisweekin4n6.wordpress.com  
- SANS Digital Forensics – https://www.sans.org/digital-forensics/  
- Forensic Focus – https://www.forensicfocus.com  
- Magnet Forensics Blog – https://www.magnetforensics.com/blog/  
- Belkasoft Blog – https://belkasoft.com/blog  

---

## Relationship to Other Phases

- **Identification** → what to collect  
- **Preservation** → protect evidence  
- **Collection** → acquire evidence  
- **Examination** → process collected data  

Collection is the **bridge between preservation and analysis**.

---

## Key Takeaway

> **Collection is not about speed.  
> It is about correctness, repeatability, and defensibility.**

A slow, correct collection always beats a fast, broken one.
