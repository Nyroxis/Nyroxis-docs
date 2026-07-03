# Architekturkomponenten

Dieser Abschnitt beschreibt die einzelnen Hauptkomponenten der Nyroxis-Plattform.
Alle Komponenten sind so konzipiert, dass sie lokal, effizient und nach einem datenschutzorientierten Ansatz arbeiten.

---

## 1. Nyroxis Agent

Der zentrale Überwachungs- und Erfassungsdienst, der auf dem Gerät läuft.

### Aufgaben
- Erfasst Sicherheitsereignisse gleichzeitig aus mehreren Systemkanälen
- Überwacht Prozesse, Netzwerkaktivität, Dateisystem, Registry und rechtebezogene Aktionen
- Normalisiert Ereignisdaten in Echtzeit
- Verschlüsselt die Nutzlast sofort und schreibt sie in die lokale Datenbank
- Gewährleistet manipulationsresistente Integrität über hash-verkettete Ereignisblöcke

### Eigenschaften
- ~57 MB RAM, ~0,1 % CPU
- Läuft still als Windows-Dienst im Hintergrund
- Offline-First — nichts verlässt das Gerät

---

## 2. Nyroxis Intelligence

Die Erkennungs- und Korrelations-Engine — der analytische Kern der Plattform.

### Drei Erkennungsschichten

| Schicht | Regeln | Zweck |
|---------|--------|-------|
| nyroxis_detection | 27 | Bekannte Bedrohungsmuster in einzelnen Ereignissen identifizieren |
| nyroxis_correlations | 12 | Zusammenhängende verdächtige Ereignisse über Zeit und Quellen verknüpfen |
| nyroxis_chains | 2 | Mehrstufige Angriffsequenzen erkennen |

### Eigenschaften
- Arbeitet mit hoher Geschwindigkeit gleichzeitig über alle drei Schichten
- Die Regelbibliothek wächst kontinuierlich, wenn neue Bedrohungen auftauchen
- Vollständig erweiterbar — Sicherheitsprofis können benutzerdefinierte Regeln im JSON-Format schreiben und einsetzen, ohne das Kernsystem zu modifizieren
- ~87 MB RAM, ~1,8 % CPU

---

## 3. Nyroxis System Guardian

Der Plattformwächter — läuft still als Windows-Systemtray-Anwendung.

### Aufgaben
- Überwacht Nyroxis Agent und Nyroxis Intelligence kontinuierlich
- Erkennt unerwartete Dienststopps und leitet Korrekturmaßnahmen ein
- Verwaltet geplante und bedarfsgesteuerte Datenbanksicherungen
- Validiert die HWID-basierte Lizenz offline (AES-GCM + HMAC-Überprüfung)
- Stoppt automatisch alle Dienste, wenn die Lizenz abläuft oder ungültig wird
- Prüft in konfigurierbaren Intervallen auf Plattform-Updates

### Eigenschaften
- ~6,5 MB RAM, ~0,1 % CPU
- Vollständig offline-Lizenzvalidierung — kein Internet erforderlich
- Entscheidend für Plattformresilienz und forensische Integrität

---

## 4. Lokale verschlüsselte Datenbank

Nyroxis verwendet eine gesicherte SQLite-Datenbank, um alle erfassten Ereignisse zu speichern.

### Merkmale
- Vollständige Verschlüsselung im Ruhezustand (AES-256)
- Hash-verkettete Ereignisblöcke zur Manipulationserkennung
- Strukturierte Ereignisspeicherung mit Integritätsverifikation
- Optimiert für schnelle Suchabfragen und Zeitstrahlrekonstruktion
- Kein Cloud-Upload — der Benutzer ist alleiniger Eigentümer der Daten

---

## 5. Nyroxis Dashboard

Eine visuelle Schnittstelle, die rohe Sicherheitsdaten in verwertbare Erkenntnisse umwandelt.

### Bietet
- Echtzeit-Ereignisüberwachung mit forensischer Suche und Filterung
- Visualisierung von Erkennungs-, Korrelations- und Kettenergebnissen
- Integrierte lokale KI/ML-Engine (Isolation Forest + statistische Analyse)
- Berichterstellung — PDF/CSV-Export
- Verwaltung von Datenbanksicherungen
- Mehrsprachige Oberfläche: Englisch, Französisch, Deutsch

### Zielgruppe
Sowohl nicht-technische Benutzer als auch Cybersicherheitsprofis können es effektiv nutzen.

---

## 6. Lokale KI/ML-Engine

Eine vollständig offline-fähige Anomalieerkennungs-Engine, die in das Dashboard eingebettet ist.

### Funktionen
- Isolation-Forest-Algorithmus (100 Bäume, 256 Samples, 8 Verhaltensmerkmale)
- Z-Score-Statistikklassifizierung: Kritisch / Hoch / Mittel / Niedrig
- IQR-Ausreißererkennung, gleitende Durchschnitte, Spike-Erkennung
- Aufbau einer Verhaltensbasislinie und Abweichungs-Scoring
- Identifikation beitragender Merkmale für den Analysten-Kontext

Alles läuft lokal — keine Cloud, keine Telemetrie, kein Datenaustausch.

---

## Zusammenfassung
Nyroxis besteht aus modularen, Local-First-Komponenten, die zusammenarbeiten, um Benutzern Sichtbarkeit und Erkennung auf Unternehmensebene zu bieten — privat, effizient und ohne Cloud-Abhängigkeit.
