# Protection Core

The Protection Core is the security backbone of the Nyroxis Agent.
It reinforces the integrity of monitoring, ensures encrypted event handling, and prevents attackers from tampering with logs or disabling the platform.

Its design follows strict privacy-first and offline-first principles.

---

## Core Objectives

The Protection Core ensures:
- Security events cannot be altered or deleted undetected
- Logs remain encrypted from source to storage
- The platform cannot be silently disabled
- Sensitive components are protected from unauthorized changes

This creates trust in the visibility and forensic layer.

---

## 1. End-to-End Local Encryption

Every event captured by Nyroxis is:
- Encrypted immediately at the moment of capture
- Written to disk in encrypted form only (AES-256)
- Indexed with timestamps and metadata
- Never stored in plaintext

The encryption model prevents attackers from reading or modifying event history.

---

## 2. Integrity Protection — Hash-Chained Event Blocks

Nyroxis stores events in a hash-chained structure where each block contains:
- Encrypted payload
- Integrity hash
- Sequential index
- Link to the previous block

This makes tampering immediately detectable:
- **Deletion** — the next block's previous-hash will not match
- **Modification** — the hash of the altered block will not match
- **Injection** — sequence numbers and chain hashes will fail

Any tampering is flagged as a security event.

---

## 3. Platform Service Protection

Nyroxis System Guardian is responsible for ensuring that Nyroxis Agent and Nyroxis Intelligence remain running at all times.

Every 3 seconds, Guardian verifies the operational status of both services. If either service stops unexpectedly — due to a system event, crash, or deliberate interference — Guardian detects it immediately and takes corrective action.

Shutdown attempts are logged as security events, preserving evidence of interference.

---

## 4. Offline Security

The Protection Core never requires:
- Cloud validation
- External APIs
- Remote servers

All integrity checks and verification happen **100% offline**.
License validation also operates fully offline via AES-GCM encryption and HMAC verification.

---

## 5. Secure Interaction with the Dashboard

The Dashboard accesses event data through:
- Verified secure read-paths
- Read-only access to logs
- Strict separation between visualization and event storage

This prevents UI-layer attacks from modifying real data.

---

## Summary

The Protection Core — combined with Nyroxis System Guardian — ensures that monitoring, encryption, and event integrity remain trustworthy even in hostile environments, while keeping all data private, local, and forensically reliable.
