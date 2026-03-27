# Architecture Components

This section describes each core component of the Nyroxis platform and how they work together to deliver private, offline, tamper-resistant security.

---

## 1. Nyroxis Agent

The lightweight background service responsible for:
- Monitoring processes, network connections, file changes, and privilege activity
- Capturing Windows Event Log entries (Security, System, Application)
- Monitoring PowerShell and script execution
- Normalizing event data in real time
- Encrypting every event immediately before writing

Properties:
- ~57 MB RAM, ~0.1% CPU
- Silent Windows service
- Fully offline — nothing leaves the device

---

## 2. Nyroxis Intelligence

The detection and correlation engine:
- **27 detection rules** — known threat patterns in individual events
- **12 correlation rules** — patterns across related events over time
- **2 chain rules** — multi-stage attack sequence detection

Properties:
- ~87 MB RAM, ~1.8% CPU
- Fully extensible — security professionals can write and deploy custom rules in JSON format
- Raises immediate alerts on rule matches
- Stores findings in dedicated detection databases

---

## 3. Nyroxis System Guardian

The platform guardian running as a system tray application:
- Monitors Nyroxis Agent and Intelligence every 3 seconds
- Manages scheduled and on-demand database backups
- Validates HWID-based license offline (AES-GCM + HMAC)
- Automatically stops services if license expires
- Checks for platform updates at configurable intervals

Properties:
- ~6.5 MB RAM, ~0.1% CPU
- Fully offline license validation
- Critical for platform resilience and forensic integrity

---

## 4. Secure Local Database

A protected SQLite database holding:
- Encrypted event logs
- Detection and correlation findings
- AI/ML analysis results
- Behavioral baseline data
- Metadata for forensic timeline reconstruction

Security features:
- AES-256 encryption at rest
- Hash-chained event blocks for tamper detection
- Protected write paths
- Integrity verification on every read

The database **never leaves the device**.

---

## 5. Local AI/ML Engine

The offline anomaly detection engine embedded in the Dashboard:
- Custom Isolation Forest (100 trees, 256 samples, 8 behavioral features)
- Z-Score statistical classification: Critical / High / Medium / Low
- IQR outlier detection, moving averages, spike detection
- Contributing feature identification with Z-score values
- Local behavioral baseline building

No cloud, no external ML library, no data sharing.

---

## 6. Nyroxis Dashboard

The user interface providing:
- Real-time event monitoring with forensic search and filtering
- Detection, correlation, and chain result visualization
- AI/ML analysis with contributing feature breakdown
- Reporting — PDF/CSV export
- Database backup management
- Settings and retention control
- Multilingual: English, French, German

Everything displayed is retrieved locally from the secure database.

---

## Summary

Nyroxis components work as an integrated, private, offline ecosystem — providing enterprise-grade visibility, multi-layer detection, local AI/ML intelligence, and forensic-grade evidence without exposing any user data to the cloud.
