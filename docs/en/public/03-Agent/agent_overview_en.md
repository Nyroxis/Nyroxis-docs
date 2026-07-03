# Nyroxis Agent — Overview

The Nyroxis Agent is the core monitoring and collection component of the platform.
It runs locally on the user's device, quietly collecting and normalizing security events, encrypting them, and storing them in a tamper-resistant local database — all with minimal resource usage.

---

## What the Agent Does

The Agent continuously observes system activity and builds a structured, encrypted security timeline.

It monitors:
- Process creation and termination
- Network connections and traffic metadata
- File modifications and registry changes
- Privilege actions and credential access attempts
- System and security events (Windows Event Logs)
- PowerShell and script execution

All events are collected **privately and locally** — nothing is transmitted externally.

---

## Collection Pipeline

1. **Collection** — events are ingested from multiple system channels simultaneously
2. **Normalization** — raw data is enriched and standardized for the detection engine
3. **Encryption** — payload is encrypted with AES-256 before any write operation
4. **Storage** — encrypted events are written to the local SQLite database
5. **Feed** — data flows to Nyroxis Intelligence for real-time rule evaluation

---

## Privacy-First Operation

The Agent never uploads logs or sends event data to external servers.
Everything remains on the device and is:
- Encrypted at the moment of collection
- Protected against tampering via hash-chained event blocks
- Stored in a secure local SQLite database
- Under the user's sole control at all times

---

## Lightweight by Design

The Agent is optimized for minimal footprint:
- ~57 MB RAM
- ~0.1% CPU
- Silent background operation as a Windows service
- Suitable for continuous operation on personal laptops without impacting daily productivity

---

## Resilient & Tamper-Aware

The Agent incorporates protective mechanisms to ensure:
- Collected event data cannot be altered or deleted undetected
- Attackers cannot silently erase their activity
- Hash-chained event blocks expose any deletion, modification, or injection attempt

Nyroxis System Guardian monitors the Agent's operational status continuously and takes corrective action if the service stops unexpectedly.

---

## Works Completely Offline

No internet connection is required for:
- Monitoring
- Normalization and encryption
- Data storage
- Feeding Nyroxis Intelligence

Nyroxis is fully functional in isolated or air-gapped environments.

---

## Summary

The Nyroxis Agent delivers continuous, encrypted, offline monitoring — giving users enterprise-grade visibility without exposing their data to third parties, and providing forensic-grade evidence forensic-grade and suitable for security investigation.
