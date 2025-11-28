# Datenfluss

Dieser Abschnitt beschreibt, wie Daten innerhalb von Nyroxis verarbeitet werden – von der Ereigniserfassung bis zur Darstellung im Dashboard – vollständig lokal, verschlüsselt und datenschutzorientiert.

Nyroxis folgt einem einfachen, transparenten und privacy-first orientierten Datenlebenszyklus.

---

## 1. Ereigniserfassung
Der Nyroxis Agent überwacht kontinuierlich:
- Prozesse  
- Netzwerkverbindungen  
- Dateiänderungen  
- Berechtigungsbezogene Aktionen  
- System- und Sicherheitsereignisse  

Alle Daten werden **lokal** erfasst – ohne jegliche Cloud-Interaktion.

---

## 2. Verschlüsselung an der Quelle
Unmittelbar nach der Erfassung:
- werden Ereignisse verschlüsselt  
- werden Integritätsschutzmechanismen angewendet  
- wird das Datenmaterial manipulationsresistent  

So können Angreifer Protokolle weder lesen noch verändern.

---

## 3. Lokale verschlüsselte Datenbank
Die verschlüsselten Ereignisse werden in einem sicheren lokalen Datenspeicher abgelegt.

Eigenschaften:
- vollständig verschlüsselt im Ruhezustand  
- strukturiert für schnelle Abfragen  
- optimiert für die Erstellung von Zeitachsen  
- keinerlei externe Übertragung  

Die Datenbank verlässt das Gerät niemals.

---

## 4. Lokale Analyse-Engine
Die Analyse-Engine verarbeitet die verschlüsselten Daten lokal und generiert:
- Verhaltensanalysen  
- Anomalieerkennung  
- KI-gestützte Bewertungen  
- Korrelationen zwischen Ereignissen  

Keine externen Server oder Cloud-Dienste werden verwendet.

---

## 5. Dashboard-Visualisierung
Das Nyroxis Dashboard verwandelt technische Daten in:
- Logansichten  
- Warnungen  
- Diagramme und Trends  
- Schweregradindikatoren  
- einfach verständliche Erläuterungen  

Alles erfolgt lokal und privat.

---

## Vollständiges Datenflussdiagramm

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

---

## Zusammenfassung
Nyroxis gewährleistet einen strikt lokalen, verschlüsselten und datenschutzorientierten Datenfluss – für maximale Transparenz ohne Preisgabe persönlicher Informationen.
