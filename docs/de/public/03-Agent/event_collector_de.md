# Ereignis-Collector

Der Ereignis-Collector ist das Teilsystem innerhalb des Nyroxis Agents, das für die Erfassung aller sicherheitsrelevanten Aktivitäten auf dem Gerät verantwortlich ist.
Er ist darauf ausgelegt, leichtgewichtig, privat und vollständig offline zu sein, während er gleichzeitig Transparenz auf Unternehmensebene über das Endpunktverhalten bietet.

---

## Zweck des Ereignis-Collectors

Das Hauptziel des Ereignis-Collectors ist es, verwertbare, strukturierte Informationen zu sammeln, die Benutzern helfen zu verstehen:
- Was auf ihrem Gerät passiert
- Wann Ereignisse auftreten
- Ob die Aktivität normal oder verdächtig ist

Alles ohne externe Datenoffenlegung.

---

## Was der Ereignis-Collector überwacht

Nyroxis konzentriert sich auf die sicherheitskritischsten Ereigniskategorien:

### 1. Prozessereignisse
- Prozesserstellung und -beendigung
- Eltern-/Kind-Beziehungen
- Befehlszeilenparameter (soweit verfügbar)
- Ausführungspfade und Binär-Metadaten

### 2. Netzwerkereignisse
- Ausgehende und eingehende Verbindungen
- Ziel-IPs und -Ports
- Protokolltyp
- Wiederholte Verbindungsversuche

### 3. Dateisystemaktivität
- Dateierstellung, -änderung und -löschung
- Zugriff auf sensible Verzeichnisse
- Registrierungsänderungen

### 4. Berechtigungs- und Sicherheitsereignisse
- Erhöhungsversuche
- Sensible Systemaufrufe
- Registrierungs- und Konfigurationsänderungen
- Zugriff auf geschützte Ressourcen

### 5. System- und Dienstereignisse
- Dienststarten/-stoppen
- Treiberladen
- Windows-Ereignisprotokolleinträge (Sicherheit, System, Anwendung)
- Indikatoren für Persistenzmechanismen
- PowerShell- und Skriptausführung

Der genaue Umfang ist für Windows (v1.0) optimiert. macOS- und Linux-Unterstützung befindet sich in der Entwicklung.

---

## Normalisierungs-Pipeline

Nach der Erfassung wird jedes Ereignis:
1. Geparst und in ein normalisiertes Format strukturiert
2. Mit kontextuellen Metadaten angereichert (Zeitstempel, Quelle, Schweregradhinweis)
3. Für Verschlüsselung und Speicherung vorbereitet
4. Für die Nutzung durch Nyroxis Intelligence bereitgestellt

Diese Normalisierung gewährleistet eine konsistente Regelauswertung für alle Ereignistypen.

---

## Sichere Erfassung und sofortige Verschlüsselung

Jedes vom Collector erfasste Ereignis wird:
- Sofort mit AES-256 verschlüsselt
- In manipulationsresistenter, hash-verketteter Form gespeichert
- Mit Zeitstempeln und Metadaten indiziert
- Niemals im Klartext auf die Festplatte geschrieben

---

## Leichtgewichtige Implementierung

Der Ereignis-Collector ist optimiert für:
- Minimalen CPU-Overhead (~0,1 %)
- Geringen Speicherverbrauch (~57 MB RAM gesamt für den Agent)
- Keinerlei Auswirkungen auf alltägliche Aufgaben
- Stabilen Langzeitbetrieb

---

## Offline-First durch Design

Der Ereignis-Collector arbeitet mit **null Cloud-Interaktion**.
Alle Überwachung, Normalisierung, Verschlüsselung und Speicherung erfolgen lokal — die Privatsphäre des Benutzers wird auch in sensiblen oder air-gapped Umgebungen gewahrt.

---

## Zusammenfassung

Der Ereignis-Collector ist das Fundament der Sichtbarkeitsschicht von Nyroxis, erfasst jede wichtige sicherheitsbezogene Aktivität und bleibt dabei leichtgewichtig, verschlüsselt und vollständig offline.
