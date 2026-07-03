# Architecture Overview

Nyroxis is built on a lightweight, privacy-first architecture designed to deliver enterprise-grade visibility and detection without relying on the cloud.
The system runs fully on the user's device and is composed of four independent components that work together securely.

---

## Core Components

### 1. Nyroxis Agent
A lightweight endpoint monitor that:
- Collects security-relevant events from multiple system channels
- Normalizes and encrypts them immediately at capture
- Stores everything in a local tamper-resistant database
- Operates 100% offline — ~57 MB RAM, ~0.1% CPU

### 2. Nyroxis Intelligence
A high-speed detection and correlation engine that:
- Applies 27 detection rules against individual events
- Runs 12 correlation rules across related events over time
- Executes 2 chain rules to detect multi-stage attack sequences
- Raises immediate alerts on any rule match
- Accepts custom rules from security professionals
- ~87 MB RAM, ~1.8% CPU

### 3. Nyroxis System Guardian
A silent system tray guardian that:
- Monitors Nyroxis Agent and Intelligence continuously
- Manages backups and HWID-based license validation (fully offline)
- Checks for updates automatically
- Stops services automatically if license expires
- ~6.5 MB RAM, ~0.1% CPU

### 4. Nyroxis Dashboard
A clear and intuitive interface that:
- Displays events, detections, correlations, and chains
- Provides forensic search, charts, and PDF/CSV reporting
- Includes a local AI/ML engine (Isolation Forest + statistical analysis)
- Supports English, French, and German

---

## High-Level Data Flow

```
[ System Events ]
        ↓
[ Nyroxis Agent ]          ← collect, normalize, encrypt
        ↓
[ Local Encrypted DB ]     ← AES-256, SQLite, hash-chained
        ↓
[ Nyroxis Intelligence ]   ← 27 detection + 12 correlation + 2 chain rules
        ↓
[ Nyroxis Dashboard ]      ← visibility, AI/ML, forensics, reporting
        ↑
[ Nyroxis System Guardian ] ← monitors, backs up, validates license
```

At no stage are logs or sensitive data uploaded to external servers.

---

## Design Principles

### Privacy by Design
- No cloud ingestion
- Local encryption at capture
- User retains full control at all times

### Forensic Integrity
- AES-256 encrypted logs
- Hash-chained event blocks
- Tamper-resistant storage suitable for security investigation

### Lightweight Operation
Built to run smoothly on personal laptops and workstations without impacting daily productivity.

### Offline-First Security
No internet connection is required for:
- Monitoring and detection
- AI/ML analysis
- Dashboard usage
- License validation

### Extensibility
Security professionals can write and deploy custom detection, correlation, and chain rules without modifying the core system.

---

## Summary
Nyroxis provides a modern, modular, and forensically sound architecture that brings professional-grade visibility and detection to personal devices — entirely offline, with full respect for user privacy.
