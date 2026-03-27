# Offline Security

Nyroxis is designed to operate fully offline without any dependency on cloud services, external APIs, or remote servers.
This ensures complete autonomy, privacy, and protection even in disconnected or air-gapped environments.

---

## 1. No Cloud Communication

Nyroxis never:
- Sends telemetry or usage data
- Syncs logs to remote servers
- Contacts cloud services for any function
- Uses cloud AI or external ML APIs
- Requires online activation

Every function is local.

---

## 2. Local-Only Key Management

Encryption keys are:
- Derived locally from hardware identifiers (HWID)
- Bound to the specific device
- Never transmitted to any server
- Never stored in plaintext
- Reconstructed only in memory when needed

All cryptographic operations happen offline.

---

## 3. Offline License Validation

Nyroxis System Guardian validates the license entirely offline:
- License bound to HWID-derived cryptographic key
- Validation uses AES-GCM encryption and HMAC verification locally
- No internet connection required for any aspect of license management
- Services stop automatically if license is invalid — enforced locally

---

## 4. Offline AI/ML Engine

The Isolation Forest and statistical analysis engine runs completely offline:
- Behavioral anomaly detection
- Z-Score statistical classification
- Spike detection and baseline comparison

All computed directly from encrypted local events — no cloud inference, no network access.

---

## 5. Local Encrypted Storage

All event logs, detection findings, and AI results remain:
- Fully encrypted (AES-256)
- Stored in a protected local database
- Accessible only on the same device
- Protected by hash-chained integrity structures

No risk of remote breaches or cloud leaks.

---

## 6. No External Fetching

Nyroxis does not download:
- Detection rules or rule updates
- AI models or model updates
- Signatures or threat intelligence feeds

Everything is embedded and managed locally. Rule updates come through manual installation.

---

## 7. Works in Air-Gapped Environments

Nyroxis runs perfectly on:
- Fully offline laptops
- Isolated corporate environments
- High-security government setups
- High-risk locations with no internet access

Full functionality requires **zero connectivity**.

---

## Summary

Nyroxis offline security ensures:
- Full autonomy — no external infrastructure dependency
- Zero cloud exposure
- Local-only AI/ML
- Private encrypted storage
- Complete independence from internet connectivity

A security model built for maximum privacy and control.
