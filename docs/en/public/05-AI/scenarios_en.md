# AI Scenarios

AI Scenarios represent predefined, high-level security situations that NyXIA is capable of detecting based on behavioral patterns, sequences, and anomalies.  
They help users understand *context*, not just individual events.

---

## Purpose of AI Scenarios
While detections highlight specific anomalies, **Scenarios** explain *why those anomalies matter* by grouping signals into meaningful categories.

Scenarios give users clarity about:
- The type of threat  
- The probable cause  
- How events are related  
- What the risk means in real-world terms  

This helps even non-technical users understand what is happening.

---

## Types of Scenarios

### **1. Suspicious Process Chain**
Detected when a process chain resembles known malicious behavior:
- Unknown process → script engine  
- Script engine → modification → network call  
- Process spawning multiple children rapidly  

Useful for catching early-stage malware or scripts.

---

### **2. Unauthorized Network Activity**
Triggered when NyXIA observes:
- Outbound connections to unknown or rare endpoints  
- Repeated failed connections  
- High-volume network activity outside normal patterns  

May indicate scanning, beaconing, or data exfiltration attempts.

---

### **3. Abnormal File Activity**
Occurs when:
- Sensitive files are accessed unexpectedly  
- Many files change in a short window  
- Modifications align with suspicious process behavior  

Useful for detecting ransomware-like behavior or tampering.

---

### **4. Privilege Escalation Attempt**
Triggered by:
- Repeated privilege actions  
- Rare or unusual system calls  
- Behavior inconsistent with normal user activity  

This helps identify local exploitation attempts.

---

### **5. Persistence Indicator**
Occurs when a process tries to:
- Modify startup locations  
- Create scheduled tasks  
- Alter system configuration to survive reboot  

This scenario warns about long-term compromise attempts.

---

### **6. Slow Intrusion Pattern**
NyXIA identifies long-term anomalies such as:
- Gradual escalation  
- Rare periodic activity  
- Multi-stage behavior spread over hours/days  

This detects stealthy attackers that evade traditional tools.

---

## Scenario Report Details
Each scenario provides:
- Description of the situation  
- Affected events  
- Sequence explanation  
- Severity level  
- Real-world interpretation  
- Recommended next steps  

---

## Fully Local Interpretation
All scenario logic:
- Runs offline  
- Uses encrypted log data  
- Never contacts cloud services  
- Preserves user privacy  

---

## Summary
AI Scenarios help users see the *bigger picture*, giving meaning to individual anomalies and enabling early detection of sophisticated threats — all fully offline and private.
