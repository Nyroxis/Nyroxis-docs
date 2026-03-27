# Key Features

Nyroxis brings enterprise-style visibility and detection to personal and professional devices, while remaining lightweight, private, and fully offline-capable.

---

## Multi-Layer Detection Engine

Nyroxis Intelligence operates across three sequential detection layers:

### Layer 1 — Detection (27 rules)
Identifies known threat patterns in individual events:
- Suspicious process execution
- Unauthorized service installation
- Abnormal network behavior
- Credential access attempts

### Layer 2 — Correlation (12 rules)
Connects related events across time and sources to reveal patterns no single event would expose:
- Failed login followed by a successful one from a different location
- New process spawning immediately after a USB device is connected

### Layer 3 — Chain (2 rules)
Detects multi-stage attack sequences — the coordinated, progressive intrusions that characterize advanced persistent threats.

The rule library grows continuously. Security professionals can write and deploy their own custom rules directly into the engine without modifying the core system.

---

## Local Event Monitoring

Nyroxis Agent continuously collects security-relevant activity:
- Process creation and termination
- Network connections and traffic metadata
- File modifications and registry changes
- Privilege-related actions
- System and security events (Windows Event Logs)
- PowerShell and script execution

All monitoring happens **locally**, without sending data to the cloud.

---

## Forensic-Grade Encrypted Storage

All collected events are:
- Encrypted at rest (AES-256)
- Protected against tampering via hash-chained event blocks
- Stored only on the user's device
- Suitable for legal and regulatory proceedings

---

## Local AI/ML Engine

Nyroxis includes a custom Isolation Forest implementation built in Rust — no external ML library required:
- 100 isolation trees per analysis cycle
- 8 behavioral features analyzed per window
- Z-Score statistical analysis: Critical / High / Medium / Low
- IQR outlier detection, moving averages, spike detection
- All computation on-device — no cloud, ever

---

## Platform Guardian (Nyroxis System Guardian)

A silent system tray service that:
- Monitors all platform services every 3 seconds
- Manages scheduled and on-demand database backups
- Validates HWID-based license fully offline
- Checks for updates automatically
- Stops services automatically if license expires

---

## Intuitive Dashboard

The dashboard provides:
- Real-time event timeline and severity indicators
- Detection, correlation, and chain result views
- Forensic search with advanced filtering
- AI/ML analysis with contributing feature breakdown
- Reporting — PDF/CSV export
- Database backup management
- Available in English, French, and German

---

## Offline-First Operation

Nyroxis works fully without:
- Cloud connection
- Internet dependency
- External authentication

The platform is designed for high-privacy environments and works in air-gapped setups.

---

## Tamper-Resistant Architecture

Nyroxis protects:
- All platform services via Nyroxis System Guardian
- Local logs via hash-chained event blocks
- Integrity of event data through continuous verification

Attackers cannot erase their footprints undetected.
