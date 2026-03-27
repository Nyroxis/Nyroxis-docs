# Local AI/ML Engine

The Nyroxis AI/ML engine is fully local and offline.
It performs all behavioral analysis, anomaly detection, and statistical scoring **without sending any data to the cloud**.

---

## 1. Fully Offline Engine

The AI/ML engine runs entirely on the device:
- No server communication
- No online model updates
- No telemetry
- No external dependencies

All inference and processing are isolated within the local runtime.
Built in Rust with no external ML library dependency.

---

## 2. Isolation Forest — Core Algorithm

The engine implements a custom Isolation Forest algorithm:
- 100 isolation trees per analysis cycle
- 256 samples maximum per tree
- 8 behavioral features per analysis window
- Anomaly score threshold: 0.6

Anomalous events require fewer splits to isolate — shorter isolation path = higher anomaly score.

**8 behavioral features analyzed:**

| Feature | Description |
|---------|-------------|
| Event count | Total events in the analysis window |
| Unique sources | Distinct event sources |
| Unique destinations | Distinct network destinations |
| Hour of day | Time context for behavioral baseline |
| Day of week | Weekly pattern recognition |
| Events per hour | Activity rate normalization |
| New sources ratio | Proportion of previously unseen sources |
| New destinations ratio | Proportion of previously unseen destinations |

---

## 3. Statistical Analysis Engine

Running in parallel with Isolation Forest:

| Z-Score | Severity | Confidence |
|---------|----------|------------|
| > 3.0 | Critical | 99.7% |
| > 2.0 | High | 95% |
| > 1.5 | Medium | 86% |
| > 1.0 | Low | 68% |

Additional methods:
- IQR outlier detection
- Simple and exponential moving averages
- Spike detection against historical baselines
- Correlation analysis between behavioral signals

---

## 4. Explainable Results

Every detection includes:
- Anomaly score (0.0–1.0)
- Severity classification
- Contributing features — the specific behavioral dimensions that deviated most, with Z-score values

The system highlights **why** something is suspicious — transparent and locally verifiable.

---

## 5. Local Behavioral Baselines

Each device builds its own private baseline profile:
- Normal process activity
- Typical network connection patterns
- Expected file access patterns
- Usual time-of-day and day-of-week behavior

Baselines:
- Stored locally in encrypted form
- Resettable by the user at any time
- Never transmitted or shared

---

## 6. No Cloud Training or Uploading

The AI/ML engine does **not** upload:
- Logs or event data
- Anomaly samples
- Behavioral profiles
- Model feedback
- Any user data

Training and inference are exclusively offline.

---

## 7. Lightweight and Resource-Efficient

Optimized for personal laptops, executive devices, and air-gapped systems — the AI/ML engine provides strong behavioral detection without requiring enterprise hardware.

---

## Summary

The Nyroxis AI/ML engine ensures:
- Local-only inference — no cloud dependency
- Full privacy — no data sharing
- Strong behavioral detection via Isolation Forest
- Statistical depth via Z-Score, IQR, and spike detection
- Transparent, explainable results with contributing features
