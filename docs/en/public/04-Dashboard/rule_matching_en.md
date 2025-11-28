# Rule Matching

The Rule Matching module allows Nyroxis to highlight events that match predefined security rules.  
It brings SIEM-style logic to personal devices — fully offline and privacy-first.

---

##  What Rule Matching Does
Nyroxis evaluates events against a set of local rules to identify:
- Suspicious behaviors  
- Repeated anomalous patterns  
- High-risk combinations of events  
- Indicators of compromise (IoCs)  

No rules or logs are ever sent online.

---

##  Rule Types

### **1. Threshold-Based Rules**
Trigger when something happens too often in a short time:
- Multiple failed network connections  
- Repeated privilege elevation attempts  
- Excessive file modifications  

---

### **2. Sequence Rules**
Detect harmful event chains:
- Process → network → persistence  
- Script execution → system modification  
- Unknown process → sensitive file access  

---

### **3. Time-Window Rules**
Identify patterns only visible over time:
- Gradual privilege escalation  
- Slow lateral movement  
- Hourly failed connections  

---

### **4. Entity-Specific Rules**
Target activity involving:
- A specific file path  
- A specific process  
- A specific registry/config entry  

---

##  How Nyroxis Evaluates Rules
The engine matches rules against:
- Event metadata  
- Timestamps  
- Process lineage  
- Network endpoints  
- Severity indicators  

Evaluations are real-time and fully local.

---

##  Rule Hit Details
When a rule is triggered, Nyroxis provides:
- A clear explanation  
- Involved events  
- Severity level  
- Recommended actions  
- Context panel with supporting details  

---

##  Privacy Guarantee
All rule matching:
- Happens locally  
- Does not communicate with external services  
- Uses encrypted event data only  
- Never uploads logs or pattern matches  

---

##  Summary
Rule Matching brings structured, SIEM-like detection to personal endpoints — but without cloud dependency or loss of privacy.
