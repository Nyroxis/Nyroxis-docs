# Diagramme & Analysen

Der Bereich Diagramme & Analysen des Nyroxis-Dashboards wandelt rohe Sicherheitsereignisse in visuelle Einblicke um und hilft Benutzern, Trends, Anomalien und potenzielle Risiken schnell zu verstehen.
Alle Analysen werden lokal generiert und wahren die vollständige Privatsphäre.

---

## Zweck der visuellen Analyse

Diagramme helfen Benutzern, wichtige Fragen sofort zu beantworten:
- Nimmt die Aktivität im Laufe der Zeit zu oder ab?
- Gibt es ungewöhnliche Spitzen bei Prozessen oder Netzwerkverkehr?
- Welche Ereigniskategorien treten am häufigsten auf?
- Wie sind Erkennungs- und Korrelationsergebnisse nach Schweregrad verteilt?
- Gibt es wiederkehrende verdächtige Muster im Laufe der Zeit?

Visualisierungen machen komplexe Sicherheitsdaten sofort verständlich.

---

## Verfügbare Diagrammtypen

### 1. Ereignishäufigkeit über Zeit
Zeigt, wie viele Ereignisse stündlich, täglich und wöchentlich auftreten.
Nützlich zum Erkennen von Spitzen, Aktivitätsschüben oder unerwarteten Ruhephasen, die darauf hindeuten könnten, dass etwas deaktiviert wurde.

### 2. Schweregradverteilung
Visuelle Aufschlüsselung der Ereignisse nach Schweregrad: Kritisch, Hoch, Warnung, Info.
Hilft Benutzern, das gesamte Risikoprofil auf einen Blick zu sehen.

### 3. Top-Ereignisquellen
Hebt hervor, welche Prozesse, Dateien oder Netzwerkendpunkte die meisten Ereignisse erzeugen:
- Aktivste Prozesse
- Am häufigsten zugegriffene Dateien
- Häufigste Netzwerkverbindungen

### 4. Erkennungs- & Korrelationstrend
Verfolgt die Entwicklung von Regelübereinstimmungen über die Zeit:
- Erkennungsergebnisse
- Korrelationsergebnisse
- Ketten-Ergebnisse

Hilft Benutzern, Eskalationsmuster zu erkennen, bevor eine vollständige Kompromittierung eintritt.

### 5. KI/ML-Anomalie-Score-Trend
Visualisiert die Ausgabe des lokalen Isolation-Forest-Engines über die Zeit:
- Entwicklung des Anomalie-Scores
- Schweregradklassifizierungen: Kritisch / Hoch / Mittel / Niedrig
- Spike-Ereignisse gegenüber der Verhaltensbasislinie

---

## Lokale Analyse-Engine

Alle Diagramme werden von der lokalen Analyse-Engine angetrieben:
- Kein Cloud
- Keine externen APIs
- Alle Berechnungen verbleiben auf dem Gerät

Diagramme werden direkt aus der verschlüsselten lokalen Datenbank und der KI/ML-Engine-Ausgabe generiert.

---

## Datenschutz & Offline-Betrieb

Nichts wird jemals an externe Dienste gesendet.
Analysen werden lokal aus verschlüsselten Ereignissen berechnet und gerendert, vollständig offline.

---

## Zusammenfassung

Diagramme & Analysen bieten eine visuelle, datenschutzfreundliche Möglichkeit, Systemaktivitäten zu verstehen, Erkennungstrends zu verfolgen, KI/ML-Ergebnisse zu überwachen und sofortige Einblicke in die Sicherheitslage des Geräts zu gewinnen.
