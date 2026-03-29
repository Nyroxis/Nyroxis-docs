# KI & Machine-Learning-Engine — Übersicht

Die Nyroxis KI/ML-Engine ist ein vollständig lokales, offline betriebenes Anomalieerkennungssystem, das in das Dashboard integriert ist.
Es analysiert Sicherheitsereignisse, ohne Daten in die Cloud zu senden, und liefert verhaltensbasierte Intelligenz mit absoluter Privatsphäre.

---

## Ein anderer Ansatz für KI

Die meisten KI-gestützten Sicherheitslösungen verlassen sich auf Cloud-Infrastruktur — sie senden Telemetriedaten zur Analyse an Remote-Server.
Nyroxis verfolgt den entgegengesetzten Ansatz: Jeder Aspekt der KI-Engine läuft lokal, auf dem eigenen Gerät des Benutzers.
Es werden keine Daten übertragen. Es wird kein externer Dienst konsultiert. Kein Verhaltensprofil verlässt jemals das Gerät.

Dies ist keine Einschränkung — es ist ein bewusstes architektonisches Bekenntnis zum Datenschutz.

---

## Was die KI-Engine bietet

- Verhaltensanomaliedetektion mit Isolation Forest
- Statistische Analyse: Z-Score, IQR, gleitende Durchschnitte, Spike-Erkennung
- Schweregradklassifizierung: Kritisch / Hoch / Mittel / Niedrig
- Identifikation beitragender Merkmale — erklärt *warum* etwas markiert wurde
- Aufbau einer Verhaltensbasislinie pro Gerät

---

## Isolation Forest — Kernalgorithmus

Im Kern der Engine befindet sich eine benutzerdefinierte Implementierung des Isolation-Forest-Algorithmus, vollständig in Rust entwickelt — keine externe ML-Bibliothek erforderlich.

**Funktionsweise:**
Isolation Forest baut einen Wald aus zufälligen Entscheidungsbäumen. Anomale Ereignisse sind statistisch selten oder strukturell ungewöhnlich — sie benötigen weniger Splits zur Isolation und erhalten daher einen höheren Anomalie-Score.

**Implementierung:**
- 100 Isolationsbäume pro Analysezyklus
- Maximal 256 Stichproben pro Baum
- 8 Verhaltensmerkmale pro Analysefenster
- Anomalie-Score > 0,6 löst eine Erkennung aus

---

## 8 analysierte Verhaltensmerkmale

| Merkmal | Beschreibung |
|---------|-------------|
| Ereignisanzahl | Gesamtzahl der Ereignisse im Analysefenster |
| Eindeutige Quellen | Anzahl der unterschiedlichen Ereignisquellen |
| Eindeutige Ziele | Anzahl der unterschiedlichen Netzwerkziele |
| Tageszeit | Zeitlicher Kontext für die Verhaltensbasislinie |
| Wochentag | Wöchentliche Mustererkennung |
| Ereignisse pro Stunde | Normalisierung der Aktivitätsrate |
| Neue-Quellen-Verhältnis | Anteil bisher ungesehener Quellen |
| Neue-Ziele-Verhältnis | Anteil bisher ungesehener Ziele |

Alle Merkmale werden vor der Analyse mittels Z-Score-Standardisierung normalisiert.

---

## Statistische Analyse-Engine

Parallel zu Isolation Forest laufend:

| Z-Score | Schweregrad | Konfidenz |
|---------|----------|------------|
| > 3,0 | Kritisch | 99,7 % |
| > 2,0 | Hoch | 95 % |
| > 1,5 | Mittel | 86 % |
| > 1,0 | Niedrig | 68 % |

Weitere Methoden: IQR-Ausreißererkennung, gleitender Durchschnitt, exponentieller gleitender Durchschnitt, Spike-Erkennung, Korrelationsanalyse.

---

## Vollständige Datenschutzgarantie

Die KI-Engine:
- Läuft vollständig offline
- Verarbeitet ausschließlich lokal verschlüsselte Ereignisdaten
- Sendet niemals Daten an Server
- Lädt niemals Verhaltensprofile hoch
- Verwendet niemals Cloud-Inferenz oder Online-APIs

Die KI-Engine gehört vollständig dem Gerät des Benutzers.

---

## Zusammenfassung

Die Nyroxis KI/ML-Engine bietet On-Device-Isolation-Forest-Anomalieerkennung kombiniert mit statistischer Analyse — und liefert verhaltensbasierte Intelligenz in Cloud-Qualität ohne Datenschutzkompromiss.
