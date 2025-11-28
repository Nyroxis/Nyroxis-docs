# Data Flow

This section explains how data moves inside Nyroxis — from event collection to user interpretation — while remaining fully local, encrypted, and private.

Nyroxis follows a simple, transparent, privacy-first lifecycle.

---

## 1. Event Collection
The Nyroxis Agent continuously monitors:
- Processes  
- Network connections  
- File changes  
- Privilege actions  
- System & security events  

All data is collected **locally**, without any cloud interaction.

---

## 2. Encryption at Source
Immediately after collection:
- Events are encrypted  
- Integrity protections are applied  
- Data becomes tamper-resistant  

This ensures logs cannot be altered or read by attackers.

---

## 3. Local Encrypted Database
Encrypted events are stored inside a secure, local datastore.

Properties:
- Fully encrypted at rest  
- Structured for fast lookups  
- Optimized for timeline reconstruction  
- No external transmission ever occurs  

The database never leaves the device.

---

## 4. Local Analysis Engine
The analysis engine processes encrypted data locally to generate:
- Behavioral insights  
- Anomaly detection  
- AI-assisted scoring  
- Correlation between events  

No external servers or cloud services are involved.

---

## 5. Dashboard Visualization
The Nyroxis Dashboard transforms technical data into:
- Logs  
- Alerts  
- Charts & trends  
- Severity indicators  
- Explanations in simple language  

Everything remains local and private.

---

## Full Data Lifecycle Diagram

```
[ System Events ] 
        ↓
[ Nyroxis Agent ]
        ↓ (encrypted)
[ Local Encrypted Database ]
        ↓
[ Local Analysis Engine ]
        ↓
[ Nyroxis Dashboard ]
```

---

## Summary
Nyroxis maintains a strictly local, encrypted, and privacy-first data flow — giving users visibility without exposing their information to the cloud or third parties.
