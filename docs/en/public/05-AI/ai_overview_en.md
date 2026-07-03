# AI & Machine Learning Engine — Overview

The Nyroxis AI/ML engine is a fully local, offline anomaly detection system embedded in the Dashboard.
It analyzes security events without sending any data to the cloud, delivering behavioral intelligence with strong privacy.

> **Note:** This page describes the **local, on-device** AI/ML engine, which runs fully offline. Nyroxis also offers a separate, optional **AI Copilot** — an opt-in, EU-hosted cloud assistant for natural-language analysis of individual alerts. The two are independent; see the *AI Copilot* page for details.

---

## A Different Approach to AI

Most AI-powered security solutions rely on cloud infrastructure — sending telemetry to remote servers for analysis.
Nyroxis takes the opposite approach: every aspect of the AI engine runs locally, on the user's own device.
No data is transmitted. No external service is consulted. No behavioral profile ever leaves the machine.

This is not a limitation — it is a deliberate architectural commitment to privacy.

---

## What the AI Engine Provides

- Behavioral anomaly detection using Isolation Forest
- Statistical analysis: Z-Score, IQR, moving averages, spike detection
- Severity classification: Critical / High / Medium / Low
- Contributing feature identification — explains *why* something was flagged
- Behavioral baseline building per device

---

## Isolation Forest — Core Algorithm

At the core of the engine is a custom implementation of the Isolation Forest algorithm, built entirely in Rust — no external ML library required.

**How it works:**
Isolation Forest builds a forest of random decision trees. Anomalous events are statistically rare or structurally unusual — they require fewer splits to isolate, and therefore receive a higher anomaly score.

**Implementation:**
- 100 isolation trees per analysis cycle
- 256 samples maximum per tree
- 8 behavioral features per analysis window
- Anomaly score > 0.6 triggers a detection

---

## 8 Behavioral Features Analyzed

| Feature | Description |
|---------|-------------|
| Event count | Total events in the analysis window |
| Unique sources | Number of distinct event sources |
| Unique destinations | Number of distinct network destinations |
| Hour of day | Time context for behavioral baseline |
| Day of week | Weekly pattern recognition |
| Events per hour | Activity rate normalization |
| New sources ratio | Proportion of previously unseen sources |
| New destinations ratio | Proportion of previously unseen destinations |

All features are normalized using z-score standardization before analysis.

---

## Statistical Analysis Engine

Running in parallel with Isolation Forest:

| Z-Score | Severity | Confidence |
|---------|----------|------------|
| > 3.0 | Critical | 99.7% |
| > 2.0 | High | 95% |
| > 1.5 | Medium | 86% |
| > 1.0 | Low | 68% |

Additional methods: IQR outlier detection, moving average, exponential moving average, spike detection, correlation analysis.

---

## Full Privacy Guarantee

The AI engine:
- Runs entirely offline
- Processes only locally encrypted event data
- Never sends data to servers
- Never uploads behavioral profiles
- Never uses cloud inference or online APIs

The AI engine belongs entirely to the user's device.

---

## Summary

The Nyroxis AI/ML engine provides on-device Isolation Forest anomaly detection combined with statistical analysis — delivering cloud-quality behavioral intelligence without the privacy trade-off.
