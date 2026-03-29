# KI-Engine — Interne Mechanik

Die Nyroxis KI/ML-Engine ist darauf ausgelegt, vollständig lokal zu laufen und intelligente Analysen auf verschlüsselten Sicherheitsereignissen durchzuführen, ohne auf Cloud-Dienste angewiesen zu sein.

---

## Grundlegende Designprinzipien

### 1. Datenschutz zuerst
- Keine Cloud-Verarbeitung
- Keine externen APIs
- Keine Datenweitergabe

Die gesamte Intelligenz läuft auf dem eigenen Gerät des Benutzers.

### 2. Leichtgewichtige Implementierung
Vollständig in Rust ohne externe ML-Bibliotheken entwickelt:
- ~Geringe CPU-Auslastung
- Minimaler Speicherbedarf
- Echtzeitausführung

### 3. Verhaltensverständnis
Anstatt Ereignisse einzeln zu analysieren, versteht die Engine *Muster*, die zeitübergreifend und über mehrere Ereignisdimensionen hinweg auftreten.

### 4. Vollständig offline
Alle Analysen, Bewertungen und Merkmalsextraktionen finden lokal statt — zu keinem Zeitpunkt ist eine Internetverbindung erforderlich.

---

## Isolation Forest — Funktionsweise

Der Isolation-Forest-Algorithmus isoliert Anomalien, indem er zufällige Entscheidungsbäume aufbaut und misst, wie schnell jeder Datenpunkt vom Rest getrennt wird.

**Das Prinzip:**
- Normale Ereignisse benötigen viele Splits zur Isolation (sie mischen sich mit anderen)
- Anomale Ereignisse benötigen weniger Splits (sie stechen hervor)
- Kürzerer Isolationspfad = höherer Anomalie-Score

**Nyroxis-Implementierung:**
- 100 Isolationsbäume pro Analysezyklus
- 256 zufällige Stichproben pro Baum
- Alle 8 Verhaltensmerkmale vor der Analyse normalisiert
- Anomalie-Score-Schwellenwert: 0,6 (darüber = Erkennung ausgelöst)
- Beitragende Merkmale identifiziert über Z-Score-Abweichung (Schwellenwert: 2,0 Standardabweichungen)

---

## Statistische Analyse-Pipeline

### Z-Score-Klassifizierung
Jeder überwachte Wert wird gegen seine historische Basislinie bewertet:

```
z = (Wert - Mittelwert) / Standardabweichung
```

| |z| | Schweregrad | Konfidenz |
|------|----------|------------|
| > 3,0 | Kritisch | 99,7 % |
| > 2,0 | Hoch | 95 % |
| > 1,5 | Mittel | 86 % |
| > 1,0 | Niedrig | 68 % |

### IQR-Ausreißererkennung
```
untere_Grenze = Q1 - 1,5 × IQR
obere_Grenze = Q3 + 1,5 × IQR
```
Werte außerhalb dieses Bereichs werden als statistische Ausreißer markiert.

### Gleitende Durchschnitte
- **Einfacher gleitender Durchschnitt** — Basislinitentrend über konfigurierbare Zeitfenster
- **Exponentieller gleitender Durchschnitt** — gewichtet neuere Aktivitäten stärker für schnellere Reaktion auf aufkommende Muster

### Spike-Erkennung
```
aktueller_Wert > Mittelwert + (Schwellenmultiplikator × Standardabweichung)
```

---

## Was die Engine ausgibt

Für jeden Analysezyklus:
- `is_anomaly` — boolescher Indikator
- `anomaly_score` — 0,0 bis 1,0 (höher = anomaler)
- `confidence` — 0,0 bis 0,95
- `contributing_features` — Liste der Merkmale mit Z-Scores, die die Erkennung ausgelöst haben

Diese Ausgaben werden im Abschnitt KI / ML-Analyse des Dashboards angezeigt.

---

## Lokale Verhaltensbasislinie

Die Engine erstellt eine private Basislinie pro Gerät:
- Normale Prozessmuster
- Typisches Netzwerkverbindungsverhalten
- Erwartete Dateiaktivität
- Übliches Tageszeit- und Wochentagsverhalten

Die Basislinie ist:
- Lokal in verschlüsselter Form gespeichert
- Jederzeit vom Benutzer zurücksetzbar
- Wird niemals übertragen oder geteilt

---

## Zusammenfassung

Die KI-Engine kombiniert Isolation Forest mit statistischer Analyse, um transparente, erklärbare und datenschutzfreundliche Anomalieerkennung zu liefern — vollständig auf dem Gerät des Benutzers, ohne Cloud-Abhängigkeit.
