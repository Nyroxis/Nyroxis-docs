# Data Flow

This section explains how data moves inside Nyroxis — from event collection to user interpretation — while remaining fully local, encrypted, and private at every step.

---

## 1. Event Collection (Nyroxis Agent)

Nyroxis Agent continuously monitors:
- Processes and services
- Network connections and traffic metadata
- File system changes and registry modifications
- Privilege actions
- System and security events (Windows Event Logs)
- PowerShell and script execution

All data is collected **locally**, without any cloud interaction.

---

## 2. Normalization & Encryption at Source

Immediately after collection:
- Events are normalized and enriched with context
- Payload is encrypted with AES-256
- Integrity hash is applied
- Data is written to the local database in encrypted form only

No plaintext ever touches the disk.

---

## 3. Local Encrypted Database

Encrypted events are stored inside a secure SQLite database.

Properties:
- Fully encrypted at rest (AES-256)
- Hash-chained event blocks for tamper detection
- Structured for fast lookups and timeline reconstruction
- No external transmission — ever

The database never leaves the device.

---

## 4. Nyroxis Intelligence — Rule Engine

Nyroxis Intelligence reads from the encrypted database and evaluates events across three layers:
- **27 detection rules** — individual event pattern matching
- **12 correlation rules** — multi-event pattern detection across time
- **2 chain rules** — multi-stage attack sequence detection

When a rule is triggered:
- An alert is raised immediately
- The finding is stored in a dedicated detections database
- The user is notified via the Dashboard

---

## 5. Local AI/ML Engine

In parallel, the AI/ML engine processes events locally:
- Isolation Forest anomaly scoring
- Z-Score statistical classification
- Behavioral baseline comparison
- Contributing feature identification

All computation stays on the device — no cloud inference, no data sharing.

---

## 6. Dashboard Visualization

The Nyroxis Dashboard transforms all of the above into:
- Event logs with forensic search and filtering
- Detection, correlation, and chain findings
- AI/ML anomaly results with contributing feature breakdown
- Charts, severity indicators, and trend analysis
- Exportable reports (PDF/CSV)

Everything remains local and private.

---

## Full Data Lifecycle

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

At no stage are logs or sensitive data uploaded to external servers.

---

## Summary
Nyroxis maintains a strictly local, encrypted, and privacy-first data flow — giving users full visibility and forensic-grade evidence without exposing any information to the cloud or third parties.
