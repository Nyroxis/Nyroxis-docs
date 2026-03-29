# Übergeordnete Architektur

Die Nyroxis-Architektur ist darauf ausgelegt, starke Sicherheit, vollständige Privatsphäre und komplette offline Autonomie zu bieten.
Diese übergeordnete Übersicht erläutert, wie alle wichtigen Komponenten zusammenarbeiten, während die Benutzerdaten lokal geschützt und verschlüsselt bleiben.

---

## Grundlegende Architekturprinzipien

### 1. Vollständig lokaler Betrieb
Alle Verarbeitung — Erfassung, Erkennung, KI-Analyse, Speicherung, Berichte — findet auf dem Gerät statt. Nichts wird hochgeladen oder übertragen.

### 2. Datenschutz durch Design
Keine Cloud. Keine Telemetrie. Keine Fernüberwachung. Kein Verhaltens-Profiling.

### 3. Leichtgewichtig und effizient
Konzipiert für den Dauerbetrieb auf persönlichen Laptops ohne Beeinträchtigung der täglichen Produktivität.

### 4. Forensische Integrität
Ereignisprotokolle sind verschlüsselt, hash-verkettet und manipulationssicher — geeignet für rechtliche und regulatorische Verfahren.

---

## Übergeordnete Komponenten

### 1. Nyroxis Agent
- Erfasst Systemereignisse in Echtzeit aus mehreren Kanälen
- Normalisiert und verschlüsselt sofort
- Speichert verschlüsselte Ereignisse in der lokalen Datenbank
- ~57 MB RAM, ~0,1 % CPU

### 2. Nyroxis Intelligence
- Bewertet Ereignisse anhand von 27 Erkennungs- + 12 Korrelations- + 2 Kettenregeln
- Löst sofortige Warnungen bei Regelübereinstimmungen aus
- Vollständig erweiterbar durch Sicherheitsexperten (JSON-Regelformat)
- ~87 MB RAM, ~1,8 % CPU

### 3. Nyroxis System Guardian
- Überwacht Agent und Intelligence alle 3 Sekunden
- Verwaltet Sicherungen und offline HWID-Lizenzvalidierung
- Stoppt Dienste, wenn die Lizenz abläuft
- ~6,5 MB RAM, ~0,1 % CPU

### 4. Sichere Lokale Datenbank
- SQLite mit AES-256-Verschlüsselung
- Hash-verkettete Ereignisblöcke zur Manipulationserkennung
- Speichert Ereignisse, Befunde, KI-Ergebnisse und Baselines
- Verlässt das Gerät niemals

### 5. Lokale KI/ML-Engine
- Isolation Forest Anomalieerkennung (100 Bäume, 8 Merkmale)
- Z-Score, IQR, gleitender Durchschnitt, Spitzenwert-Erkennung
- Aufschlüsselung beitragender Merkmale für Analysten
- Vollständig offline — keine Cloud-Inferenz

### 6. Nyroxis Dashboard
- Echtzeit-Sichtbarkeit: Ereignisse, Erkennungen, Korrelationen, Ketten, KI/ML
- Forensische Suche, Diagramme, Berichte (PDF/CSV)
- Sicherungsverwaltung, Einstellungen, mehrsprachig (EN/FR/DE)
- Alle Daten lokal abgerufen

---

## Sicherheitsschichten

Die Architektur umfasst mehrere Verteidigungsschichten:
- Verschlüsselung bei der Erfassung (AES-256)
- Hash-verkettete Ereignisstrukturen
- Geschützte Schreibpfade
- Plattformwächter für Dienst-Resilienz
- Offline-Lizenzvalidierung
- Keinerlei externe Kommunikation

---

## Datenflusszusammenfassung

```
[ Systemereignisse ]
        ↓
[ Nyroxis Agent ]          ← erfassen, normalisieren, verschlüsseln
        ↓
[ Lokale Verschlüsselte DB ]  ← AES-256, SQLite, hash-verkettet
        ↓
[ Nyroxis Intelligence ]   ← 27 Erkennungs- + 12 Korrelations- + 2 Kettenregeln
        ↓
[ Lokale KI/ML-Engine ]    ← Isolation Forest + statistische Analyse
        ↓
[ Nyroxis Dashboard ]      ← Sichtbarkeit, Forensik, Berichte
        ↑
[ Nyroxis System Guardian ] ← überwacht, sichert, validiert Lizenz
```

---

## Zusammenfassung

Die Nyroxis-Architektur liefert leistungsstarke, private, offline Sicherheit durch die Kombination von vier Kernkomponenten — Agent, Intelligence, System Guardian und Dashboard — die zusammen mit lokaler KI/ML und forensisch geeignetem Speicher arbeiten, vollständig ohne Cloud-Exposition.
