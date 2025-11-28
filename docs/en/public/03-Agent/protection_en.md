# Protection Core

The Protection Core is the security backbone of the Nyroxis Agent.  
It reinforces the integrity of monitoring, ensures encrypted event handling, and prevents attackers from tampering with logs or disabling the Agent.

Its design follows strict privacy-first and offline-first principles.

---

## Core Objectives
The Protection Core ensures:
- Security events cannot be altered  
- Logs remain encrypted from source to storage  
- The Agent cannot be silently disabled  
- Sensitive components are protected from unauthorized changes  

This creates trust in the visibility layer.

---

## 1. End-to-End Local Encryption
Every event captured by Nyroxis is:
- Encrypted immediately  
- Written to disk in encrypted form only  
- Indexed with timestamps and metadata  
- Never stored in plaintext  

The encryption model prevents attackers from reading or modifying event history.

---

## 2. Integrity Protection (Anti-Tamper)
Nyroxis applies mechanisms such as:
- Protected write paths  
- Hashing & verification of event blocks  
- Monitoring of its own critical files  
- Alerting on suspicious modification attempts  

These components help detect attempts to erase traces.

---

## 3. Agent Self-Protection
The Protection Core ensures the Agent cannot be quietly disabled.

Protections include:
- Monitoring the Agent’s runtime state  
- Detecting unexpected shutdowns  
- Ensuring immediate restart on interruption  
- Logging shutdown attempts as security events  

This ensures persistent monitoring even under attack.

---

## 4. Offline Security
The Protection Core never requires:
- Cloud validation  
- External APIs  
- Remote servers  

All checks and verification happen **100% offline**.

---

## 5. Secure Interaction with the Dashboard
The Dashboard accesses data through:
- Verified secure read-paths  
- Read-only access to logs  
- Strict separation between visualization and event storage  

This prevents UI-layer attacks from modifying real data.

---

## Summary
The Protection Core ensures that monitoring, encryption, and event integrity remain trustworthy — even in hostile environments — while keeping all data private and fully local.
