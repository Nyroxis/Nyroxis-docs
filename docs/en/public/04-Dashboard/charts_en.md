# Charts & Analytics

The Charts & Analytics section of the Nyroxis Dashboard transforms raw security events into visual insights, helping users quickly understand trends, anomalies, and potential risks.
All analytics are generated locally, preserving full privacy.

---

## Purpose of Visual Analytics

Charts help users answer key questions immediately:
- Is activity increasing or decreasing over time?
- Are there unusual spikes in processes or network traffic?
- Which event categories occur the most?
- How are detection and correlation findings distributed by severity?
- Are there recurring suspicious patterns over time?

Visuals make complex security data immediately understandable.

---

## Available Chart Types

### 1. Event Frequency Over Time
Shows how many events occur hourly, daily, and weekly.
Useful for spotting spikes, bursts of activity, or unexpected quiet periods that may indicate something was disabled.

### 2. Severity Distribution
Visual breakdown of events by severity level: Critical, High, Warning, Info.
Helps users see the overall risk profile at a glance.

### 3. Top Event Sources
Highlights which processes, files, or network endpoints generate the most events:
- Most active processes
- Most accessed files
- Most frequent network connections

### 4. Detection & Correlation Trend
Tracks the evolution of rule matches over time:
- Detection findings
- Correlation findings
- Chain findings

Helps users detect escalation patterns before a full compromise occurs.

### 5. AI/ML Anomaly Score Trend
Visualizes the output of the local Isolation Forest engine over time:
- Anomaly score evolution
- Severity classifications: Critical / High / Medium / Low
- Spike events against the behavioral baseline

---

## Local Analytics Engine

All charts are powered by the local analysis engine:
- No cloud
- No external APIs
- All computation stays on the device

Charts are generated directly from the encrypted local database and AI/ML engine output.

---

## Privacy & Offline Operation

Nothing is sent to external services — ever.
Analytics are computed and rendered locally from encrypted events, entirely offline.

---

## Summary

Charts & Analytics provide a visual, privacy-preserving way to understand system activity, track detection trends, monitor AI/ML findings, and gain immediate insight into the security posture of the device.
