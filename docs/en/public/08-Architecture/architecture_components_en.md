# Architecture Components

This section describes each core component of the Nyroxis platform and how they work together to deliver private, offline, tamper‑resistant security.

---

##  1. Nyroxis Agent (Event Collector)
The Agent is the lightweight background service responsible for:
- Monitoring processes  
- Tracking network connections  
- Observing file changes  
- Watching privilege activity  
- Capturing system events in real time  

All events are **encrypted immediately** before being written anywhere.

It is designed to be:
- Silent  
- Efficient  
- Low‑resource  
- Fully offline  

---

##  2. Secure Local Database
A protected, encrypted local storage that holds:
- Event logs  
- Metadata  
- Behavioral baselines  
- Correlation indexes  

Security features include:
- AES‑based encryption  
- Integrity checking  
- Hash‑chained event blocks  
- No plaintext storage  

The database **never leaves the device**.

---

##  3. NyXIA — Local AI Engine
NyXIA is the offline AI engine powering:
- Behavioral anomaly detection  
- Scenario generation  
- Risk scoring  
- Sequence pattern analysis  

It processes encrypted events locally and does not require:
- Cloud AI  
- Telemetry  
- Network access  

Privacy‑first by design.

---

##  4. Rule Matching Engine
A deterministic rule‑based engine used for:
- Pattern detection  
- Event frequency checks  
- Threshold‑based alerts  
- Correlation support  

It complements AI with predictable, transparent logic.

---

##  5. Dashboard (User Interface)
The Dashboard provides:
- Real‑time visibility  
- Event search  
- AI insights  
- Charts & analytics  
- Settings and retention control  

Everything displayed is retrieved locally from the secure database.

---

##  6. Security Layer
Every component is protected by:
- Local encryption  
- Integrity verification  
- No cloud communication  
- Strict offline operation  
- Tamper‑resistant data structures  

---

##  Summary
Nyroxis components work as an integrated, private, offline ecosystem — providing strong security without exposing any user data to the cloud.
