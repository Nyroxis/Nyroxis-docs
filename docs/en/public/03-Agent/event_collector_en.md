# Event Collector

The Event Collector is the subsystem inside the Nyroxis Agent responsible for capturing all security‑relevant activity on the device.  
It is designed to be lightweight, private, and fully offline, while providing enterprise‑grade visibility into endpoint behavior.

---

## Purpose of the Event Collector
The Event Collector’s main goal is to gather actionable, structured information that helps users understand:
- What is happening on their device  
- When events occur  
- Whether activity is normal or suspicious  

All without exposing data externally.

---

## What the Event Collector Monitors
Nyroxis focuses on the most security‑critical categories of events:

### **1. Process Events**
- Process creation  
- Process termination  
- Parent/child relationships  
- Command-line parameters (where available)

### **2. Network Events**
- Outgoing connections  
- Incoming connections  
- Destination IPs, ports  
- Protocol type  
- Suspicious repeated attempts  

### **3. File System Activity**
- File creation  
- File deletion  
- Modifications  
- Access to sensitive directories  

### **4. Privilege & Security Events**
- Elevation attempts  
- Sensitive system calls  
- Registry/config changes (on supported platforms)  
- Access to protected resources  

### **5. System & Kernel-Level Events**
- Service start/stop  
- Driver loading  
- System warnings  
- Indicators of persistence mechanisms  

The exact scope is optimized per operating system.

---

## Secure Collection & Immediate Encryption
Every event gathered by the collector is:
- Encrypted instantly  
- Stored in tamper‑resistant form  
- Indexed with timestamps and metadata  

No unencrypted logs are ever written to disk.

---

## ️ Lightweight Implementation
The Event Collector is optimized for:
- Minimal CPU overhead  
- Low memory usage  
- Zero impact on everyday tasks  
- Stable operation over long periods  

This ensures Nyroxis remains suitable for home and professional environments.

---

## Anti‑Tamper Protections
To ensure collected logs cannot be altered or erased:
- Integrity checks are applied  
- Secure write‑paths are enforced  
- Critical files are monitored for unauthorized changes  

This increases trustworthiness during investigations.

---

## Offline‑First by Design
The Event Collector operates with **zero cloud interaction**.  
All monitoring, encryption, and storage happen locally — preserving user privacy even in sensitive environments.

---

## Summary
The Event Collector is the foundation of Nyroxis’ visibility layer, capturing every important security‑related activity while staying lightweight, encrypted, and completely offline.
