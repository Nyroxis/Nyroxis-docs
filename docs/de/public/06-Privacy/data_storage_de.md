# Sichere Datenspeicherung

Nyroxis speichert nur die Mindestmenge an Daten, die zur Bereitstellung von Sicherheitseinblicken erforderlich ist — und alle gespeicherten Daten sind vollständig verschlüsselt, lokal und manipulationsgeschützt.
Dies gewährleistet die Privatsphäre von Einzelpersonen, Familien und Fachleuten, die sich auf Nyroxis für echten Schutz ohne Offenlegung verlassen.

---

## Was Nyroxis speichert

Nyroxis bewahrt **nur sicherheitsrelevante Informationen**:

### 1. Ereignisprotokolle
Verschlüsselte Einträge für:
- Prozessaktivität
- Netzwerkverbindungen
- Datei- und Registrierungsänderungen
- Berechtigungsaktionen
- System- und Windows-Ereignisprotokolleinträge

### 2. Erkennungs- und Korrelationsergebnisse
Ergebnisse der Nyroxis Intelligence-Regelauswertung:
- Erkennungsergebnisse (27 Regeln)
- Korrelationsergebnisse (12 Regeln)
- Kettenergebnisse (2 Regeln)

### 3. KI/ML-Analyseergebnisse
Ausgabe des lokalen Isolation-Forest- und Statistikmotors:
- Anomalie-Scores und Schweregradklassifizierungen
- Aufschlüsselungen der beitragenden Merkmale
- Verhaltensbasislinien-Daten

### 4. Metadaten für die Analyse
Leichtgewichtige Metadaten, die benötigt werden für:
- Regelabgleich und Korrelation
- Aufbau der KI-Verhaltensbasislinie
- Zeitachsenrekonstruktion

---

## Was Nyroxis NICHT speichert

Nyroxis vermeidet bewusst das Sammeln oder Speichern persönlicher oder sensibler Inhalte.

Es speichert **NICHT**:
- Persönliche Dokumente oder Projektdateien
- Bilder oder Videos
- Browserverlauf
- Standortdaten
- Passwörter oder Anmeldedaten
- Dateiinhalte
- Benutzernachrichten oder E-Mails
- Daten, die nicht mit Sicherheitsereignissen zusammenhängen

Nur sicherheitsorientierte technische Daten werden aufbewahrt.

---

## Verschlüsselungsmodell

Alle gespeicherten Daten sind:
- Zum Zeitpunkt der Erfassung verschlüsselt (AES-256)
- Nur in verschlüsselter Form gespeichert — niemals im Klartext geschrieben
- Nur im Speicher während Lesevorgängen entschlüsselt
- Durch hashverkettete Integritätsstrukturen geschützt

Verschlüsselungsschlüssel sind:
- Lokal auf dem Gerät
- Aus Hardware-Identifikatoren (HWID) abgeleitet
- Niemals in der Anwendung eingebettet
- Niemals an Server übertragen

---

## Manipulationsgeschützte Strukturen

Nyroxis verwendet hash-verkettete Ereignisblöcke, wobei jeder Block enthält:
- Verschlüsselte Nutzlast
- Integritäts-Hash
- Sequenziellen Index
- Link zum vorherigen Block

Dies macht Manipulationen sofort erkennbar:
- Löschung, Änderung, Injektion oder Neuanordnung unterbricht die Kette
- Jede Abweichung wird als Sicherheitsereignis markiert

---

## Datenspeicherung

Benutzer haben die volle Kontrolle über ihre Daten:
- Protokolle jederzeit zurücksetzen
- KI-Verhaltensbasislinie löschen
- Aufbewahrungsdauer über die Einstellungsansicht verwalten
- Verschlüsselte Backups aus dem Backup-Bereich exportieren

---

## Vollständig lokale Speicherung

Die gesamte Speicherung ist:
- Nur lokal auf dem Gerät des Benutzers
- Vollständig offline
- AES-256 verschlüsselt
- Kein Cloud-Upload — jemals

Ihre Sicherheitsdaten bleiben auf Ihrem Gerät — immer.

---

## Zusammenfassung

Nyroxis speichert nur verschlüsselte, minimale, sicherheitsorientierte Informationen — niemals persönliche Inhalte — und gewährleistet echten Datenschutz und forensischen Schutz für jeden Benutzer.
