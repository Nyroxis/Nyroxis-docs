# Datenfluss

Dieser Abschnitt erklärt, wie Daten innerhalb von Nyroxis fließen — von der Ereigniserfassung bis zur Interpretation durch den Benutzer — während sie bei jedem Schritt vollständig lokal, verschlüsselt und privat bleiben.

---

## 1. Ereigniserfassung (Nyroxis Agent)

Nyroxis Agent überwacht kontinuierlich:
- Prozesse und Dienste
- Netzwerkverbindungen und Datenverkehrs-Metadaten
- Dateisystemänderungen und Registry-Modifikationen
- Rechtebezogene Aktionen
- System- und Sicherheitsereignisse (Windows-Ereignisprotokolle)
- PowerShell- und Skriptausführung

Alle Daten werden **lokal** erfasst, ohne jegliche Cloud-Interaktion.

---

## 2. Normalisierung und Verschlüsselung an der Quelle

Unmittelbar nach der Erfassung:
- Ereignisse werden normalisiert und mit Kontext angereichert
- Die Nutzlast wird mit AES-256 verschlüsselt
- Ein Integritäts-Hash wird angewendet
- Daten werden ausschließlich in verschlüsselter Form in die lokale Datenbank geschrieben

Kein Klartext berührt jemals den Datenträger.

---

## 3. Lokale verschlüsselte Datenbank

Verschlüsselte Ereignisse werden in einer sicheren SQLite-Datenbank gespeichert.

Eigenschaften:
- Vollständig verschlüsselt im Ruhezustand (AES-256)
- Hash-verkettete Ereignisblöcke zur Manipulationserkennung
- Strukturiert für schnelle Suchabfragen und Zeitstrahlrekonstruktion
- Keine externe Übertragung — niemals

Die Datenbank verlässt das Gerät niemals.

---

## 4. Nyroxis Intelligence — Regel-Engine

Nyroxis Intelligence liest aus der verschlüsselten Datenbank und wertet Ereignisse über drei Schichten aus:
- **27 Erkennungsregeln** — Mustererkennung einzelner Ereignisse
- **12 Korrelationsregeln** — Multi-Ereignis-Mustererkennung über die Zeit
- **2 Kettenregeln** — Erkennung mehrstufiger Angriffsequenzen

Wenn eine Regel ausgelöst wird:
- Wird sofort eine Warnung ausgegeben
- Der Fund wird in einer dedizierten Erkennungsdatenbank gespeichert
- Der Benutzer wird über das Dashboard benachrichtigt

---

## 5. Lokale KI/ML-Engine

Parallel dazu verarbeitet die KI/ML-Engine Ereignisse lokal:
- Isolation-Forest-Anomalie-Scoring
- Z-Score-Statistikklassifizierung
- Verhaltensbasislinie-Vergleich
- Identifikation beitragender Merkmale

Alle Berechnungen verbleiben auf dem Gerät — keine Cloud-Inferenz, kein Datenaustausch.

---

## 6. Dashboard-Visualisierung

Das Nyroxis Dashboard wandelt all das oben Genannte um in:
- Ereignisprotokolle mit forensischer Suche und Filterung
- Erkennungs-, Korrelations- und Kettenbefunde
- KI/ML-Anomalieergebnisse mit Aufschlüsselung der beitragenden Merkmale
- Diagramme, Schweregradindikatoren und Trendanalysen
- Exportierbare Berichte (PDF/CSV)

Alles bleibt lokal und privat.

---

## Vollständiger Datenlebenszyklus

```
[ Systemereignisse ]
        ↓
[ Nyroxis Agent ]          ← erfassen, normalisieren, verschlüsseln
        ↓
[ Lokale verschlüsselte DB ] ← AES-256, SQLite, hash-verkettet
        ↓
[ Nyroxis Intelligence ]   ← 27 Erkennung + 12 Korrelation + 2 Kettenregeln
        ↓
[ Lokale KI/ML-Engine ]    ← Isolation Forest + statistische Analyse
        ↓
[ Nyroxis Dashboard ]      ← Sichtbarkeit, Forensik, Berichterstellung
        ↑
[ Nyroxis System Guardian ] ← überwacht, sichert, validiert Lizenz
```

In keiner Phase werden Protokolle oder sensible Daten auf externe Server hochgeladen.

---

## Zusammenfassung
Nyroxis pflegt einen strikt lokalen, verschlüsselten und datenschutzorientierten Datenfluss — und gibt Benutzern vollständige Sichtbarkeit und forensisch verwertbare Beweise, ohne Informationen an die Cloud oder Dritte preiszugeben.
