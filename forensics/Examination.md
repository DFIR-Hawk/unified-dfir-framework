# Examination Phase – Digital Forensics

## Purpose

The Examination phase involves **processing collected evidence to extract relevant artifacts**
while **preserving the integrity of the original evidence**.

Examination is a **controlled, technical reduction phase**:
- It prepares evidence for analysis
- It does not draw conclusions
- It does not modify originals

Errors during examination commonly result in:
- Evidence contamination
- Missed artifacts
- Timeline distortion
- Challenges to forensic credibility

Examination is performed **only on verified working copies**, never on original evidence.

---

## When Examination Is Triggered

Examination begins when:

- Evidence has been collected and hashed
- Chain of custody is intact
- Working copies are created and verified
- Examination scope is defined
- Legal constraints are confirmed

> **If originals are touched, examination has failed.**

---

## Core Objectives

The Examination phase ensures:

1. Evidence is processed **without altering originals**
2. Relevant artifacts are **identified and extracted**
3. Noise is reduced while preserving context
4. Metadata and timestamps remain intact
5. Outputs are repeatable and defensible

---

## Key Examination Principles (Field-Tested)

### Work Only on Verified Copies
- Originals remain sealed
- Working copies are hashed and logged
- Any transformation happens on copies only

### Reduce, Do Not Interpret
- Extract artifacts
- Normalize formats
- Decode structures
- **Do not conclude or attribute**

### Preserve Context
- Keep directory structures
- Preserve timestamps
- Retain surrounding artifacts
- Avoid cherry-picking

---

## Practical Examination Workflow

### 1. Prepare Working Copies

Before examination:

- Create forensic working copies
- Verify hashes against originals
- Record copy creation in custody logs
- Use write-protected mounts where applicable

---

### 2. File System & Structure Examination

Objectives:
- Identify file systems
- Locate hidden or deleted content
- Extract metadata

Activities:
- Partition analysis
- File carving
- Deleted file recovery
- Alternate data stream identification

---

### 3. Artifact Extraction & Parsing

Extract forensic artifacts such as:

- Registry hives
- Event logs (EVTX)
- Prefetch files
- Shimcache / Amcache
- Browser history and cache
- Email databases
- Application-specific logs

Artifacts should be:
- Parsed using validated tools
- Stored separately from raw images
- Hash-verified after extraction

---

### 4. Timeline Preparation (Pre-Analysis)

Create timelines to:

- Understand sequencing
- Identify gaps
- Support later correlation

This step prepares data but **does not infer attacker intent**.

---

### 5. Data Normalization & Decoding

Activities include:
- Decompression
- De-obfuscation
- Format conversion (binary → readable)
- Log normalization

Ensure:
- Original data remains untouched
- Transformations are documented
- Intermediate outputs are retained

---

### 6. Malware & Suspicious Object Handling

During examination:

- Identify suspicious binaries/scripts
- Do **not execute** samples on production systems
- Hash and label malware
- Isolate samples in controlled environments

Deep reverse engineering belongs to **Malware Analysis**, not Examination.

---

## Examination by Evidence Type

### Disk & File System Examination

Focus areas:
- File creation/modification/access timestamps
- Deleted and orphaned files
- Persistence mechanisms
- Evidence of wiping or anti-forensics

---

### Memory Examination

Extract:
- Process lists
- Injected code
- Network connections
- Credential material
- Encryption keys (when present)

Memory examination often reveals:
- Fileless malware
- In-memory execution
- Lateral movement artifacts

---

### Log Examination

Examine:
- Windows Event Logs
- Linux audit logs
- Application logs
- Authentication records

Ensure:
- Timezone normalization
- Source correlation
- Log integrity verification

---

### Cloud & SaaS Examination

Examine:
- API call sequences
- Identity activity patterns
- Resource access events
- Configuration changes

Preserve:
- Native timestamps
- Actor identifiers
- Correlation IDs

---

### Mobile Device Examination

Extract:
- Call logs
- Messages
- App databases
- Location artifacts
- Media metadata

Ensure:
- Extraction format preserved
- No reprocessing of originals
- Legal scope respected

---

## Tools Commonly Used for Examination

### Disk & File System Examination

- **Autopsy / Sleuth Kit** – Open-source forensic analysis  
  https://www.sleuthkit.org

- **X-Ways Forensics** – Fast, efficient disk analysis  
  https://www.x-ways.net/forensics/

- **EnCase Forensic** – Enterprise forensic examination  
  https://www.opentext.com/products/encase-forensic

- **Magnet AXIOM** – Unified disk, memory, mobile examination  
  https://www.magnetforensics.com

- **Belkasoft Evidence Center** – Multi-source forensic analysis  
  https://belkasoft.com

---

### Memory Examination

- **Volatility 3** – Memory artifact extraction  
  https://github.com/volatilityfoundation/volatility3

- **Rekall** – Advanced memory analysis  
  http://www.rekall-forensic.com

- **MemProcFS** – Memory exposed as file system  
  https://github.com/ufrisk/MemProcFS

---

### Artifact Parsing & Timeline Tools

- **Plaso (log2timeline)** – Multi-source timeline generation  
  https://github.com/log2timeline/plaso

- **Timesketch** – Collaborative timeline analysis  
  https://github.com/google/timesketch

- **Eric Zimmerman Tools** – Windows artifact parsers  
  https://ericzimmerman.github.io

- **Hayabusa** – Windows event log examination  
  https://github.com/Yamato-Security/hayabusa

---

### Log & Data Examination

- **Wireshark** – Packet and protocol examination  
  https://www.wireshark.org

- **NetworkMiner** – Passive network artifact extraction  
  https://www.netresec.com

- **ELK / OpenSearch** – Large-scale log examination  
  https://www.elastic.co  
  https://opensearch.org

---

### Mobile Examination

- **Cellebrite Physical Analyzer**  
  https://www.cellebrite.com

- **Oxygen Forensic Detective**  
  https://www.oxygen-forensic.com

- **Magnet AXIOM Mobile**  
  https://www.magnetforensics.com

---

## Common Examination Failures (Real Incidents)

- Examining original evidence
- Mixing examination with analysis
- Overwriting metadata
- Poor timestamp normalization
- Ignoring negative findings
- Inadequate documentation

---

## Documentation Requirements

Every examination step must record:

- Evidence ID and working copy reference
- Tool name and version
- Actions performed
- Artifacts extracted
- Output locations
- Hashes of extracted data

Documentation ensures **repeatability and defensibility**.

---

## Outputs of the Examination Phase

By the end of examination, investigators must have:

- Extracted forensic artifacts
- Prepared timelines and datasets
- Normalized and decoded data
- Verified artifact integrity
- Clean inputs for Analysis

---

## Authoritative Blogs & References (Examination-Focused)

- AboutDFIR – https://aboutdfir.com  
- DFIR.blog – https://dfir.blog  
- The DFIR Report – https://thedfirreport.com  
- This Week in 4n6 – https://thisweekin4n6.wordpress.com  
- SANS Digital Forensics – https://www.sans.org/digital-forensics/  
- Forensic Focus – https://www.forensicfocus.com  
- Eric Zimmerman Blog – https://ericzimmerman.github.io  

---

## Relationship to Other Phases

- **Collection** acquires evidence
- **Examination** extracts artifacts
- **Analysis** interprets findings
- **Reporting** communicates conclusions

Examination is the **technical bridge between evidence and truth**.

---

## Key Takeaway

> **Examination is about discipline, not conclusions.**

Strong examination:
- Preserves forensic integrity
- Reduces noise
- Enables accurate analysis
- Protects investigators in court
