# Rule Matching

Das Rule Matching Modul ermöglicht es Nyroxis, Ereignisse hervorzuheben, die vordefinierten Sicherheitsregeln entsprechen.  
Es bringt SIEM-ähnliche Logik auf persönliche Endgeräte — vollständig offline und datenschutzorientiert.

## Was Rule Matching macht
Nyroxis bewertet Ereignisse nach lokalen Regeln, um zu erkennen:
- verdächtige Verhaltensweisen  
- wiederkehrende Anomalien  
- riskante Kombinationen von Ereignissen  
- Indikatoren für Kompromittierungen (IoCs)  

Keine Regeln oder Logs werden jemals online übertragen.

## Regeltypen

### **1. Schwellenwertbasierte Regeln**
Werden ausgelöst, wenn etwas zu oft in kurzer Zeit passiert:
- mehrere fehlgeschlagene Netzwerkverbindungen  
- wiederholte Versuche der Rechteerhöhung  
- exzessive Dateiänderungen  

### **2. Sequenzregeln**
Erkennen gefährliche Ereignisketten:
- Prozess → Netzwerk → Persistenz  
- Skriptausführung → Systemänderung  
- unbekannter Prozess → Zugriff auf sensible Datei  

### **3. Zeitfenster-Regeln**
Identifizieren Muster, die nur über einen größeren Zeitraum sichtbar sind:
- schrittweise Eskalation von Rechten  
- langsame laterale Bewegung  
- stündliche Fehlverbindungen  

### **4. Entitätsspezifische Regeln**
Zielen auf Aktivitäten im Zusammenhang mit:
- einem bestimmten Dateipfad  
- einem bestimmten Prozess  
- einem bestimmten Konfigurations-/Registry-Eintrag  

## Wie Nyroxis Regeln bewertet
Die Engine gleicht Regeln ab mit:
- Ereignismetadaten  
- Zeitstempeln  
- Prozessverläufen  
- Netzwerkendpunkten  
- Schweregradindikatoren  

Bewertungen erfolgen in Echtzeit und vollständig lokal.

## Details bei Regel-Treffern
Wird eine Regel ausgelöst, liefert Nyroxis:
- eine klare Erklärung  
- beteiligte Ereignisse  
- Schweregrad  
- empfohlene Maßnahmen  
- Kontextinformationen  

## Datenschutzgarantie
Alles Rule Matching:
- erfolgt lokal  
- nutzt nur verschlüsselte Ereignisdaten  
- sendet nie Logs oder Ergebnisse nach außen  

## Zusammenfassung
Rule Matching bringt strukturierte, SIEM-ähnliche Erkennung auf persönliche Endgeräte — ohne Cloud-Abhängigkeit und ohne Datenschutzverlust.
