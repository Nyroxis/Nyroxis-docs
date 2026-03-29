# Lokale KI/ML-Engine

Die Nyroxis KI/ML-Engine ist vollständig lokal und offline.
Sie führt alle Verhaltensanalysen, Anomalieerkennung und statistische Bewertung **durch, ohne Daten an die Cloud zu senden**.

---

## 1. Vollständig Offline-Engine

Die KI/ML-Engine läuft vollständig auf dem Gerät:
- Keine Serverkommunikation
- Keine Online-Modellaktualisierungen
- Keine Telemetrie
- Keine externen Abhängigkeiten

Alle Inferenz und Verarbeitung sind innerhalb der lokalen Laufzeitumgebung isoliert.
In Rust entwickelt ohne externe ML-Bibliotheksabhängigkeit.

---

## 2. Isolation Forest — Kernalgorithmus

Die Engine implementiert einen angepassten Isolation Forest-Algorithmus:
- 100 Isolationsbäume pro Analysezyklus
- Maximal 256 Stichproben pro Baum
- 8 Verhaltensmerkmale pro Analysefenster
- Anomalie-Score-Schwellenwert: 0,6

Anomale Ereignisse benötigen weniger Teilungen zur Isolation — kürzerer Isolationspfad = höherer Anomalie-Score.

**8 analysierte Verhaltensmerkmale:**

| Merkmal | Beschreibung |
|---------|--------------|
| Ereignisanzahl | Gesamtereignisse im Analysefenster |
| Eindeutige Quellen | Verschiedene Ereignisquellen |
| Eindeutige Ziele | Verschiedene Netzwerkziele |
| Tageszeit | Zeitlicher Kontext für Verhaltens-Baseline |
| Wochentag | Wöchentliche Mustererkennung |
| Ereignisse pro Stunde | Normalisierung der Aktivitätsrate |
| Neue-Quellen-Verhältnis | Anteil bisher unbekannter Quellen |
| Neue-Ziele-Verhältnis | Anteil bisher unbekannter Ziele |

---

## 3. Statistische Analyse-Engine

Parallel zu Isolation Forest laufend:

| Z-Score | Schweregrad | Konfidenz |
|---------|-------------|-----------|
| > 3,0 | Kritisch | 99,7 % |
| > 2,0 | Hoch | 95 % |
| > 1,5 | Mittel | 86 % |
| > 1,0 | Niedrig | 68 % |

Zusätzliche Methoden:
- IQR-Ausreißererkennung
- Einfache und exponentielle gleitende Durchschnitte
- Spitzenwert-Erkennung gegenüber historischen Baselines
- Korrelationsanalyse zwischen Verhaltenssignalen

---

## 4. Erklärbare Ergebnisse

Jede Erkennung enthält:
- Anomalie-Score (0,0–1,0)
- Schweregrad-Klassifizierung
- Beitragende Merkmale — die spezifischen Verhaltensdimensionen, die am stärksten abgewichen sind, mit Z-Score-Werten

Das System hebt hervor, **warum** etwas verdächtig ist — transparent und lokal überprüfbar.

---

## 5. Lokale Verhaltens-Baselines

Jedes Gerät erstellt sein eigenes privates Baseline-Profil:
- Normale Prozessaktivität
- Typische Netzwerkverbindungsmuster
- Erwartete Dateizugriffsmuster
- Übliches Tageszeit- und Wochentagsverhalten

Baselines:
- Lokal in verschlüsselter Form gespeichert
- Jederzeit vom Benutzer zurücksetzbar
- Niemals übertragen oder geteilt

---

## 6. Kein Cloud-Training oder Hochladen

Die KI/ML-Engine lädt **nicht** hoch:
- Protokolle oder Ereignisdaten
- Anomalie-Stichproben
- Verhaltensprofile
- Modell-Feedback
- Keinerlei Benutzerdaten

Training und Inferenz erfolgen ausschließlich offline.

---

## 7. Leichtgewichtig und Ressourceneffizient

Optimiert für persönliche Laptops, Führungskräfte-Geräte und Air-Gapped-Systeme — die KI/ML-Engine bietet starke Verhaltenserkennung ohne Enterprise-Hardware zu erfordern.

---

## Zusammenfassung

Die Nyroxis KI/ML-Engine gewährleistet:
- Ausschließlich lokale Inferenz — keine Cloud-Abhängigkeit
- Vollständige Privatsphäre — keine Datenweitergabe
- Starke Verhaltenserkennung über Isolation Forest
- Statistische Tiefe über Z-Score, IQR und Spitzenwert-Erkennung
- Transparente, erklärbare Ergebnisse mit beitragenden Merkmalen
