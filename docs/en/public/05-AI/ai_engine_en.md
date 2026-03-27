# AI Engine — Internal Mechanics

The Nyroxis AI/ML engine is designed to run fully locally, performing intelligent analysis on encrypted security events without relying on cloud services.

---

## Core Design Principles

### 1. Privacy-First
- No cloud processing
- No external APIs
- No data sharing

All intelligence runs on the user's own device.

### 2. Lightweight Implementation
Built entirely in Rust without external ML libraries:
- ~Low CPU usage
- Minimal memory footprint
- Real-time execution

### 3. Behavioral Understanding
Instead of analyzing events individually, the engine understands *patterns* that occur across time and across multiple event dimensions.

### 4. Fully Offline Operation
All analysis, scoring, and feature extraction happen locally — no internet required at any stage.

---

## Isolation Forest — How It Works

The Isolation Forest algorithm isolates anomalies by building random decision trees and measuring how quickly each data point is separated from the rest.

**The principle:**
- Normal events require many splits to isolate (they blend in with others)
- Anomalous events require fewer splits (they stand out)
- Shorter isolation path = higher anomaly score

**Nyroxis implementation:**
- 100 isolation trees built per analysis cycle
- 256 random samples used per tree
- All 8 behavioral features normalized before analysis
- Anomaly score threshold: 0.6 (above this = detection triggered)
- Contributing features identified via Z-score deviation (threshold: 2.0 standard deviations)

---

## Statistical Analysis Pipeline

### Z-Score Classification
Every monitored value is evaluated against its historical baseline:

```
z = (value - mean) / standard_deviation
```

| |z| | Severity | Confidence |
|------|----------|------------|
| > 3.0 | Critical | 99.7% |
| > 2.0 | High | 95% |
| > 1.5 | Medium | 86% |
| > 1.0 | Low | 68% |

### IQR Outlier Detection
```
lower_bound = Q1 - 1.5 × IQR
upper_bound = Q3 + 1.5 × IQR
```
Values outside this range are flagged as statistical outliers.

### Moving Averages
- **Simple Moving Average** — baseline trend over configurable time windows
- **Exponential Moving Average** — weights recent activity more heavily for faster response to emerging patterns

### Spike Detection
```
current_value > mean + (threshold_multiplier × std_dev)
```

---

## What the Engine Outputs

For each analysis cycle:
- `is_anomaly` — boolean flag
- `anomaly_score` — 0.0 to 1.0 (higher = more anomalous)
- `confidence` — 0.0 to 0.95
- `contributing_features` — list of features with Z-scores that drove the detection

These outputs are displayed in the AI / ML Analysis section of the Dashboard.

---

## Local Behavioral Baseline

The engine builds a private baseline per device:
- Normal process patterns
- Typical network connection behavior
- Expected file activity
- Usual time-of-day and day-of-week behavior

The baseline is:
- Stored locally in encrypted form
- Resettable by the user at any time
- Never transmitted or shared

---

## Summary

The AI engine combines Isolation Forest with statistical analysis to deliver transparent, explainable, privacy-preserving anomaly detection — entirely on the user's device, with no cloud dependency.
