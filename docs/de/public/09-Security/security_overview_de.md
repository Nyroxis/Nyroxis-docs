# Sicherheitsübersicht

Nyroxis ist mit einer strikten Sicherheit-zuerst-Philosophie entwickelt: Alle Operationen sind lokal, verschlüsselt, manipulationssicher und darauf ausgelegt, den Benutzer zu schützen, ohne Daten an Dritte weiterzugeben.

Diese Übersicht fasst die wichtigsten Sicherheitsprinzipien und -mechanismen der Plattform zusammen.

---

## Grundlegende Sicherheitsprinzipien

### 1. Datenschutz durch Design
Nyroxis lädt keine Daten hoch, synchronisiert oder überträgt sie an Server.
Alle Sicherheitslogik, Überwachung, Erkennung und KI-Analyse laufen vollständig auf dem Gerät.

### 2. Verschlüsselung Überall
Jedes erfasste Ereignis wird:
- Sofort bei der Erfassung verschlüsselt (AES-256)
- Nur in verschlüsselter Form gespeichert — niemals im Klartext
- Ausschließlich im Arbeitsspeicher während der Verarbeitung entschlüsselt
- Mit Integritäts-Hashes geschützt

Auf der Festplatte existieren niemals Klartextprotokolle.

### 3. Null Cloud-Abhängigkeit
Nyroxis stützt sich nicht auf:
- Cloud-Speicher oder -Verarbeitung
- Externe APIs
- Remote-Server
- Telemetrie-Pipelines
- Online-Authentifizierung

Benutzer behalten vollständige Autonomie und null externe Exposition für den Offline-Kern. Die einzige optionale Ausnahme, auf Aktivierung, ist die Cloud-Funktion **AI Copilot** (standardmäßig deaktiviert) — siehe die Seite *AI Copilot*.

### 4. Mehrschichtige Erkennung
Nyroxis Intelligence bietet:
- 27 Erkennungsregeln — bekannte Bedrohungsmuster
- 12 Korrelationsregeln — Multi-Ereignis-Muster über Zeit
- 2 Kettenregeln — mehrstufige Angriffssequenzen
- Erweiterbar durch Sicherheitsexperten ohne Änderung der Kernkomponenten

### 5. Lokale KI/ML
Die KI/ML-Engine verarbeitet Daten lokal:
- Isolation Forest Anomalieerkennung
- Z-Score-statistische Klassifizierung
- Identifikation beitragender Merkmale

Kein Cloud-Training, keine Cloud-Inferenz, keine Datenweitergabe.

---

## Wichtige Sicherheitsmechanismen

### 1. Sichere Ereigniserfassung
Nyroxis Agent erfasst:
- Prozesse und Dienste
- Dateisystem- und Registrierungsänderungen
- Netzwerkverbindungen
- Berechtigungsaktionen
- Windows-Ereignisprotokolleinträge

Alle Ereignisse werden sofort bei der Erfassung verschlüsselt.

### 2. Manipulationssichere Speicherung
Die lokale SQLite-Datenbank umfasst:
- AES-256-Verschlüsselung
- Hash-verkettete Ereignisblöcke
- Geschützte Schreibpfade
- Integritätsprüfung bei jedem Lesevorgang

Angreifer können Protokolle nicht unbemerkt ändern, löschen oder injizieren.

### 3. Plattformresilienz
Nyroxis System Guardian:
- Überwacht Agent und Intelligence kontinuierlich
- Erkennt unerwartete Dienststopps sofort
- Protokolliert Abschaltversuche als Sicherheitsereignisse
- Verwaltet Sicherungen und Offline-Lizenzvalidierung

Die Plattform kann nicht still deaktiviert werden.

### 4. HWID-Basierte Lizenzierung
Lizenzvalidierung:
- An Gerätehardware gebunden (HWID-abgeleiteter Schlüssel)
- Offline mit AES-GCM und HMAC validiert
- Durch System Guardian durchgesetzt — Dienste stoppen automatisch, wenn die Lizenz ungültig ist

### 5. Dashboard-Sicherheit
Das Dashboard:
- Liest entschlüsselte Zusammenfassungen nur im RAM
- Schreibt niemals entschlüsselte Daten zurück auf die Festplatte
- Verbindet sich nicht mit externen Quellen
- Bietet schreibgeschützten Zugriff auf den Protokollspeicher

---

## Zusammenfassung der Sicherheitsschichten

Nyroxis integriert mehrere Verteidigungsschichten:
- AES-256-Verschlüsselung bei der Erfassung
- Hash-verketteter, manipulationssicherer Speicher
- Plattformwächter für Dienst-Resilienz
- Ausschließlich lokale KI/ML-Engine
- Offline-Lizenzvalidierung
- Null Cloud-Exposition
- Datenschutzorientierte Architektur durchgehend

---

## Zusammenfassung

Nyroxis bietet ein modernes, privates, offline Sicherheitsmodell, das Benutzer schützt, ohne sie zu verfolgen — kombiniert Transparenz, Kontrolle, forensische Integrität und starkes defensives Design auf jeder Ebene.
