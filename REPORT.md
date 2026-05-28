# Operational Forensic Report

**Project:** Cross-Border Heavy  
**Case File:** OC-GH-2024-DR-0312  
**Classification:** Organized Crime / Cross-Border Smuggling / Vehicle Telematics Forensics  
**Primary Subject:** Kwame Boateng Asare  
**Target Asset:** 2021 Toyota HiAce

## Executive Summary

This report presents the complete digital forensic reconstruction of an 11-run cross-border smuggling operation between Tema Industrial Area (Warehouse B4) and the Aflao border, conducted between 4 October 2024 and 13 December 2024.

All findings were derived **exclusively** from the vehicle’s internal databases and telemetry as per CTF rules.

---

## Core Evidence Sources
- `navigation.db`
- `edr_events.db` (Event Data Recorder + Suspension logs)
- `phone_sync.db` (Bluetooth + SMS artifacts)
- `system_log.db`
- Raw NMEA telemetry
- Carved deleted records & WAL files

*(Full evidence list and analysis in sections below)*

## Comprehensive 11-Run Timeline

| Run ID | Date          | Key Forensic Observations |
|--------|---------------|---------------------------|
| Run 1  | 04 Oct 2024   | Baseline route established |
| Run 2  | 11 Oct 2024   | First suspension anomaly |
| Run 3  | 18 Oct 2024   | `deleted=1` flags appear |
| ...    | ...           | ... |
| Run 11 | 13 Dec 2024   | NACOC interdiction + panic deletion attempt ("Delete everything") |

> **Full detailed timeline and artifact analysis is continued in the original detailed sections...**

# Operational Forensic Report

**Project:** Cross-Border Heavy

**Case File:** OC-GH-2024-DR-0312

**Classification:** Organized Crime / Cross-Border Smuggling / Vehicle Telematics Forensics

**Primary Subject:** Kwame Boateng Asare

**Target Asset:** 2021 Toyota HiAce

---

## 1. Executive Summary

This forensic report documents the digital and mechanical reconstruction of an eleven-run cross-border smuggling operation executed between the Tema Industrial Area and the Aflao border corridor from 4 October 2024 through 13 December 2024.

The target organization utilized a legitimate textile logistics cover to mask undeclared inbound contraband shipments. Forensic analysis reveals that the operation relied on highly structured convoy discipline, synchronized inter-device communications, route intelligence gathering, staged fuel stops, repeated border transfer windows, and deliberate post-interdiction data sanitization attempts.

The operational timeline and mechanics were reconstructed exclusively from non-volatile flash memory and vehicle-derived telemetry extracted from the infotainment and telematics ecosystem of a seized 2021 Toyota HiAce.

### Core Evidentiary Domains

The forensic findings are constructed upon the convergence of multiple independent data streams:

* **Spatial & Kinematic Telemetry:** GPS route history, raw NMEA-0183 telemetry, Event Data Recorder (EDR) high-G deceleration logs, and suspension control module diagnostic data.
* **System & Connectivity Artifacts:** Internal Bluetooth synchronization logs, SQLite database slack space parsing (recovered SMS artifacts), USB bus event logging, and keyfob/Body Control Module (BCM) cargo-door actuation events.
* **Corroborative Field Data:** Automated parking camera metadata, fuel receipt timestamps, and dashcam optical media.

The operation ceased on 13 December 2024 (Run 11) following an anomaly-based interdiction by the Narcotics Control Commission (NACOC) at the Aflao border, triggered by persistent physical discrepancies in return-leg vehicle dynamics.

---

## 2. Evidence Inventory & Forensic Image Verification

All digital evidence was acquired using write-blocked hardware interfaces and verified via SHA-256 cryptographic hashing to ensure data integrity prior to analysis.

| Source Data Store | Technical Context & Extracted Artifacts |
| --- | --- |
| `navigation.db` | Contains system route history, targeted GPS track logs, physical destinations, and point-of-interest (POI) queries. |
| `edr_events.db` | Event Data Recorder telemetry, high-G deceleration events, body control module states, and suspension height sensor logs. |
| `phone_sync.db` | Bluetooth pairing history, peripheral device profiles, localized text message logs, and call detail records (CDRs). |
| `system_log.db` | Linux-kernel system daemons, USB mass storage mount events, file deletion commands, and power-cycle events. |
| **NMEA Telemetry** | Raw GPS streams providing un-smoothed, real-time spatial verification for Run 11. |
| **Dashcam Media** | Non-volatile flash storage capturing continuous visual forward-facing route verification. |
| **Optical Media** | Closed-Circuit Television (CCTV) capture from staging facilities validating physical cargo orientation. |
| **Metadata Ingestion** | Transactional timestamps from fuel distribution receipts used to anchor spatial-temporal tracking. |

---

## 3. Comprehensive Forensic Chronology

The following matrix details the continuous, multi-run operational cadence reconstructed from the target vehicle's internal logs. All timestamps are anchored to localized UTC.

| Run ID | Execution Date | Origin Terminus | Terminal Boundary Activity | Return Payload Profile | Analytical Forensic Inference |
| --- | --- | --- | --- | --- | --- |
| **Run 1** | 04 Oct 2024 | Warehouse B4 | Aflao Border Transfer | Heavy Inbound Displacement | Baseline transit establishing corridor discipline. |
| **Run 2** | 11 Oct 2024 | Warehouse B4 | Aflao Border Transfer | Suspension Overload Detected | Operational replication confirming transit parameters. |
| **Run 3** | 18 Oct 2024 | Warehouse B4 | Aflao Border Transfer | DTC C1A00 Initialization | Implementation of deliberate database deletion flags (`deleted=1`). |
| **Run 4** | 25 Oct 2024 | Warehouse B4 | Aflao Border Transfer | Return Mass Discrepancy | Scaled payload volume exceeding baseline averages. |
| **Run 5** | 01 Nov 2024 | Warehouse B4 | Aflao Border Transfer | Suspension Anomaly Registered | Highly regularized temporal and route standardization. |
| **Run 6** | 08 Nov 2024 | Warehouse B4 | Aflao Border Transfer | Kinetic Velocity Degradation | Extended static boundary duration; increased cargo mass. |
| **Run 7** | 15 Nov 2024 | Warehouse B4 | Aflao Border Transfer | Mass Profile Elevating | Intercepted text traffic explicitly references inbound volume. |
| **Run 8** | 22 Nov 2024 | Warehouse B4 | Aflao Border Transfer | Severe Mechanical Overload | Axle displacement operating at critical load-limit threshold. |
| **Run 9** | 29 Nov 2024 | Warehouse B4 | Aflao Border Transfer | Repeated DTC Generation | Active execution of route-history suppression commands. |
| **Run 10** | 06 Dec 2024 | Warehouse B4 | Aflao Border Transfer | Co-Location Validation | Inter-vehicle network data confirms optimized fleet cohesion. |
| **Run 11** | 13 Dec 2024 | Warehouse B4 | NACOC Interdiction Site | Emergency Deceleration Event | Operational cessation; high-G braking and emergency erasure attempt. |

---

## 4. Architectural Analysis & Pre-Operational Reconnaissance

### Spatial Staging

The target asset systematically initiated transits from a fixed logistics facility within the Tema Industrial Area, designated internally within database schemas as **Warehouse B4**. External optical metadata verified that vehicle staging occurred within rigid temporal windows prior to deployment.

### Route Intelligence & Surveillance Countermeasures

Parsing of unallocated sectors within the `navigation.db` string cache recovered the following high-priority Point-of-Interest (POI) queries executed by the user interface:

* `“checkpoint schedule aflao road”`
* `“police patrol time tema aflao night”`
* `“weighbridge hours sogakope”`

```
[POI Queries Extracted] ───> Establishes Intentional Route Intelligence Gathering
                                      │
[Weighbridge Avoidance] ───> Confirms Pre-Meditated Law Enforcement Evasion Planning

```

---

## 5. Network Cohesion & Convoy Architecture

Analysis of the infotainment system's transceiver logs (`phone_sync.db`) identified persistent, synchronized co-location patterns involving the target asset and two peripheral vehicles. The network configuration operated under a strict functional hierarchy:

| Asset Classification | Assigned Operational Role | System Identifier Trait |
| --- | --- | --- |
| **Toyota HiAce** | Primary Contraband Transport Vector | Subject: Kwame Boateng Asare |
| **Mercedes Sprinter** | Forward Logistic / Spacing Support | Identity Token: Adjoa |
| **Toyota Hilux** | Tactical Escort / Counter-Surveillance | Identity Token: Nii |

The internal Bluetooth chipset logged repeated, synchronous connection requests and Received Signal Strength Indicator (RSSI) spikes corresponding to the unique MAC addresses of the co-conspirator devices, confirming persistent physical proximity along the transit corridor.

---

## 6. Run-by-Run Forensic Breakdown

### Run 1: 04 October 2024

* **Sequence Profile:** Departure from Warehouse B4; localized fuel replenishment at Shell Sogakope facility; arrival at Aflao border zone.
* **Telemetry Verification:** `navigation.db` records consistent velocity tracking. Cargo-door sensor arrays log open/close flags at the terminus point, immediately followed by rear suspension compression changes.
* **Analytical Conclusion:** Commencement of operational routing establishing baseline corridor signatures.

### Run 2: 11 October 2024

* **Sequence Profile:** Execution of identical spatial routing and fuel distribution nodes.
* **Telemetry Verification:** The vehicle's Suspension Control Module registers the first instance of Diagnostic Trouble Code (DTC) `C1A00` (Suspension Control Anomaly), indicating inbound mass asymmetry.
* **Analytical Conclusion:** Increased operational confidence with rising payload weights.

### Run 3: 18 October 2024

* **Sequence Profile:** Coordinated multi-vehicle transit with tactical spacing.
* **Telemetry Verification:** System logs reveal database management alterations. Route entries within `navigation.db` are flagged with a boolean value of `deleted=1`.
* **Analytical Conclusion:** Initial deployment of physical operational security (OPSEC) masking protocols.

### Run 4: 25 October 2024

* **Sequence Profile:** Inbound heavy-load transportation.
* **Telemetry Verification:** Inbound kinematic deceleration data shows a marked reduction in braking efficiency, proportional to an elevated return-leg mass index.
* **Analytical Conclusion:** Scaled increase in contraband density/volume.

### Run 5: 01 November 2024

* **Sequence Profile:** Standardized corridor loop.
* **Telemetry Verification:** Automated alignment of BCM cargo-door timestamps with localized commercial transaction receipts at Sogakope.
* **Analytical Conclusion:** Normalization of smuggling workflow into a highly predictable, mechanical routine.

### Run 6: 08 November 2024

* **Sequence Profile:** Extended border stationing followed by return transit.
* **Telemetry Verification:** Long-duration static idling recorded within NMEA tracking loops. Return-leg hill ascent speeds show severe engine load degradation.
* **Analytical Conclusion:** Substantial increase in inbound cargo volume or weight profiles.

### Run 7: 15 November 2024

* **Sequence Profile:** Network-coordinated route navigation.
* **Telemetry Verification:** Forensic carving of the SMS database unallocated blocks recovered the following raw string payload:
> *"Cargo loaded at KA. 22 units. Move at 9."*


* **Analytical Conclusion:** Direct, unambiguous confirmation of real-time multi-vehicle operational coordination.

### Run 8: 22 November 2024

* **Sequence Profile:** Heavy-mass payload return phase.
* **Telemetry Verification:** Continuous activation of DTC `C1A00`. The suspension height sensors record a constant voltage floor, establishing structural bottoming-out of the rear axle assembly.
* **Analytical Conclusion:** Vehicle transport physical parameters diverge completely from standard textile transport specifications.

### Run 9: 29 November 2024

* **Sequence Profile:** Enhanced electronic countermeasure enforcement.
* **Telemetry Verification:** System events register a sequence of manual cache-clearing commands targeting the internal infotainment navigation application.
* **Analytical Conclusion:** Operators demonstrate acute awareness of forensic vulnerability and exposure risks.

### Run 10: 06 December 2024

* **Sequence Profile:** Highly optimized tactical transit window.
* **Telemetry Verification:** Bluetooth proximity logs capture automated peer-to-peer handshakes with co-conspirator MAC addresses at precise interval boundaries.
* **Analytical Conclusion:** Smuggling network operating at peak logistics efficiency.

### Run 11: 13 December 2024

* **Sequence Profile:** Tactical law enforcement interdiction and operational collapse.
* **Telemetry Verification:** EDR logs record a High-G Emergency Deceleration Event (panic braking).
* **Data Destruction Activity:** `system_log.db` recorded an unauthenticated USB Mount event (`/dev/sdb1`) exactly $43\text{ seconds}$ post-deceleration. System logs capture a user-initiated shell command attempting to execute a mass file-export and subsequent unlinked file erasure (`rm -rf` equivalents or database vacuuming).
* **Recovered Communications:** Carving of the SQLite Write-Ahead Log (WAL) recovered a volatile SMS fragment transmitted at the exact time of the stop:
> *"Police stopped me at Aflao. They have the van. Delete everything."*


* **Received Response:**
> *"Say nothing. You were transporting fabric."*


* **Analytical Conclusion:** Abrupt operational cessation. The convergence of sudden deceleration, desperate file deletion commands, and explicit text artifacts provides definitive proof of a failed evidence-destruction attempt during active interdiction.

---

## 7. Core Evidentiary Findings

### Finding 1: Systemic Undeclared Inbound Payload Anomalies

* **Classification:** Critical / High Evidentiary Weight
* **Technical Matrix:**

$$\text{Outbound Mass: } 284\text{–}357 \text{ kg } \longleftrightarrow \text{Inbound Mass: } 671\text{–}836 \text{ kg (Exceeding Nominal Gross Axle Weight Rating)}$$


* **Diagnostic Verification:** Persistent registration of Diagnostic Trouble Code (DTC) `C1A00` within the Suspension Control Module. The timestamp of the DTC initialization matches the exact delta-t of the cargo door actuation sequence at the border terminus.
* **Forensic Conclusion:** The vehicle’s mechanical telemetry objectively refutes the declared cargo manifest (lightweight textiles), establishing a systemic pattern of heavy, unmanifested inbound cargo importation.

### Finding 2: Structured Multi-Vehicle Convoy Cohesion

* **Classification:** Critical
* **Technical Matrix:** Continuous co-location mapping via Bluetooth Peripheral RSSI tracking.
* **Forensic Interpretation:** The repetitive, multi-run synchronization of unique MAC identifiers across distinct vehicle types (`Mercedes Sprinter` and `Toyota Hilux`) establishes that the transit behavior was a highly structured, organized fleet operation rather than isolated transport events.

### Finding 3: Border Terminus Cargo Transoperability

* **Classification:** Critical
* **Technical Matrix:** Discrete state changes within the Body Control Module tracking array:

$$\text{Event Flag: } \texttt{CARGO\_SLIDING\_DOOR\_LEFT} \longrightarrow \text{State: } \texttt{UNLOCKED}$$


* **Forensic Interpretation:** These state changes occurred exclusively within localized border-side coordinates during static intervals. The immediate subsequent data entries show a profound drop in suspension clearance and an immediate trigger of load-fault diagnostics, providing direct physical proof of border-side contraband loading.

### Finding 4: Post-Interdiction Data Manipulation ("Consciousness of Guilt")

* **Classification:** Critical
* **Technical Matrix:** Verification of unauthorized external I/O hardware mounting sequences during the physical interdiction window.
* **Forensic Interpretation:** The simultaneous occurrence of a high-G braking event, manual flash-drive mounts, targeted database clearing commands, and carved text transmissions stating *"Delete everything"* legally and technically establishes an intentional, coordinated attempt to destroy digital evidence.

### Finding 5: Pre-Meditated Law Enforcement Avoidance

* **Classification:** High
* **Technical Matrix:** Extraction of deleted plain-text string fragments from the infotainment system's cache storage.
* **Forensic Interpretation:** Targeted queries regarding police patrol routing, weighbridge operational parameters, and boundary inspection intervals confirm that the operator possessed prior knowledge of the illicit nature of the cargo and engaged in active reconnaissance to bypass state enforcement nodes.

---

## 8. Technical Telemetry Analysis

The vehicle's mechanical and spatial performance metrics vary fundamentally depending on the direction of travel, as detailed in the matrix below.

```
       Outbound Leg (Declared Textile Profile)
       ├─ Mass: 294–349 kg
       ├─ Chassis Clearance: Nominal / Standard
       └─ Fault Registers: None (System Stable)

       Inbound Leg (Contraband Profile)
       ├─ Mass: 680–836 kg (Overloaded)
       ├─ Chassis Clearance: Critical Compression
       └─ Fault Registers: Persistent DTC C1A00 Generation

```

Parsing of the raw NMEA-0183 sentences (specifically `$GPRMC` and `$GPGGA` sentences) independently validated all database-derived route tracking, confirming that the internal system clock and spatial coordinates were completely synchronized across all onboard vehicle arrays.

---

## 9. Forensic Attribution & Network Roles

Based on unique hardware IDs, synced telecommunication profiles, and physical telemetry, the following individuals are securely linked to specific operational roles within this illicit enterprise:

* **Kwame Boateng Asare (Primary Operator):** Direct physical attribution established via biometric/keyfob authentication sequences, constant Bluetooth association, and primary operation of the steering/braking interfaces during Run 11.
* **Kofi Amankwah (Warehouse Handler):** Linked via inbound SMS routing layers; coordinated the origin staging sequences and verified physical warehouse departures at Warehouse B4.
* **Adjoa Sarpong (Logistics Support):** Linked via persistent peripheral device registration (`phone_sync.db`) and synchronized spatial tracking of the support vehicle.
* **Nii Lantey Kwei (Escort Vector):** Attributed via recurrent co-location profiles and ahead-of-route reconnaissance tracking patterns.
* **"Papa Kofi Mensah" (Command & Control):** Identified as the authoring entity of the remote commands directing the physical movement of the convoy and ordering the post-interdiction data sanitization process.

---

## 10. Expert Witness Forensic Conclusion

The integrated analysis of the digital and mechanical evidence recovered from the target 2021 Toyota HiAce establishes an airtight, multi-vector profile of a sophisticated, eleven-run contraband smuggling operation.

The convergence of physical chassis stress logging, localized cargo-door access tracking, and carved database communication blocks completely refutes any defense asserting legitimate, baseline commercial textile transportation. The data confirms a highly coordinated, organized criminal network utilizing advanced technical awareness, counter-surveillance planning, and deliberate post-interdiction evidence destruction protocols.

### Forensic Integrity Statement

This report reflects the analytical findings derived strictly from bit-stream forensic copies of the seized digital media. All analysis was conducted in a certified, write-blocked environment using industry-standard, validated forensic tools. The findings, technical inferences, and structural correlations detailed herein are accurate to a reasonable degree of scientific and technical certainty based on current automotive telematics and digital forensic methodologies.


## Conclusion
The recovered telemetry, Bluetooth co-location data, cargo door events, and carved communications establish a clear, well-organized smuggling network with strong consciousness of guilt indicators.

**Report Prepared By:** Micheal Oscar  
**CTF:** Cross-Border Heavy by Hive Consult & RedHat Pentester
