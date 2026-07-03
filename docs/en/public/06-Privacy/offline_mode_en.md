# Offline Mode

Nyroxis is built from the ground up to operate fully offline — its core monitoring, detection, and local analysis require no cloud access, remote authentication, or external APIs.
This design gives users security, privacy, and full autonomy over their device.

> **One optional exception:** the **AI Copilot** is an opt-in, EU-hosted cloud feature. When you deliberately enable it and analyze a specific alert, that alert's data is sent to nyroxis.ai. It is disabled by default. Everything described on this page refers to the offline core, which works with no connectivity at all. See the *AI Copilot* page for details.

---

## Why Offline Matters

Operating offline ensures:
- **No security event data leaves the device** in offline operation
- **No exposure to cloud breaches** or third-party infrastructure failures
- **No dependency on external servers** for monitoring or detection
- **No risk of third-party monitoring** or behavioral profiling
- **Full functionality even without internet** — including in air-gapped environments

Users retain complete control over their security data.

---

## 1. Full Local Operation

Every function of the Nyroxis platform operates locally:
- Event collection and normalization (Nyroxis Agent)
- Detection, correlation, and chain rule evaluation (Nyroxis Intelligence)
- Service monitoring, backup, and license validation (Nyroxis System Guardian)
- AI/ML anomaly detection and statistical analysis
- Dashboard visualization and reporting

Nothing is uploaded. Nothing is transmitted.

---

## 2. No Cloud, No Servers

Nyroxis does not use:
- Cloud processing or storage
- Telemetry or usage tracking
- Remote logging
- Online scanning or threat intelligence feeds
- External authentication services

For the offline core, this eliminates entire classes of privacy and attack risks. (The optional AI Copilot is the single, opt-in exception noted above.)

---

## 3. Offline License Validation

Nyroxis System Guardian validates the HWID-based license entirely offline:
- No internet connection required
- Validation uses AES-GCM encryption and HMAC verification locally
- License integrity is enforced without contacting any external server

---

## 4. Local AI/ML Engine

The Isolation Forest and statistical analysis engine runs completely offline:
- Behavioral anomaly detection
- Z-Score classification
- Spike detection and baseline comparison

All computed directly from encrypted local events — no cloud inference, no model updates over the network.

---

## 5. Update Checking (Optional)

Nyroxis System Guardian can check for updates at configurable intervals.
Update installation remains manual — there are no forced or automatic cloud connections.
The platform operates at full capability regardless of update status.

---

## 6. Transparent Architecture

Nyroxis exposes clear indicators in the Dashboard that allow users to verify:
- No outgoing network connections from Nyroxis processes
- No background telemetry
- No cloud dependency

Trust is measurable — not assumed.

---

## Summary

Offline Mode guarantees that Nyroxis remains private, encrypted, autonomous, and fully local — a security platform designed to protect users without ever exposing their data.
