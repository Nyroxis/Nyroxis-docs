# Data Flow — High-Level Overview

This section explains how data moves inside Nyroxis — from event collection to AI analysis — while remaining fully encrypted, offline, and private at every step.

---

##  1. Event Capture (Nyroxis Agent)

The flow begins with the Agent monitoring:
- Processes  
- Network events  
- File system operations  
- Privilege actions  

Every event is captured **in real time**.

Immediately after capture:
- The event is serialized  
- Encrypted using the device’s local key  
- Prepared for storage  

No plaintext ever touches the disk.

---

##  2. Encrypted Storage (Local Database)

Once encrypted, events are written into:
- The secure local database  
- Hash‑chained event structures  
- Protected write paths  

Each entry includes:
- Timestamp  
- Encrypted payload  
- Integrity hash  
- Metadata required for AI  

All data stays on the user’s device — never synced or uploaded.

---

##  3. Local AI Processing (NyXIA)

NyXIA periodically reads events from the database:
- Still encrypted at rest  
- Decrypted only in memory  
- Processed inside a secure local runtime  

NyXIA performs:
- Behavioral feature extraction  
- Sequence grouping  
- Anomaly scoring  
- Scenario evaluation  

No part of the AI requires cloud access.

---

## ️ 4. Rule Matching Engine

In parallel, the rule engine analyzes:
- Event frequency  
- Threshold violations  
- Pattern matches  
- Correlation hints  

It complements AI with deterministic logic.

---

##  5. Dashboard Display (Local UI)

The Dashboard pulls only:
- Decrypted-in-memory summaries  
- Processed AI results  
- Correlation outputs  
- Alerts  

All UI rendering happens locally, with no external communication.

---

##  6. Optional User Actions
Users may:
- Search encrypted logs (decrypted in memory)  
- Clear/reset data  
- Adjust thresholds  
- Export encrypted backups (future feature)  

All options stay local and private.

---

##  Privacy by Architecture
Every step ensures:
- No cloud use  
- No telemetry  
- No remote access  
- No online dependencies  

Nyroxis maintains full privacy through architecture — not just configuration.

---

##  Summary
Nyroxis data flow is simple, private, and fully offline:
1. Event captured → encrypted  
2. Stored securely → integrity-protected  
3. Analyzed locally → AI + rules  
4. Displayed locally → dashboard  
5. No cloud, no upload, no exposure  
