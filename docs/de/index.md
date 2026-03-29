# Was ist Nyroxis?

Nyroxis ist eine leichtgewichtige, KI-gestützte Cybersicherheitsplattform zum Schutz **persönlicher und nicht verwalteter Endpoints** — der Geräte, die traditionelle Enterprise-Sicherheitstools oft ignorieren.

Sie bietet kontinuierliche, datenschutzzentrierte Überwachung und bringt SOC-grade Erkennung auf persönliche Geräte, ohne Cloud-Konnektivität, technisches Fachwissen oder Enterprise-Infrastruktur zu erfordern.

## Warum Nyroxis Existiert

Moderne Cyberangriffe zielen nicht mehr nur auf Unternehmen ab. Führungskräfte, Anwälte, Richter, Ärzte, Journalisten und sogar Familien werden auf **ihren persönlichen Geräten** angegriffen — wo es kein SOC, kein SIEM und kein Sicherheitsteam gibt, das über sie wacht.

Nyroxis füllt diese Lücke, indem es **Sichtbarkeit und Erkennung auf Enterprise-Niveau** auf die persönliche Ebene bringt — still, lokal und ohne Kompromisse.

## Für Wen ist Nyroxis?

- Führungskräfte und hochrangige Persönlichkeiten
- Rechtsanwälte, Richter, Ärzte und Fachleute, die mit sensiblen Daten umgehen
- Familien, die digitale Sicherheitstransparenz suchen
- Cybersicherheitsingenieure und SOC-Analysten zu Hause
- Vielreisende und Remote-Mitarbeiter
- Freie Mitarbeiter und Berater

## Wie Nyroxis Funktioniert (Überblick)

Nyroxis ist um vier Kernkomponenten aufgebaut, die zusammenarbeiten:

### Nyroxis Agent
- Kontinuierliche stille Überwachung aus mehreren Systemkanälen
- Normalisiert, verschlüsselt und speichert alles lokal
- Arbeitet vollständig offline — manipulationssicheres Design
- ~57 MB RAM, 0,1 % CPU

### Nyroxis Intelligence
- Dreischichtige Erkennungs-Engine
- 27 Erkennungsregeln, 12 Korrelationsregeln, 2 Kettenregeln (kontinuierlich wachsend)
- Erweiterbar durch Sicherheitsexperten — benutzerdefinierte Regeln im JSON-Format
- ~87 MB RAM, 1,8 % CPU

### Nyroxis System Guardian
- Stiller Systemtray-Wächter
- Überwacht alle Dienste alle 3 Sekunden
- Verwaltet Sicherungen, Offline-Lizenzvalidierung und Update-Prüfung
- Stoppt Dienste automatisch, wenn die Lizenz abläuft
- ~6,5 MB RAM, 0,1 % CPU

### Nyroxis Dashboard
- Echtzeit-Sichtbarkeit über Ereignisse, Erkennungen, Korrelationen und Ketten
- Forensische Suche, KI/ML-Analyse, PDF/CSV-Berichte
- Englisch, Französisch und Deutsch

```
[ Gerät ]
   |--> Nyroxis Agent          (Erfassung & Verschlüsselung)
   |--> Nyroxis Intelligence   (Erkennung & Korrelation)
   |--> Nyroxis System Guardian (Überwachung & Schutz)
   |--> Nyroxis Dashboard      (Sichtbarkeit & Analyse)
```

## Hauptvorteile

- Alle Daten verbleiben auf Ihrem Gerät — immer
- Forensisch geeigneter verschlüsselter Speicher (AES-256)
- 27 + 12 + 2 Erkennungsregelschichten, erweiterbar durch Sicherheitsexperten
- Lokale KI/ML-Anomalieerkennung — keine Cloud, keine Telemetrie
- HWID-basierte Offline-Lizenzierung
- Leichtgewichtig und still — für Angreifer unsichtbar

## Dokumentationsübersicht

Diese Dokumentation umfasst:
- Architektur & Komponenten
- Agent, Intelligence & System Guardian
- Dashboard & KI/ML-Engine
- Sicherheit & Datenschutz
- Anwendungsfälle
- Roadmap
- Lizenzierung
- FAQ & Glossar
