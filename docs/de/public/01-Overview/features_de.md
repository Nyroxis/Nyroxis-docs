# Hauptfunktionen

Nyroxis bringt Sichtbarkeit und Erkennung auf Unternehmensebene auf persönliche und professionelle Geräte – dabei bleibt es leichtgewichtig, datenschutzfreundlich und vollständig offline-fähig.

---

## Mehrschichtige Erkennungs-Engine

Nyroxis Intelligence arbeitet über drei sequenzielle Erkennungsschichten:

### Schicht 1 — Erkennung (27 Regeln)
Identifiziert bekannte Bedrohungsmuster in einzelnen Ereignissen:
- Verdächtige Prozessausführung
- Nicht autorisierte Dienstinstallation
- Anomales Netzwerkverhalten
- Versuche zum Zugriff auf Anmeldedaten

### Schicht 2 — Korrelation (12 Regeln)
Verbindet verwandte Ereignisse über Zeit und Quellen hinweg, um Muster aufzudecken, die kein einzelnes Ereignis preisgeben würde:
- Fehlgeschlagene Anmeldung, gefolgt von einer erfolgreichen von einem anderen Standort
- Neuer Prozess, der unmittelbar nach dem Anschluss eines USB-Geräts gestartet wird

### Schicht 3 — Kette (2 Regeln)
Erkennt mehrstufige Angriffsequenzen — die koordinierten, fortschreitenden Einbrüche, die für Advanced Persistent Threats charakteristisch sind.

Die Regelbibliothek wächst kontinuierlich. Sicherheitsfachleute können eigene benutzerdefinierte Regeln direkt in die Engine schreiben und einsetzen, ohne das Kernsystem zu modifizieren.

---

## Lokale Ereignisüberwachung

Der Nyroxis Agent erfasst kontinuierlich sicherheitsrelevante Aktivitäten:
- Prozesserstellung und -beendigung
- Netzwerkverbindungen und Datenverkehrs-Metadaten
- Dateiänderungen und Registry-Änderungen
- Rechtebezogene Aktionen
- System- und Sicherheitsereignisse (Windows-Ereignisprotokolle)
- PowerShell- und Skriptausführung

Die gesamte Überwachung erfolgt **lokal**, ohne Daten an die Cloud zu senden.

---

## Verschlüsselter Speicher in forensischer Qualität

Alle erfassten Ereignisse sind:
- Im Ruhezustand verschlüsselt (AES-256)
- Durch hash-verkettete Ereignisblöcke gegen Manipulation geschützt
- Nur auf dem Gerät des Benutzers gespeichert
- Für rechtliche und regulatorische Verfahren geeignet

---

## Lokale KI/ML-Engine

Nyroxis enthält eine benutzerdefinierte Isolation-Forest-Implementierung, die in Rust entwickelt wurde — keine externe ML-Bibliothek erforderlich:
- 100 Isolationsbäume pro Analysezyklus
- 8 verhaltensbasierte Merkmale pro Fenster analysiert
- Z-Score-Statistikanalyse: Kritisch / Hoch / Mittel / Niedrig
- IQR-Ausreißererkennung, gleitende Durchschnitte, Spike-Erkennung
- Alle Berechnungen auf dem Gerät — niemals in der Cloud

---

## Plattformwächter (Nyroxis System Guardian)

Ein stiller Systemtray-Dienst, der:
- Alle Plattformdienste alle 3 Sekunden überwacht
- Geplante und bedarfsgesteuerte Datenbanksicherungen verwaltet
- Die HWID-basierte Lizenz vollständig offline validiert
- Automatisch auf Updates prüft
- Dienste automatisch stoppt, wenn die Lizenz abläuft

---

## Intuitives Dashboard

Das Dashboard bietet:
- Echtzeit-Ereigniszeitstrahl und Schweregradindikatoren
- Ansichten für Erkennungs-, Korrelations- und Kettenergebnisse
- Forensische Suche mit erweiterter Filterung
- KI/ML-Analyse mit Aufschlüsselung der beitragenden Merkmale
- Berichterstellung — PDF/CSV-Export
- Verwaltung von Datenbanksicherungen
- Verfügbar auf Englisch, Französisch und Deutsch

---

## Offline-First-Betrieb

Nyroxis funktioniert vollständig ohne:
- Cloud-Verbindung
- Internetabhängigkeit
- Externe Authentifizierung

Die Plattform ist für hochprivate Umgebungen konzipiert und funktioniert in Air-Gapped-Setups.

---

## Manipulationsresistente Architektur

Nyroxis schützt:
- Alle Plattformdienste über Nyroxis System Guardian
- Lokale Protokolle über hash-verkettete Ereignisblöcke
- Die Integrität der Ereignisdaten durch kontinuierliche Überprüfung

Angreifer können ihre Spuren nicht unbemerkt verwischen.
