# Event Collector

The Event Collector is the subsystem inside the Nyroxis Agent responsible for capturing all security-relevant activity on the device.
It is designed to be lightweight, private, and fully offline, while providing enterprise-grade visibility into endpoint behavior.

---

## Purpose of the Event Collector

The Event Collector's main goal is to gather actionable, structured information that helps users understand:
- What is happening on their device
- When events occur
- Whether activity is normal or suspicious

All without exposing data externally.

---

## What the Event Collector Monitors

Nyroxis focuses on the most security-critical categories of events:

### 1. Process Events
- Process creation and termination
- Parent/child relationships
- Command-line parameters (where available)
- Execution paths and binary metadata

### 2. Network Events
- Outgoing and incoming connections
- Destination IPs and ports
- Protocol type
- Repeated connection attempts

### 3. File System Activity
- File creation, modification, and deletion
- Access to sensitive directories
- Registry modifications

### 4. Privilege & Security Events
- Elevation attempts
- Sensitive system calls
- Registry and config changes
- Access to protected resources

### 5. System & Service Events
- Service start/stop
- Driver loading
- Windows Event Log entries (Security, System, Application)
- Indicators of persistence mechanisms
- PowerShell and script execution

The exact scope is optimized for Windows (v1.0). macOS and Linux support is in development.

---

## Normalization Pipeline

After collection, each event is:
1. Parsed and structured into a normalized format
2. Enriched with contextual metadata (timestamp, source, severity hint)
3. Prepared for encryption and storage
4. Made ready for consumption by Nyroxis Intelligence

This normalization ensures consistent rule evaluation across all event types.

---

## Secure Collection & Immediate Encryption

Every event gathered by the collector is:
- Encrypted instantly with AES-256
- Stored in tamper-resistant hash-chained form
- Indexed with timestamps and metadata
- Never written to disk in plaintext

---

## Lightweight Implementation

The Event Collector is optimized for:
- Minimal CPU overhead (~0.1%)
- Low memory usage (~57 MB RAM total for the Agent)
- Zero impact on everyday tasks
- Stable long-term operation

---

## Offline-First by Design

The Event Collector operates with **zero cloud interaction**.
All monitoring, normalization, encryption, and storage happen locally — preserving user privacy even in sensitive or air-gapped environments.

---

## Summary

The Event Collector is the foundation of Nyroxis' visibility layer, capturing every important security-related activity while staying lightweight, encrypted, and completely offline.
