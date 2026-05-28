# Methodology & Analysis Approach

**CTF:** Cross-Border Heavy  
**Case File:** OC-GH-2024-DR-0312  
**Author:** Micheal Oscar
**Date:** 27 May 2026

## Overview

This investigation focused on reconstructing an organized cross-border smuggling operation through detailed forensic analysis of a seized 2021 Toyota HiAce telematics ecosystem.

The analysis was conducted **exclusively** from the vehicle’s internal databases and telemetry as per the CTF rules. All findings were derived in a controlled Kali Linux forensic environment using strict read-only evidence handling procedures.

**Primary Objectives:**
- Reconstruct the full 11-run operational chronology
- Identify recurring movement patterns and corridor usage
- Analyze mechanical telemetry anomalies (especially payload variations)
- Correlate communications, Bluetooth, and GPS artifacts
- Map convoy coordination and co-conspirator attribution

## Evidence Acquisition

The source evidence was provided as an EnCase **E01** forensic image. Acquisition validation included:

- Verification of E01 file integrity using hashing
- Forensic mounting with `ewfmount`
- Read-only filesystem access
- Partition structure validation using `fdisk`

No modifications were made to the original evidence at any stage.

## Analysis Environment

- **Operating System:** Kali Linux (forensic workstation)
- **Evidence Handling:** Write-blocked analysis throughout

## Core Tools Used

| Tool          | Purpose                                      |
|---------------|----------------------------------------------|
| `ewfmount`    | Mounting EnCase E01 forensic images         |
| `sqlite3`     | Direct SQLite database querying and analysis |
| `exiftool`    | Metadata extraction from media and receipts |
| `strings`     | Slack space and unallocated artifact recovery |
| `grep`        | Pattern searching across logs and databases |
| `tree`        | Evidence directory structure mapping        |
| `fdisk`       | Filesystem partition validation             |
| Autopsy       | GUI-based carving and timeline analysis     |

## Evidence Enumeration

The mounted filesystem was systematically enumerated to locate:

- SQLite databases (`navigation.db`, `edr_events.db`, `phone_sync.db`, `system_log.db`)
- Raw GPS telemetry (`GPS_RAW_RUN11_20241213.nmea`)
- Media files (dashcam footage and receipt images)
- System logs and Bluetooth synchronization data

## Analytical Phases

### 1. Database Analysis
- Schema extraction and table mapping
- SQL queries for timeline reconstruction
- Recovery of deleted records and `deleted=1` flagged entries
- Write-Ahead Log (WAL) carving for deleted SMS fragments

### 2. GPS & Navigation Analysis
- Correlation of `navigation.db` with raw NMEA sentences
- Reconstruction of recurring routes, stop points, and border activities
- Validation of Warehouse B4 staging and Aflao border patterns

### 3. Mechanical Telemetry Analysis
- Detailed review of Event Data Recorder (EDR) and suspension control module logs
- Identification of recurring DTC `C1A00` (suspension anomaly) on return legs
- Correlation between cargo-door BCM events and chassis compression

### 4. Communication & Convoy Analysis
- Bluetooth pairing and RSSI-based proximity mapping
- Recovery and correlation of deleted messages from `phone_sync.db`
- Identification of co-location patterns with support vehicles

### 5. Cross-Domain Correlation
- Timeline merging across GPS, mechanical, communication, and system logs
- Detection of post-interdiction USB mount events and deletion attempts
- Establishment of "consciousness of guilt" indicators

## Reporting Standards

Findings were documented with:
- Clear separation between direct evidence and interpretation
- Confidence grading on key assertions
- Structured evidentiary tables and timelines
- Adherence to digital forensic best practices (inspired by NIST and ACPO principles)

This methodology ensured a rigorous, defensible, and transparent reconstruction of the smuggling operation based solely on the vehicle’s internal digital evidence.
