# What is Nyroxis?

Nyroxis is a lightweight, AI-assisted cybersecurity platform designed to protect **personal and unmanaged endpoints** — the devices that traditional enterprise security tools often ignore.

It provides continuous, privacy-first monitoring and brings SOC-grade detection to personal devices, without requiring cloud connectivity, technical expertise, or enterprise infrastructure.

## Why Nyroxis Exists

Modern cyberattacks no longer target only companies. Executives, lawyers, judges, doctors, journalists, and even families are targeted on **their personal devices** — where there is no SOC, no SIEM, and no security team watching over them.

Nyroxis fills this gap by bringing **enterprise-grade visibility and detection** to the personal level — silently, locally, and without compromise.

## Who is Nyroxis For?

- Executives & high-profile individuals
- Lawyers, judges, doctors & professionals handling sensitive data
- Families seeking digital safety visibility
- Cybersecurity engineers & SOC analysts at home
- Frequent travelers and remote workers
- Independent contractors and consultants

## How Nyroxis Works (High-Level)

Nyroxis is built around four core components working in concert:

### Nyroxis Agent
- Continuous silent monitoring from multiple system channels
- Normalizes, encrypts and stores everything locally
- Works fully offline — tamper-resistant design
- ~57 MB RAM, 0.1% CPU

### Nyroxis Intelligence
- Three-layer detection engine
- 27 detection rules, 12 correlation rules, 2 chain rules (growing continuously)
- Extensible by security professionals — custom rules in JSON format
- ~87 MB RAM, 1.8% CPU

### Nyroxis System Guardian
- Silent system tray guardian
- Monitors all services continuously
- Manages backups, offline license validation, and update checking
- Stops services automatically if license expires
- ~6.5 MB RAM, 0.1% CPU

### Nyroxis Dashboard
- Real-time visibility across events, detections, correlations, and chains
- Forensic search, AI/ML analysis, PDF/CSV reporting
- English, French, and German

```
[ Device ]
   |--> Nyroxis Agent          (collection & encryption)
   |--> Nyroxis Intelligence   (detection & correlation)
   |--> Nyroxis System Guardian (monitoring & protection)
   |--> Nyroxis Dashboard      (visibility & analysis)
```

## Key Advantages

- Your security data stays on your device by default
- Forensic-grade encrypted storage (AES-256)
- 27 + 12 + 2 detection rule layers, extensible by security professionals
- Local AI/ML anomaly detection — runs fully on-device, no cloud
- Optional AI Copilot — an opt-in, EU-hosted cloud assistant for natural-language analysis of a single alert (disabled by default)
- HWID-based offline licensing
- Lightweight and silent — invisible to attackers

> **On privacy:** Nyroxis is offline-first. Event collection, detection, correlation, chain analysis, and the local AI/ML engine all run on your device. The only optional exception is the **AI Copilot**, which you explicitly enable and trigger per alert; see the AI Copilot page for exactly what it sends.

## Documentation Guide

This documentation includes:
- Architecture & Components
- Agent, Intelligence & System Guardian
- Dashboard & AI/ML Engine
- Security & Privacy
- Use Cases
- Roadmap
- Licensing
- FAQ & Glossary
