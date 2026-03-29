# KI-Szenarien

KI-Szenarien repräsentieren übergeordnete Sicherheitssituationen, die die lokale KI/ML-Engine anhand von Verhaltensmustern, Ereignissequenzen und Anomaliekorrelationen identifiziert.
Sie helfen Benutzern, den *Kontext* zu verstehen — nicht nur einzelne Ereignisse oder isolierte Anomalien.

---

## Zweck der KI-Szenarien

Während Erkennungen spezifische Anomalien hervorheben und Regelübereinstimmungen einzelne Bedrohungen markieren, erklären **Szenarien** *warum diese Signale wichtig sind*, indem sie verwandte Ergebnisse in bedeutungsvolle, reale Angriffskontexte gruppieren.

Szenarien geben Benutzern Klarheit über:
- Die Art der beobachteten Bedrohung
- Wie einzelne Ereignisse und Anomalien zusammenhängen
- Was das kombinierte Muster in realen Begriffen bedeutet
- Was die empfohlenen nächsten Schritte sind

Dies macht ausgeklügelte Bedrohungsmuster auch für nicht-technische Benutzer verständlich.

---

## Arten von Szenarien

### 1. Verdächtige Prozesskette
Erkannt, wenn eine Prozessaktivitätssequenz bekanntem bösartigem Verhalten ähnelt:
- Unbekannter Prozess startet eine Script-Engine
- Script-Engine löst Dateiänderung gefolgt von einem Netzwerkaufruf aus
- Prozess erzeugt mehrere Kindprozesse in rascher Folge

Nützlich zum Erkennen von Malware im Frühstadium, Dropper-Verhalten oder Living-off-the-Land-Techniken.

---

### 2. Nicht autorisierte Netzwerkaktivität
Ausgelöst, wenn die Engine folgendes beobachtet:
- Ausgehende Verbindungen zu unbekannten oder seltenen Netzwerkendpunkten
- Wiederholte fehlgeschlagene Verbindungen gefolgt von einem erfolgreichen ausgehenden Anruf
- Hochvolumige Netzwerkaktivität weit außerhalb normaler Basislinienmuster

Kann auf Scanning, Beaconing oder Datenexfiltrations-Versuche hinweisen.

---

### 3. Abnormale Dateiaktivität
Tritt auf, wenn:
- Sensible Dateien oder Verzeichnisse unerwartet zugegriffen werden
- Eine große Anzahl von Dateien in einem kurzen Zeitfenster geändert wird
- Dateiänderungen mit verdächtigem Prozess- oder Netzwerkverhalten korrelieren

Nützlich zum Erkennen von Ransomware-ähnlichem Verhalten, Daten-Staging oder Manipulation.

---

### 4. Berechtigungserhöhungsversuch
Ausgelöst durch:
- Wiederholte Berechtigungserhöhungsversuche
- Seltene oder ungewöhnliche Systemaufrufe
- Verhalten, das mit dem normalen Benutzeraktivitätsmuster des Geräts nicht vereinbar ist

Hilft bei der Identifizierung lokaler Ausnutzungsversuche oder Missbrauch von Anmeldeinformationen.

---

### 5. Persistenzindikator
Tritt auf, wenn ein Prozess versucht:
- Startorte oder geplante Aufgaben zu ändern
- Systemkonfiguration zu ändern, um einen Neustart zu überleben
- Dienste oder Treiber unerwartet zu installieren

Warnt vor langfristiger Kompromittierung und Etablierung eines Angreifer-Stützpunkts.

---

### 6. Langsames Einbruchsmuster
Die Engine identifiziert langfristige, rauscharme Anomalien wie:
- Allmähliche Eskalation ungewöhnlicher Aktivitäten über Stunden oder Tage
- Seltene periodische Aktivität, die sich planmäßig wiederholt
- Mehrstufige Verhaltenssequenzen, die über erweiterte Zeitfenster verteilt sind

Erkennt heimliche Angreifer, die absichtlich vermeiden, schwellenwertbasierte Regeln auszulösen.

---

## Details des Szenarioberichts

Jedes Szenario enthält:
- Beschreibung der Situation in einfacher Sprache
- Betroffene Ereignisse und Ergebnisse
- Sequenzerklärung, die zeigt, wie Signale verbunden sind
- Schweregrad
- Reale Interpretation
- Empfohlene nächste Schritte

---

## Vollständig lokal

Die gesamte Szenariologik:
- Läuft offline auf dem Gerät
- Verwendet verschlüsselte lokale Ereignisdaten
- Kontaktiert niemals Cloud-Dienste
- Wahrt die vollständige Privatsphäre des Benutzers

---

## Zusammenfassung

KI-Szenarien helfen Benutzern, das Gesamtbild zu sehen — sie geben einzelnen Anomalien und Regelübereinstimmungen Bedeutung, indem sie diese realen Angriffskontexten zuordnen, und ermöglichen die frühzeitige Erkennung ausgeklügelter Bedrohungen vollständig offline und privat.
