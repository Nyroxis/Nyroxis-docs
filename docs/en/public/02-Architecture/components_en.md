# Architecture Components

This section describes each major component of the Nyroxis platform.
All components are designed to operate locally, efficiently, and with a privacy-first approach.

---

## 1. Nyroxis Agent

The core monitoring and collection service running on the device.

### Responsibilities
- Collects security events from multiple system channels simultaneously
- Monitors processes, network activity, file system, registry, and privilege actions
- Normalizes event data in real time
- Encrypts the payload immediately and writes to the local database
- Maintains tamper-resistant integrity via hash-chained event blocks

### Properties
- ~57 MB RAM, ~0.1% CPU
- Runs silently as a Windows service in the background
- Offline-first — nothing leaves the device

---

## 2. Nyroxis Intelligence

The detection and correlation engine — the analytical core of the platform.

### Three Detection Layers

| Layer | Rules | Purpose |
|-------|-------|---------|
| nyroxis_detection | 27 | Identify known threat patterns in individual events |
| nyroxis_correlations | 12 | Connect related suspicious events across time and sources |
| nyroxis_chains | 2 | Detect multi-stage attack sequences |

### Properties
- Operates at high speed across all three layers simultaneously
- Rule library grows continuously as new threats emerge
- Fully extensible — security professionals can write and deploy custom rules in JSON format without modifying the core system
- ~87 MB RAM, ~1.8% CPU

---

## 3. Nyroxis System Guardian

The platform guardian — runs silently as a Windows system tray application.

### Responsibilities
- Monitors Nyroxis Agent and Nyroxis Intelligence every 3 seconds
- Detects unexpected service stops and takes corrective action
- Manages scheduled and on-demand database backups
- Validates HWID-based license offline (AES-GCM + HMAC verification)
- Automatically stops all services if license expires or is invalidated
- Checks for platform updates at configurable intervals

### Properties
- ~6.5 MB RAM, ~0.1% CPU
- Fully offline license validation — no internet required
- Critical for platform resilience and forensic integrity

---

## 4. Local Encrypted Database

Nyroxis uses a secured SQLite database to retain all collected events.

### Features
- Full at-rest encryption (AES-256)
- Hash-chained event blocks for tamper detection
- Structured event storage with integrity verification
- Optimized for fast lookups and timeline reconstruction
- No cloud upload — the user is the sole owner of the data

---

## 5. Nyroxis Dashboard

A visual interface that transforms raw security data into actionable intelligence.

### Provides
- Real-time event monitoring with forensic search and filtering
- Detection, correlation, and chain result visualization
- Built-in local AI/ML engine (Isolation Forest + statistical analysis)
- Reporting — PDF/CSV export
- Database backup management
- Multilingual interface: English, French, German

### Audience
Both non-technical users and cybersecurity professionals can use it effectively.

---

## 6. Local AI/ML Engine

A fully offline anomaly detection engine embedded in the Dashboard.

### Functions
- Isolation Forest algorithm (100 trees, 256 samples, 8 behavioral features)
- Z-Score statistical classification: Critical / High / Medium / Low
- IQR outlier detection, moving averages, spike detection
- Behavioral baseline building and deviation scoring
- Contributing feature identification for analyst context

Everything operates locally — no cloud, no telemetry, no data sharing.

---

## Summary
Nyroxis is built from modular, local-first components that work together to give users enterprise-grade visibility and detection — privately, efficiently, and without cloud dependency.
