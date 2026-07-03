# Glossary

**AES-256** — Advanced Encryption Standard with a 256-bit key. Used to encrypt all Nyroxis event logs and database storage at rest.

**Agent** — See *Nyroxis Agent*.

**Anomaly Score** — A value between 0.0 and 1.0 produced by the Isolation Forest engine. Higher scores indicate more anomalous behavior. Scores above 0.6 trigger a detection.

**Behavioral Baseline** — A local profile of normal device activity built over time by the AI/ML engine, used to identify deviations.

**Chain Rule** — A detection rule targeting multi-stage attack sequences spread across multiple events and time windows. Nyroxis v1.0 includes 2 chain rules.

**Correlation Rule** — A detection rule that connects related events across time and sources to reveal patterns no single event would expose. Nyroxis v1.0 includes 12 correlation rules.

**Detection Rule** — A rule targeting known threat patterns in individual events. Nyroxis v1.0 includes 27 detection rules.

**Forensic Evidence** — Tamper-resistant, encrypted event logs forensic-grade and suitable for security investigation.

**Hash Chain** — A cryptographic structure where each event block contains the hash of the previous block, making deletion, modification, injection, or reordering immediately detectable.

**HMAC** — Hash-based Message Authentication Code. Used in Nyroxis license validation to verify file integrity offline.

**HWID** — Hardware Identifier. A unique value derived from the physical characteristics of a device, used to bind a Nyroxis license to a specific machine and derive encryption keys.

**Isolation Forest** — A machine learning algorithm that detects anomalies by building random decision trees and measuring how quickly each data point is isolated. Implemented in Rust in Nyroxis with no external ML library.

**IQR** — Interquartile Range. A statistical method for outlier detection used in the Nyroxis statistical analysis engine.

**Nyroxis Agent** — The core monitoring service. Collects, normalizes, encrypts, and stores security events locally (~57 MB RAM, 0.1% CPU).

**Nyroxis Dashboard** — The user interface for visibility, forensic analysis, AI/ML insights, and reporting.

**Nyroxis Intelligence** — The detection and correlation engine. Operates across 27 detection rules, 12 correlation rules, and 2 chain rules (~87 MB RAM, 1.8% CPU).

**Nyroxis System Guardian** — The platform guardian. Monitors all services continuously, manages backups, validates the license offline, and checks for updates (~6.5 MB RAM, 0.1% CPU).

**Rule Engine** — The component inside Nyroxis Intelligence that evaluates incoming events against detection, correlation, and chain rules in real time.

**SIEM** — Security Information and Event Management. A system that collects, correlates, and analyzes security events. Nyroxis functions as a personal endpoint SIEM.

**SQLite** — The local database engine used by Nyroxis to store encrypted event logs and detection findings.

**Tamper Protection** — Mechanisms including hash-chained event blocks and integrity verification that prevent attackers from deleting, modifying, or injecting logs undetected.

**Z-Score** — A statistical measure of how many standard deviations a value is from the mean. Used by Nyroxis to classify anomaly severity: Critical (>3.0), High (>2.0), Medium (>1.5), Low (>1.0).
