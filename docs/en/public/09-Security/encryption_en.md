# Encryption Model

Nyroxis implements a strict, multi‑layered encryption model designed to ensure that **no readable data ever touches disk**, and that all security events remain protected, private, and verifiable.

This page describes how encryption is applied across the entire platform.

---

##  Core Goals of the Encryption Model
Nyroxis encryption is designed to achieve:

- **Confidentiality** — no one can read user data  
- **Integrity** — no one can modify logs undetected  
- **Isolation** — data never leaves the device  
- **Zero plaintext storage** — everything encrypted at capture  
- **Offline operation** — no need for cloud keys or servers  

---

##  1. Encryption at Event Capture
Every system event is encrypted *the moment it is collected* by the Agent.

Steps:
1. Event is serialized in memory  
2. A device‑specific key is loaded  
3. The event is encrypted with AES‑based encryption  
4. Only the encrypted block is written to storage  

No plaintext logs are ever written.

---

##  2. Encrypted Local Database
All logs and metadata are stored inside a secure encrypted database.

Features include:
- AES‑encrypted data pages  
- Encrypted metadata  
- Hash‑chained storage blocks  
- Per‑record integrity verification  
- No plaintext caching  

The database cannot be opened or read outside Nyroxis.

---

##  3. In‑Memory Decryption Only (AI & Dashboard)
Nyroxis decrypts records *only while processing them*:

- NyXIA decrypts event batches in RAM  
- Dashboard decrypts only what it needs to display summaries  
- Nothing is written back in plaintext  
- Memory buffers are securely cleared  

This eliminates risk of forensic recovery.

---

##  4. Device‑Bound Keys
Encryption keys are tied to the user’s machine using:
- Hardware identifiers  
- Local derivation  
- Salted hashing  
- Split secrets  

Keys are **never stored directly** and **never transmitted**.

Even if the database is copied, it cannot be decrypted elsewhere.

---

##  5. Integrity Protection
Each encrypted block contains:
- Integrity hash  
- Event sequence marker  
- Tamper flag  
- Link to the previous block  

This forms a **hash‑chain** that exposes:
- Log deletion  
- Log modification  
- Log reordering  
- Log injection  

Tampering becomes immediately detectable.

---

##  6. No Cloud Involvement
Nyroxis does *not* use:
- Cloud key vaults  
- Remote servers  
- Online activation  
- Telemetry systems  

All encryption, key derivation, and verification are local.

---

##  Summary
Nyroxis encryption ensures:
- Zero plaintext  
- Encrypted‑everywhere design  
- Local‑only keys  
- Tamper‑resistant logs  
- Privacy‑preserving AI  

A modern encryption model built for personal security and full offline autonomy.
