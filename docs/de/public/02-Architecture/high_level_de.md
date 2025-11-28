# Architektur – Übersicht

Nyroxis basiert auf einer leichtgewichtigen, datenschutzorientierten Architektur, die Unternehmenssichtbarkeit ohne Cloud-Abhängigkeit ermöglicht.  
Das gesamte System läuft vollständig auf dem Gerät des Nutzers und besteht aus klar definierten, unabhängigen Komponenten, die sicher zusammenarbeiten.

---

## Zentrale Komponenten

Nyroxis besteht aus den folgenden übergeordneten Modulen:

### **1. Nyroxis Agent**
Ein leichtgewichtiger Endpoint-Monitor, der:
- sicherheitsrelevante Ereignisse erfasst  
- sie lokal verschlüsselt und speichert  
- eine manipulationsresistente Datenintegrität gewährleistet  
- vollständig offline arbeitet  

### **2. Lokale verschlüsselte Datenbank**
Alle erfassten Ereignisse werden in:
- einem gesicherten lokalen Datenspeicher  
- vollständig verschlüsselt im Ruhezustand  
- strukturiert für schnelle Analyse und Wiederherstellung von Zeitachsen  

abgelegt.

### **3. Nyroxis Dashboard**
Eine klare und intuitive Benutzeroberfläche, die:
- Logs, Warnungen und Korrelationen darstellt  
- Diagramme und Zeitachsen generiert  
- Erklärungen und Schweregradindikatoren liefert  
- sowohl Experten als auch nicht-technische Nutzer unterstützt  

### **4. Lokale Analyse-Engine**
Nyroxis umfasst:
- leichtgewichtige Verhaltensheuristiken  
- KI-unterstützte Bewertungen  
- Ereigniskorrelationslogik  

Alle Analysen erfolgen **lokal**, um den Datenschutz vollständig zu gewährleisten.

### **5. Optionale Lizenzvalidierung (Local‑First)**
Nyroxis kann die Lizenzintegrität validieren, ohne Ereignisdaten zu übertragen.  
Nur minimale Metadaten – sofern vom Nutzer erforderlich – werden ausgetauscht, niemals Logs.

---

## High-Level Datenfluss

Die Architektur folgt einem einfachen, transparenten Lebenszyklus:

```
[ Systemereignisse ]  
        ↓  
[ Nyroxis Agent ]  
        ↓ (verschlüsselt)
[ Lokale verschlüsselte Datenbank ]  
        ↓  
[ Lokale Analyse-Engine ]  
        ↓  
[ Nyroxis Dashboard ]
```

Zu keinem Zeitpunkt werden Protokolle oder sensible Daten an externe Server übertragen.

---

## Designprinzipien

### **Privacy by Design**
- keine Cloud-Datenverarbeitung  
- lokale Verschlüsselung  
- vollständige Benutzerkontrolle  

### **Einfachheit & Klarheit**
- klare Architektur  
- leicht verständlich  
- geeignet für Familien, Fachkräfte und Experten  

### **Leichtgewichtiges Design**
Optimiert für flüssigen Betrieb – selbst auf älteren Laptops oder Heimgeräten.

### **Offline‑First Sicherheit**
Keine Internetverbindung erforderlich für:
- Überwachung  
- Analyse  
- Dashboard-Nutzung  
- Ereigniskorrelation  

---

## Zusammenfassung
Nyroxis bietet eine moderne, minimalistische und sichere Architektur, die professionelle Sichtbarkeit auf persönliche Geräte bringt – vollständig offline und mit uneingeschränktem Respekt für die Privatsphäre der Nutzer.
