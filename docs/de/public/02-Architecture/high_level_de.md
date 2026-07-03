# Architekturübersicht

Nyroxis basiert auf einer leichtgewichtigen, datenschutzorientierten Architektur, die darauf ausgelegt ist, Sichtbarkeit und Erkennung auf Unternehmensebene zu liefern, ohne auf die Cloud angewiesen zu sein.
Das System läuft vollständig auf dem Gerät des Benutzers und besteht aus vier unabhängigen Komponenten, die sicher zusammenarbeiten.

---

## Kernkomponenten

### 1. Nyroxis Agent
Ein leichtgewichtiger Endpunktmonitor, der:
- Sicherheitsrelevante Ereignisse aus mehreren Systemkanälen erfasst
- Sie sofort bei der Erfassung normalisiert und verschlüsselt
- Alles in einer lokalen, manipulationsresistenten Datenbank speichert
- 100 % offline arbeitet — ~57 MB RAM, ~0,1 % CPU

### 2. Nyroxis Intelligence
Eine hochgeschwindigkeits-Erkennungs- und Korrelations-Engine, die:
- 27 Erkennungsregeln auf einzelne Ereignisse anwendet
- 12 Korrelationsregeln über zusammenhängende Ereignisse im Zeitverlauf ausführt
- 2 Kettenregeln ausführt, um mehrstufige Angriffsequenzen zu erkennen
- Bei jeder Regelübereinstimmung sofortige Alarme auslöst
- Benutzerdefinierte Regeln von Sicherheitsprofis akzeptiert
- ~87 MB RAM, ~1,8 % CPU

### 3. Nyroxis System Guardian
Ein stiller Systemtray-Wächter, der:
- Nyroxis Agent und Intelligence kontinuierlich überwacht
- Backups und HWID-basierte Lizenzvalidierung verwaltet (vollständig offline)
- Automatisch auf Updates prüft
- Dienste automatisch stoppt, wenn die Lizenz abläuft
- ~6,5 MB RAM, ~0,1 % CPU

### 4. Nyroxis Dashboard
Eine klare und intuitive Oberfläche, die:
- Ereignisse, Erkennungen, Korrelationen und Ketten anzeigt
- Forensische Suche, Diagramme und PDF/CSV-Berichte bereitstellt
- Eine lokale KI/ML-Engine enthält (Isolation Forest + statistische Analyse)
- Englisch, Französisch und Deutsch unterstützt

---

## Datenfluss auf hoher Ebene

```
[ Systemereignisse ]
        ↓
[ Nyroxis Agent ]          ← erfassen, normalisieren, verschlüsseln
        ↓
[ Lokale verschlüsselte DB ] ← AES-256, SQLite, hash-verkettet
        ↓
[ Nyroxis Intelligence ]   ← 27 Erkennung + 12 Korrelation + 2 Kettenregeln
        ↓
[ Nyroxis Dashboard ]      ← Sichtbarkeit, KI/ML, Forensik, Berichterstellung
        ↑
[ Nyroxis System Guardian ] ← überwacht, sichert, validiert Lizenz
```

In keiner Phase werden Protokolle oder sensible Daten auf externe Server hochgeladen.

---

## Designprinzipien

### Datenschutz by Design
- Keine Cloud-Ingestion
- Lokale Verschlüsselung bei der Erfassung
- Der Benutzer behält jederzeit die volle Kontrolle

### Forensische Integrität
- AES-256-verschlüsselte Protokolle
- Hash-verkettete Ereignisblöcke
- Manipulationsresistenter Speicher, geeignet für Rechtsverfahren

### Leichtgewichtiger Betrieb
Entwickelt, um auf persönlichen Laptops und Workstations reibungslos zu laufen, ohne die tägliche Produktivität zu beeinträchtigen.

### Offline-First-Sicherheit
Keine Internetverbindung erforderlich für:
- Überwachung und Erkennung
- KI/ML-Analyse
- Dashboard-Nutzung
- Lizenzvalidierung

### Erweiterbarkeit
Sicherheitsprofis können benutzerdefinierte Erkennungs-, Korrelations- und Kettenregeln schreiben und einsetzen, ohne das Kernsystem zu modifizieren.

---

## Zusammenfassung
Nyroxis bietet eine moderne, modulare und forensisch fundierte Architektur, die professionelle Sichtbarkeit und Erkennung auf persönliche Geräte bringt — vollständig offline, mit vollständigem Respekt für die Privatsphäre des Benutzers.
