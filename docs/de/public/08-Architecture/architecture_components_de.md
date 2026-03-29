# Architekturkomponenten

Dieser Abschnitt beschreibt jeden Kernbestandteil der Nyroxis-Plattform und erläutert, wie sie zusammenarbeiten, um private, offline und manipulationssichere Sicherheit zu gewährleisten.

---

## 1. Nyroxis Agent

Der schlanke Hintergrunddienst, verantwortlich für:
- Überwachung von Prozessen, Netzwerkverbindungen, Dateiänderungen und Berechtigungsaktivitäten
- Erfassung von Windows-Ereignisprotokolleinträgen (Sicherheit, System, Anwendung)
- Überwachung von PowerShell- und Skriptausführungen
- Normalisierung von Ereignisdaten in Echtzeit
- Sofortige Verschlüsselung jedes Ereignisses vor dem Schreiben

Eigenschaften:
- ~57 MB RAM, ~0,1 % CPU
- Stiller Windows-Dienst
- Vollständig offline — nichts verlässt das Gerät

---

## 2. Nyroxis Intelligence

Die Erkennungs- und Korrelations-Engine:
- **27 Erkennungsregeln** — bekannte Bedrohungsmuster in einzelnen Ereignissen
- **12 Korrelationsregeln** — Muster über zusammenhängende Ereignisse hinweg
- **2 Kettenregeln** — Erkennung mehrstufiger Angriffssequenzen

Eigenschaften:
- ~87 MB RAM, ~1,8 % CPU
- Vollständig erweiterbar — Sicherheitsexperten können eigene Regeln im JSON-Format schreiben und bereitstellen
- Löst sofortige Warnungen bei Regelübereinstimmungen aus
- Speichert Befunde in dedizierten Erkennungsdatenbanken

---

## 3. Nyroxis System Guardian

Der Plattformwächter, der als Systemtray-Anwendung läuft:
- Überwacht Nyroxis Agent und Intelligence alle 3 Sekunden
- Verwaltet geplante und auf Anfrage durchgeführte Datenbanksicherungen
- Validiert HWID-basierte Lizenzen offline (AES-GCM + HMAC)
- Stoppt Dienste automatisch, wenn die Lizenz abläuft
- Prüft Plattform-Updates in konfigurierbaren Intervallen

Eigenschaften:
- ~6,5 MB RAM, ~0,1 % CPU
- Vollständig offline Lizenzvalidierung
- Entscheidend für die Plattformresilienz und forensische Integrität

---

## 4. Sichere Lokale Datenbank

Eine geschützte SQLite-Datenbank mit:
- Verschlüsselten Ereignisprotokollen
- Erkennungs- und Korrelationsbefunden
- KI/ML-Analyseergebnissen
- Verhaltens-Baselinedaten
- Metadaten zur forensischen Zeitachsenrekonstruktion

Sicherheitsmerkmale:
- AES-256-Verschlüsselung im Ruhezustand
- Hash-verkettete Ereignisblöcke zur Manipulationserkennung
- Geschützte Schreibpfade
- Integritätsprüfung bei jedem Lesevorgang

Die Datenbank **verlässt das Gerät niemals**.

---

## 5. Lokale KI/ML-Engine

Die offline Anomalieerkennungs-Engine, eingebettet in das Dashboard:
- Angepasster Isolation Forest (100 Bäume, 256 Stichproben, 8 Verhaltensmerkmale)
- Z-Score-statistische Klassifizierung: Kritisch / Hoch / Mittel / Niedrig
- IQR-Ausreißererkennung, gleitende Durchschnitte, Spitzenwert-Erkennung
- Identifikation beitragender Merkmale mit Z-Score-Werten
- Lokaler Aufbau der Verhaltens-Baseline

Keine Cloud, keine externe ML-Bibliothek, keine Datenweitergabe.

---

## 6. Nyroxis Dashboard

Die Benutzeroberfläche bietet:
- Echtzeit-Ereignisüberwachung mit forensischer Suche und Filterung
- Visualisierung von Erkennungs-, Korrelations- und Kettenergebnissen
- KI/ML-Analyse mit Aufschlüsselung der beitragenden Merkmale
- Berichte — PDF/CSV-Export
- Verwaltung von Datenbanksicherungen
- Einstellungen und Aufbewahrungssteuerung
- Mehrsprachig: Englisch, Französisch, Deutsch

Alles Angezeigte wird lokal aus der sicheren Datenbank abgerufen.

---

## Zusammenfassung

Die Nyroxis-Komponenten arbeiten als integriertes, privates, offline-Ökosystem — und bieten Sichtbarkeit auf Unternehmensniveau, mehrschichtige Erkennung, lokale KI/ML-Intelligenz und forensisch verwertbare Nachweise, ohne Benutzerdaten in die Cloud zu übertragen.
