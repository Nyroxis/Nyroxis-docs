# Secure Data Storage

Nyroxis stores only the minimum amount of data required to provide security insights — and all stored data is fully encrypted, local, and tamper-resistant.
This ensures privacy for individuals, families, and professionals who rely on Nyroxis for real protection without exposure.

---

## What Nyroxis Stores

Nyroxis keeps **only security-relevant information**:

### 1. Event Logs
Encrypted entries for:
- Process activity
- Network connections
- File changes and registry modifications
- Privilege actions
- System and Windows Event Log entries

### 2. Detection & Correlation Findings
Results from Nyroxis Intelligence rule evaluation:
- Detection findings (27 rules)
- Correlation findings (12 rules)
- Chain findings (2 rules)

### 3. AI/ML Analysis Results
Output from the local Isolation Forest and statistical engine:
- Anomaly scores and severity classifications
- Contributing feature breakdowns
- Behavioral baseline data

### 4. Metadata for Analysis
Lightweight metadata needed for:
- Rule matching and correlation
- AI behavioral baseline building
- Timeline reconstruction

---

## What Nyroxis Does NOT Store

Nyroxis deliberately avoids collecting or saving personal or sensitive content.

It does **NOT** store:
- Personal documents or project files
- Images or videos
- Browser history
- Location data
- Passwords or credentials
- Contents of files
- User messages or emails
- Any data unrelated to security events

Only security-oriented technical data is retained.

---

## Encryption Model

All stored data is:
- Encrypted at the moment of capture (AES-256)
- Saved only in encrypted form — never written in plaintext
- Decrypted only in memory during read operations
- Protected by hash-chained integrity structures

Encryption keys are:
- Local to the device
- Derived from hardware identifiers (HWID)
- Never embedded inside the application
- Never transmitted to servers

---

## Tamper-Resistant Structures

Nyroxis uses hash-chained event blocks where each block contains:
- Encrypted payload
- Integrity hash
- Sequential index
- Link to the previous block

This makes tampering immediately detectable:
- Deletion, modification, injection, or reordering breaks the chain
- Any mismatch is flagged as a security event

---

## Data Retention

Users have full control over their data:
- Reset logs at any time
- Clear the AI behavioral baseline
- Manage retention duration from the Settings view
- Export encrypted backups from the Backup section

---

## Fully Local Storage

All storage is:
- Local-only on the user's device
- Fully offline
- AES-256 encrypted
- Zero cloud upload — ever

Your security data stays on your machine — always.

---

## Summary

Nyroxis stores only encrypted, minimal, security-focused information — never personal content — ensuring real privacy and forensic-grade protection for every user.
