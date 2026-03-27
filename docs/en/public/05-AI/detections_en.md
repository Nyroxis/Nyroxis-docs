# AI Detections

The AI Detections view shows anomalies identified by the local AI/ML engine — when it identifies unusual or suspicious activity on the device based on behavioral analysis and statistical scoring.
All detections are generated locally, without cloud processing or data sharing.

---

## Purpose of AI Detections

The AI engine detects:
- Behavioral anomalies — deviations from the established device baseline
- Suspicious activity sequences
- Rare or unexpected patterns
- Statistical outliers across behavioral features
- High-risk deviations identified by Isolation Forest scoring

These detections complement the rule-based findings from Nyroxis Intelligence, adding a layer of behavioral intelligence that does not rely on predefined rules.

---

## Types of AI Detections

### 1. Anomaly-Based Detections
Triggered when the Isolation Forest anomaly score exceeds 0.6 — meaning the observed behavioral pattern is statistically isolated from the normal baseline.

Example cases:
- Unusual process activity at unexpected times
- Irregular network connection patterns
- Unexpected file modification bursts
- Activity far outside typical hour-of-day or day-of-week baseline

---

### 2. Statistical Outliers (Z-Score)
Triggered when a specific behavioral feature deviates significantly from the historical mean:
- Critical: Z-score > 3.0 (99.7% confidence)
- High: Z-score > 2.0 (95% confidence)
- Medium: Z-score > 1.5 (86% confidence)
- Low: Z-score > 1.0 (68% confidence)

---

### 3. Spike Detections
Triggered when a monitored metric suddenly jumps far above its historical average:
- Sudden burst of events per hour
- Spike in new network destinations
- Rapid increase in unique sources

---

### 4. Persistent Anomalies
Long-term deviations that accumulate over time:
- Gradual increase in new destination ratio
- Slow-building unusual activity patterns
- Repeated low-score anomalies forming a trend

---

## Detection Details

Each AI detection includes:
- Description of the anomaly
- Anomaly score (0.0 – 1.0)
- Severity classification
- Contributing features — the specific behavioral dimensions that deviated most significantly from baseline, with Z-score values
- Timestamp and analysis window

---

## 100% Local & Private

All AI detections are:
- Computed offline on the device
- Stored locally in the encrypted database
- Derived from encrypted event logs
- Never uploaded to servers or shared with any third party

---

## Summary

AI Detections provide intelligent, privacy-preserving anomaly alerts that complement rule-based detection — helping users identify dangerous or abnormal activity early, with full local processing and no cloud dependency.
