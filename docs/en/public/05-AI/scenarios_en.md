# AI Scenarios

AI Scenarios represent high-level security situations that the local AI/ML engine identifies based on behavioral patterns, event sequences, and anomaly correlations.
They help users understand *context* — not just individual events or isolated anomalies.

---

## Purpose of AI Scenarios

While detections highlight specific anomalies and rule matches flag individual threats, **Scenarios** explain *why those signals matter* by grouping related findings into meaningful, real-world attack contexts.

Scenarios give users clarity about:
- The type of threat being observed
- How individual events and anomalies are related
- What the combined pattern means in real-world terms
- What the recommended next steps are

This makes sophisticated threat patterns understandable even for non-technical users.

---

## Types of Scenarios

### 1. Suspicious Process Chain
Detected when a sequence of process activity resembles known malicious behavior:
- Unknown process spawning a script engine
- Script engine triggering file modification followed by a network call
- Process spawning multiple children in rapid succession

Useful for catching early-stage malware, dropper behavior, or living-off-the-land techniques.

---

### 2. Unauthorized Network Activity
Triggered when the engine observes:
- Outbound connections to unknown or rare network endpoints
- Repeated failed connections followed by a successful outbound call
- High-volume network activity far outside normal baseline patterns

May indicate scanning, beaconing, or data exfiltration attempts.

---

### 3. Abnormal File Activity
Occurs when:
- Sensitive files or directories are accessed unexpectedly
- A large number of files are modified in a short time window
- File modifications correlate with suspicious process or network behavior

Useful for detecting ransomware-like behavior, data staging, or tampering.

---

### 4. Privilege Escalation Attempt
Triggered by:
- Repeated privilege elevation attempts
- Rare or unusual system calls
- Behavior inconsistent with the device's normal user activity pattern

Helps identify local exploitation attempts or credential abuse.

---

### 5. Persistence Indicator
Occurs when a process attempts to:
- Modify startup locations or scheduled tasks
- Alter system configuration to survive reboot
- Install services or drivers unexpectedly

Warns about long-term compromise and attacker foothold establishment.

---

### 6. Slow Intrusion Pattern
The engine identifies long-term, low-noise anomalies such as:
- Gradual escalation of unusual activity over hours or days
- Rare periodic activity that repeats on a schedule
- Multi-stage behavioral sequences spread across extended time windows

Detects stealthy attackers who deliberately avoid triggering threshold-based rules.

---

## Scenario Report Details

Each scenario provides:
- Description of the situation in plain language
- Affected events and findings
- Sequence explanation showing how signals are connected
- Severity level
- Real-world interpretation
- Recommended next steps

---

## Fully Local

All scenario logic:
- Runs offline on the device
- Uses encrypted local event data
- Never contacts cloud services
- Preserves full user privacy

---

## Summary

AI Scenarios help users see the bigger picture — giving meaning to individual anomalies and rule matches by mapping them to real-world attack contexts, enabling early detection of sophisticated threats entirely offline and privately.
