# Encryption Model

Nyroxis implements a strict, multi-layered encryption model designed to ensure that **no readable data ever touches disk**, and that all security events remain protected, private, and verifiable.

---

## Core Goals

Nyroxis encryption achieves:
- **Confidentiality** — no one can read user data
- **Integrity** — no one can modify logs undetected
- **Isolation** — data never leaves the device
- **Zero plaintext storage** — everything encrypted at capture
- **Offline operation** — no cloud keys or servers required

---

## 1. Encryption at Event Capture

Every system event is encrypted the moment it is collected by Nyroxis Agent.

Steps:
1. Event is serialized in memory
2. A device-specific key is derived from hardware identifiers (HWID)
3. The event is encrypted with AES-256
4. Only the encrypted block is written to storage

No plaintext logs are ever written.

---

## 2. Encrypted Local Database

All logs, detection findings, AI results, and metadata are stored inside a secure SQLite database.

Features:
- AES-256 encrypted data pages
- Encrypted metadata
- Hash-chained storage blocks
- Per-record integrity verification
- No plaintext caching

The database cannot be opened or read outside Nyroxis, and cannot be decrypted on a different device.

---

## 3. In-Memory Decryption Only

Nyroxis decrypts records *only while processing them*:
- AI/ML engine decrypts event batches in RAM during analysis
- Dashboard decrypts only what it needs to display, in memory
- Nothing is written back in plaintext
- Memory buffers are cleared after use

This eliminates the risk of forensic recovery of plaintext from disk.

---

## 4. Device-Bound Keys

Encryption keys are:
- Derived from the user's hardware identifiers (HWID)
- Generated locally using salted hashing
- Never stored directly inside the application
- Never transmitted to any server

Even if the database file is copied to another device, it cannot be decrypted — it is bound to the original hardware.

---

## 5. Integrity Protection — Hash Chain

Each encrypted block contains:
- Integrity hash of the block content
- Event sequence index
- Hash of the previous block

This forms a **hash chain** that exposes:
- Log deletion — next block's previous-hash will not match
- Log modification — block hash will not match
- Log reordering — sequence index will be wrong
- Log injection — chain and sequence checks will fail

Tampering is immediately detectable.

---

## 6. No Cloud Involvement

Nyroxis does not use:
- Cloud key vaults
- Remote key servers
- Online activation
- Telemetry systems

All encryption, key derivation, and integrity verification are entirely local.

---

## Summary

Nyroxis encryption ensures:
- Zero plaintext storage
- Encrypted-everywhere design
- Device-bound local keys
- Hash-chained tamper-resistant logs
- In-memory-only decryption

A modern encryption model built for personal security and full offline autonomy.
