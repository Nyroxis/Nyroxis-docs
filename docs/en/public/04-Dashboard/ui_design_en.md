# Dashboard UI Design

The Nyroxis Dashboard is built to give users — both non-technical and professional — a clear, intuitive, and actionable view of their device's security state.
Its design follows principles of clarity, minimalism, privacy, and real-time awareness.

---

## Design Philosophy

### Clarity Above Complexity
Security data should never overwhelm the user.
The Dashboard transforms raw logs into readable insights with clean layouts, color-coded severity indicators, and simple explanations.

### Privacy-First Visualization
All data shown in the Dashboard:
- Comes from local encrypted storage
- Never leaves the device
- Is processed entirely offline

### Consistent UX for All Personas
The interface serves non-technical executives, legal professionals, families, and cybersecurity analysts equally — each receives the same clean, structured layout.

---

## Core Dashboard Sections

### 1. Main Overview
The entry point — provides an at-a-glance picture of the current security posture:
- Total events collected in the last 24 hours
- Active alerts by severity: Critical, High, Warning, Info
- Real-time event timeline
- Severity distribution chart
- System status: agent state, database size, rule engine health, license validity, backup status

### 2. Events
The forensic core of the dashboard:
- Full access to the raw event database
- Search across all event fields: source, channel, severity, content
- Filter by time range, severity, source, and channel
- Forensic inspection of individual events with full payload detail
- Export to CSV for legal documentation

### 3. Detection
All findings from Nyroxis Intelligence's 27-rule detection layer:
- Rule that triggered the alert
- Specific events that matched
- Severity classification and timestamp
- Direct link to underlying raw events for forensic drill-down

### 4. Correlation
Findings from the 12-rule correlation engine:
- Patterns that emerge from relationships between events over time
- Time window and source mapping
- Where isolated signals become actionable intelligence

### 5. Chain
Findings from the 2-rule chain detection layer:
- Multi-stage attack sequence detection
- Highest-priority alerts in the system
- Full reconstruction of the detected attack sequence

### 6. Reports
Structured, exportable documentation:
- Configurable time windows
- PDF and CSV export
- Suitable for internal review, regulatory submission, or legal proceedings

### 7. AI / ML Analysis
Access to the local machine learning engine:
- Anomaly detection findings with contributing feature breakdown
- Z-Score classifications: Critical / High / Medium / Low
- Behavioral baseline evolution tracking
- Statistical outlier and spike identification
- All analysis performed locally — no data leaves the device

### 8. Settings
Complete platform configuration:
- Database file path and storage management
- Dashboard refresh interval
- Default lookback window and sample limit
- Interface language selection: English, French, German
- Theme configuration
- Hardware ID display for license reference

### 9. Backup
Direct management of database backup operations:
- Scheduled and on-demand execution
- Backup history with timestamps and file sizes
- All backups encrypted and stored locally

---

## Visual Style

- **Red / Critical:** critical severity alerts
- **Amber / Orange:** high and warning severity
- **Blue:** informational events
- **Green:** normal / safe status

---

## Responsiveness

The Dashboard is optimized for desktops and laptops:
- 13" laptops to ultra-wide monitors
- High-resolution screens

---

## Summary

The Nyroxis Dashboard does not ask its users to choose between power and simplicity. Security professionals have the forensic depth they need. Non-technical users have the clarity they need. Enterprise-grade protection, accessible to everyone it protects.
