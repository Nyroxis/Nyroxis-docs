# Data Flow — High-Level Overview

This section explains how data moves inside Nyroxis — from event collection to AI analysis and dashboard display — while remaining fully encrypted, offline, and private at every step.

---

## 1. Event Capture (Nyroxis Agent)

The flow begins with Nyroxis Agent monitoring:
- Processes and services
- Network connections and traffic metadata
- File system operations and registry changes
- Privilege actions
- Windows Event Log entries (Security, System, Application)
- PowerShell and script execution

Every event is captured **in real time**.

Immediately after capture:
- The event is normalized and enriched with context
- Encrypted using the device's local HWID-derived key (AES-256)
- Prepared for storage

No plaintext ever touches the disk.

---

## 2. Encrypted Storage (Local Database)

Once encrypted, events are written into:
- The secure local SQLite database
- Hash-chained event structures
- Protected write paths

Each entry includes:
- Timestamp
- Encrypted payload
- Integrity hash
- Sequential index linked to the previous block
- Metadata required for rule evaluation and AI analysis

All data stays on the user's device — never synced or uploaded.

---

## 3. Rule Evaluation (Nyroxis Intelligence)

Nyroxis Intelligence reads from the encrypted database and evaluates events across three layers:
- **27 detection rules** — individual event pattern matching
- **12 correlation rules** — multi-event patterns across time and sources
- **2 chain rules** — multi-stage attack sequence detection

When a rule triggers:
- An alert is raised immediately
- The finding is written to a dedicated detections database
- The user is notified via the Dashboard

---

## 4. Local AI/ML Processing

In parallel, the AI/ML engine reads events from the database:
- Decrypted only in memory — never written back in plaintext
- Processed by the Isolation Forest algorithm
- Evaluated by Z-Score, IQR, and spike detection methods

Outputs:
- Anomaly score (0.0–1.0)
- Severity classification
- Contributing features with Z-score values
- Behavioral baseline update

No part of the AI requires cloud access or external communication.

---

## 5. Dashboard Display (Local UI)

The Dashboard pulls only:
- Decrypted-in-memory summaries
- Detection, correlation, and chain findings
- AI/ML results with contributing feature breakdown
- Charts and trend data

All UI rendering happens locally with no external communication.

---

## 6. User Actions

Users can:
- Search encrypted logs (decrypted in memory during search)
- Export findings in PDF or CSV format
- Clear or reset data at any time
- Manage backup operations from the Backup section
- Adjust settings and retention from the Settings view

All actions stay local and private.

---

## Privacy by Architecture

Every step ensures:
- No cloud use
- No telemetry
- No remote access
- No online dependencies

Nyroxis maintains full privacy through architecture — not just configuration.

---

## Summary

```
Event captured  →  encrypted immediately
Stored securely →  hash-chained, integrity-protected
Rule evaluation →  27 detection + 12 correlation + 2 chain
AI/ML analysis  →  Isolation Forest + statistical engine
Displayed locally → dashboard, forensics, reporting
No cloud        →  no upload, no exposure, ever
```
