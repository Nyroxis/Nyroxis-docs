# High-Level Architecture

The Nyroxis architecture is designed to provide strong security, full privacy, and complete offline autonomy.
This high-level overview explains how all major components work together while keeping user data protected and encrypted locally.

---

## Core Architectural Principles

### 1. Fully Local Operation
All processing — collection, detection, AI analysis, storage, reporting — happens on the device. Nothing is uploaded or transmitted.

### 2. Privacy by Design
No cloud. No telemetry. No remote monitoring. No behavioral profiling.

### 3. Lightweight & Efficient
Designed to run continuously on personal laptops without impacting daily productivity.

### 4. Forensic Integrity
Event logs are encrypted, hash-chained, and tamper-resistant — suitable for legal and regulatory proceedings.

---

## High-Level Components

### 1. Nyroxis Agent
- Captures system events in real time from multiple channels
- Normalizes and encrypts immediately
- Stores encrypted events in the local database
- ~57 MB RAM, ~0.1% CPU

### 2. Nyroxis Intelligence
- Evaluates events across 27 detection + 12 correlation + 2 chain rules
- Raises immediate alerts on rule matches
- Fully extensible by security professionals (JSON rule format)
- ~87 MB RAM, ~1.8% CPU

### 3. Nyroxis System Guardian
- Monitors Agent and Intelligence every 3 seconds
- Manages backups and offline HWID license validation
- Stops services if license expires
- ~6.5 MB RAM, ~0.1% CPU

### 4. Secure Local Database
- SQLite with AES-256 encryption
- Hash-chained event blocks for tamper detection
- Stores events, findings, AI results, and baselines
- Never leaves the device

### 5. Local AI/ML Engine
- Isolation Forest anomaly detection (100 trees, 8 features)
- Z-Score, IQR, moving average, spike detection
- Contributing feature breakdown for analysts
- Fully offline — no cloud inference

### 6. Nyroxis Dashboard
- Real-time visibility: events, detections, correlations, chains, AI/ML
- Forensic search, charts, reporting (PDF/CSV)
- Backup management, settings, multilingual (EN/FR/DE)
- All data retrieved locally

---

## Security Layers

The architecture includes multiple defensive layers:
- Encryption at capture (AES-256)
- Hash-chained event structures
- Protected write paths
- Platform guardian for service resilience
- Offline license validation
- No external communication of any kind

---

## Data Flow Summary

```
[ System Events ]
        ↓
[ Nyroxis Agent ]          ← collect, normalize, encrypt
        ↓
[ Local Encrypted DB ]     ← AES-256, SQLite, hash-chained
        ↓
[ Nyroxis Intelligence ]   ← 27 detection + 12 correlation + 2 chain rules
        ↓
[ Local AI/ML Engine ]     ← Isolation Forest + statistical analysis
        ↓
[ Nyroxis Dashboard ]      ← visibility, forensics, reporting
        ↑
[ Nyroxis System Guardian ] ← monitors, backs up, validates license
```

---

## Summary

Nyroxis architecture delivers powerful, private, offline security by combining four core components — Agent, Intelligence, System Guardian, and Dashboard — working together with local AI/ML and forensic-grade storage, entirely without cloud exposure.
