# Rule Matching & Detection

The Rule Matching module is how Nyroxis Intelligence evaluates security events and generates alerts.
It brings SIEM-style detection logic to personal devices — fully offline, privacy-first, and extensible by security professionals.

---

## What Rule Matching Does

Nyroxis Intelligence evaluates events against three layers of local rules to identify:
- Known threat patterns in individual events
- Suspicious relationships between events over time
- Multi-stage attack sequences

No rules or logs are ever sent online.

---

## Three Detection Layers

### Layer 1 — Detection Rules (27 rules)
Pattern matching against individual events.

**Trigger types:**
- Suspicious process execution
- Unauthorized service installation
- Abnormal network behavior
- Credential access attempts
- Indicators of known malware activity

When a detection rule fires, an immediate alert is generated and stored in the detections database.

---

### Layer 2 — Correlation Rules (12 rules)
Pattern matching across related events over time and across sources.

**Trigger types:**
- Failed login followed by a successful one from a different location
- New process spawning immediately after USB device connection
- Repeated failed connections followed by a successful outbound call
- Script execution followed by file system modification

Correlation rules reveal threat patterns that no single event would expose alone.

---

### Layer 3 — Chain Rules (2 rules)
Detection of multi-stage attack sequences spread across multiple events and time windows.

Chain rules are the highest-priority alerts in the system. They represent coordinated, progressive intrusions — the kind that characterize advanced persistent threats.

Each chain finding includes a full reconstruction of the detected attack sequence.

---

## Extensible by Security Professionals

The rule engine is fully open for extension. Security professionals can:
- Write custom detection, correlation, or chain rules in JSON format
- Deploy them directly into the system without modifying core components
- Test rules against existing event data before deployment
- Version and manage their custom rule library

This allows Nyroxis to be adapted to specific environments, threat models, or organizational requirements.

---

## How the Engine Evaluates Rules

Nyroxis Intelligence matches rules against:
- Event metadata and content
- Timestamps and time windows
- Process lineage
- Network endpoints
- Severity indicators
- Cross-event relationships

All evaluations are real-time and fully local.

---

## When a Rule Triggers

When a rule is matched, Nyroxis:
- Raises an immediate alert
- Stores the finding in the dedicated detections database
- Records the matched events, severity level, and rule details
- Makes the finding visible in the Detection, Correlation, or Chain view of the Dashboard

---

## Privacy Guarantee

All rule matching:
- Happens locally on the device
- Does not communicate with external services
- Uses encrypted event data only
- Never uploads logs, rules, or pattern matches

---

## Summary

The Nyroxis rule matching engine brings structured, SIEM-like detection to personal endpoints — across three layers, growing continuously, and extensible by security professionals — without cloud dependency or privacy compromise.
