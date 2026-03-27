# Security Overview

Nyroxis is built with a strict security-first philosophy: all operations are local, encrypted, tamper-resistant, and designed to protect the user without exposing any data to third parties.

This overview summarizes the main security principles and mechanisms used across the platform.

---

## Core Security Principles

### 1. Privacy by Design
Nyroxis does not upload, sync, or transmit any data to servers.
All security logic, monitoring, detection, and AI analysis run entirely on the device.

### 2. Encryption Everywhere
Every captured event is:
- Encrypted instantly at capture (AES-256)
- Stored only in encrypted form — never in plaintext
- Decrypted exclusively in memory during processing
- Protected with integrity hashes

No plaintext logs ever exist on disk.

### 3. Zero Cloud Dependency
Nyroxis does not rely on:
- Cloud storage or processing
- External APIs
- Remote servers
- Telemetry pipelines
- Online authentication

Users maintain full autonomy and zero external exposure.

### 4. Multi-Layer Detection
Nyroxis Intelligence provides:
- 27 detection rules — known threat patterns
- 12 correlation rules — multi-event patterns over time
- 2 chain rules — multi-stage attack sequences
- Extensible by security professionals without modifying core components

### 5. Local AI/ML
The AI/ML engine processes data locally:
- Isolation Forest anomaly detection
- Z-Score statistical classification
- Contributing feature identification

No cloud training, no cloud inference, no data sharing.

---

## Key Security Mechanisms

### 1. Secure Event Capture
Nyroxis Agent captures:
- Processes and services
- File system and registry changes
- Network connections
- Privilege actions
- Windows Event Log entries

All events are encrypted immediately at capture.

### 2. Tamper-Resistant Storage
The local SQLite database includes:
- AES-256 encryption
- Hash-chained event blocks
- Protected write paths
- Integrity verification on every read

Attackers cannot modify, delete, or inject logs without detection.

### 3. Platform Resilience
Nyroxis System Guardian:
- Monitors Agent and Intelligence every 3 seconds
- Detects unexpected service stops immediately
- Logs shutdown attempts as security events
- Manages backups and offline license validation

The platform cannot be silently disabled.

### 4. HWID-Based Licensing
License validation:
- Bound to device hardware (HWID-derived key)
- Validated offline using AES-GCM and HMAC
- Enforced by System Guardian — services stop automatically if license is invalid

### 5. Dashboard Security
The Dashboard:
- Reads decrypted summaries only in RAM
- Never writes back decrypted data to disk
- Does not connect to external sources
- Provides read-only access to log storage

---

## Security Layers Summary

Nyroxis integrates multiple defensive layers:
- AES-256 encryption at capture
- Hash-chained tamper-resistant storage
- Platform guardian for service resilience
- Local-only AI/ML engine
- Offline license validation
- Zero cloud exposure
- Privacy-first architecture throughout

---

## Summary

Nyroxis provides a modern, private, offline security model that protects users without tracking them — combining transparency, control, forensic integrity, and strong defensive design at every layer.
