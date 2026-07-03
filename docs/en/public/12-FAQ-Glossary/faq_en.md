# Frequently Asked Questions

## General

**What is Nyroxis?**
Nyroxis is a personal endpoint SIEM — a lightweight, offline-capable cybersecurity platform that brings SOC-grade monitoring, detection, and forensic evidence to personal devices. It is designed for executives, legal professionals, families, and security practitioners who need enterprise-grade protection without enterprise complexity.

**Who is Nyroxis for?**
Executives, senior managers, judges, lawyers, doctors, journalists, SOC administrators, families, independent contractors, and security professionals — anyone whose personal device is a potential attack vector.

**Is Nyroxis fully offline?**
The core platform is fully offline: event collection, detection, correlation, chain analysis, the local AI/ML engine, and license validation all happen entirely on your device, with no telemetry. The one optional exception is the **AI Copilot** — an opt-in, EU-hosted cloud feature that is disabled by default and only sends data when you explicitly analyze a specific alert. (License activation and update checks also contact Nyroxis servers, but exchange only license/version information, not event data.)

**What is the AI Copilot?**
An optional, opt-in cloud feature that provides a natural-language explanation of a specific alert. It is separate from the local AI/ML engine and is disabled by default. When enabled and triggered on an alert, it sends that alert's metadata, source IP, your note, and the matched rule definition to the EU-hosted nyroxis.ai service. It never sends raw event logs or local AI/ML output. See the *AI Copilot* page for full details.

**What platforms does Nyroxis support?**
Currently Windows (v1.0). macOS and Linux support is in active development.

**What languages does the Dashboard support?**
English, French, and German.

---

## Detection & Rules

**How many detection rules does Nyroxis have?**
Version 1.0 includes 27 detection rules, 12 correlation rules, and 2 chain rules. The library grows continuously as new threat patterns are identified.

**What is the difference between detection, correlation, and chain rules?**
- **Detection** — identifies known threat patterns in individual events
- **Correlation** — connects related events across time and sources to reveal patterns no single event would expose
- **Chain** — detects multi-stage attack sequences spread across multiple events and time windows

**Can security professionals add their own rules?**
Yes. The rule engine is fully extensible. Security professionals can write and deploy custom rules in JSON format without modifying the core system.

---

## Privacy & Data

**Does Nyroxis read my personal files?**
No. Nyroxis only collects security-relevant technical events — processes, network connections, file system activity, and privilege actions. It never reads the content of your documents, emails, photos, or browser history.

**Where is my data stored?**
All data is stored locally in an AES-256 encrypted SQLite database on your device. It never leaves your machine.

**Can logs be exported?**
Yes — from the Dashboard, you can export findings in PDF or CSV format for reporting or security investigation.

**Is the AI/ML engine local?**
The local AI/ML engine is 100% local. The Isolation Forest algorithm is implemented in Rust with no external ML library, and no behavioral data is ever sent to a server. (This is separate from the optional AI Copilot cloud feature — see above.)

**Can I reset my data?**
Yes. From the Dashboard you can reset event logs, detection findings, AI behavioral baseline, and all metadata at any time.

---

## Licensing

**How does licensing work?**
Each license is bound to your hardware (HWID). The cryptographic key is derived from your device's hardware profile. Validation is fully offline — no internet required.

**Is there a free trial?**
Yes. Every new installation includes one month of full access with no restrictions. No credit card required.

**What happens if my license expires?**
Nyroxis System Guardian automatically stops Nyroxis Agent and Nyroxis Intelligence when the license expires or is invalidated.

---

## Technical

**What resources does Nyroxis use?**
- Nyroxis Agent: ~57 MB RAM, 0.1% CPU
- Nyroxis Intelligence: ~87 MB RAM, 1.8% CPU
- Nyroxis System Guardian: ~6.5 MB RAM, 0.1% CPU
- Nyroxis Dashboard: ~32 MB RAM when open

**What is Nyroxis System Guardian?**
A silent system tray application that monitors all platform services continuously, manages backups, validates the HWID-based license offline, and checks for updates. It automatically stops services if the license expires.

**What technology is Nyroxis built with?**
Core services are built in Rust. The Dashboard uses Tauri + WebView. The local database is SQLite. Event data is encrypted at rest with AES-256, and event integrity is protected by a hash chain. The AI/ML engine is a custom Isolation Forest implementation in Rust with no external ML library.

**Does Nyroxis work in air-gapped environments?**
Yes. Full functionality requires zero internet connectivity — monitoring, detection, AI/ML analysis, and license validation all work completely offline.
