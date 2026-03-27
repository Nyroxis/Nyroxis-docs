# User Control & Transparency

Nyroxis is designed to give users full control over their security data, system behavior, and privacy settings.
No hidden processes, no background uploads, no cloud connections — everything is transparent and locally managed.

---

## Core Principles of User Control

Nyroxis ensures that users can:
- See what is being monitored
- Control what is stored and for how long
- Reset or delete data at any time
- Verify that the platform operates offline
- Understand how AI/ML decisions are made

The user always stays in charge.

---

## 1. No Silent Data Collection

Nyroxis collects **only** what is necessary for security analysis:
- Logs of processes and services
- Network connection events
- File system and registry changes
- Privilege actions
- Windows Event Log entries

No personal files, photos, messages, browsing data, or credentials are ever collected.
Everything collected is documented in this documentation.

---

## 2. Full Data Reset

Users can reset at any time from the Dashboard:
- Event logs
- Detection and correlation findings
- AI/ML behavioral baseline
- All metadata

A full reset restores Nyroxis to a clean state without leftovers.

---

## 3. Local-Only Storage

All data is:
- Stored locally in the encrypted SQLite database
- Fully encrypted (AES-256)
- Never transmitted externally
- Under the user's sole control

Users do not depend on cloud accounts, online authentication, or remote storage.

---

## 4. Transparent AI/ML

The AI/ML engine provides:
- Clear anomaly score with severity classification
- Contributing features — the specific behavioral dimensions that drove the detection, with Z-score values
- Scenario-based reasoning summaries

AI decisions are designed to be understandable and explainable — not black-boxed.

---

## 5. Customization Options

Users can adjust from the Settings view:
- Database file path and storage location
- Dashboard refresh interval
- Default lookback window for event queries
- Default sample limit
- Interface language: English, French, German
- Theme configuration

All settings are local.

---

## 6. Backup Control

From the Backup section, users can:
- Schedule automatic backups
- Run on-demand backups
- Review backup history with timestamps and file sizes
- All backups are encrypted and stored locally

---

## 7. Verification of Offline Operation

The Dashboard and Nyroxis System Guardian expose indicators allowing users to verify:
- No outgoing network connections from Nyroxis processes
- No background telemetry
- No cloud dependency
- Agent and Intelligence service status in real time

Trust is measurable — not assumed.

---

## Summary

Nyroxis empowers users with full control over their data, full transparency of its operations, and the ability to manage, reset, back up, or verify everything locally — without cloud reliance or hidden processes.
