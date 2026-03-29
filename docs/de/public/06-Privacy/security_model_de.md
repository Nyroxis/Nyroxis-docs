# Sicherheitsmodell

Das Nyroxis-Sicherheitsmodell stellt sicher, dass alle Überwachungs-, Erkennungs-, KI-Analyse- und Ereignisspeichervorgänge unter strengen Grundsätzen der Datenschutz-Priorität und Manipulationsresistenz operieren.
Dieses Modell ist für Einzelpersonen, Fachleute und Führungskräfte konzipiert, die vertrauenswürdige Sicherheit ohne Einbußen bei der Privatsphäre benötigen.

---

## Kernziele

Nyroxis schützt:
- Datenvertraulichkeit — kein unbefugter Zugriff auf Ereignisprotokolle
- Systemintegrität — manipulationsresistente Beweiskette
- Benutzerprivatsphäre — keine Cloud-Übertragung, kein Verhaltens-Profiling
- Plattformresilienz — kontinuierliche Überwachung, geschützt vor Störungen

Das Ergebnis: Unternehmensschutz auf einem persönlichen Gerät.

---

## 1. End-to-End lokale Verschlüsselung

Alle Ereignisdaten sind:
- Zum Zeitpunkt der Erfassung verschlüsselt (AES-256)
- Nur in verschlüsselter Form gespeichert — niemals im Klartext geschrieben
- Nur über sichere Lesepfade zugänglich
- Nur im Speicher während der Verarbeitung entschlüsselt

Verschlüsselungsschlüssel sind:
- Aus der Hardware des Geräts (HWID) abgeleitet
- Lokal auf dem Gerät
- Niemals in der Anwendung gespeichert
- Niemals extern übertragen

---

## 2. Manipulationsresistente Speicherung

Nyroxis verwendet hash-verkettete Ereignisblöcke:
- Jeder Block enthält einen Hash des vorherigen Blocks
- Die Integrität wird bei jedem Lesevorgang überprüft
- Jede Löschung, Änderung, Injektion oder Neuanordnung unterbricht die Kette und löst einen Alarm aus
- Geschützte Schreibpfade verhindern partielle oder beschädigte Schreibvorgänge

Angreifer können Protokolle nicht ändern oder ihre Spuren unentdeckt verwischen.

---

## 3. Plattformresilienz (Nyroxis System Guardian)

Nyroxis System Guardian überwacht den Betriebsstatus von Nyroxis Agent und Nyroxis Intelligence alle 3 Sekunden.

Wenn einer der Dienste gestoppt wird — durch einen Absturz, ein Systemereignis oder absichtliche Störung:
- Guardian erkennt die Störung sofort
- Korrekturmaßnahmen werden ergriffen
- Der Abschaltversuch wird als Sicherheitsereignis protokolliert

Die Plattform kann nicht still deaktiviert werden.

---

## 4. Lokaler KI/ML-Motor

Der KI/ML-Motor:
- Läuft vollständig offline
- Verarbeitet nur lokal verschlüsselte Ereignisdaten
- Generiert Anomalieerkennungen und statistische Ergebnisse lokal
- Sendet niemals Daten an Server
- Lädt niemals Verhaltensprofile oder Modell-Feedback hoch

Ihre Daten bleiben immer auf Ihrem Gerät.

---

## 5. Vollständiger Offline-Betrieb

Nyroxis benötigt nicht:
- Cloud-Verarbeitung oder -Speicherung
- Online-Authentifizierung
- Externe APIs
- Remote-Server jeglicher Art

Dies beseitigt ganze Klassen von Datenschutzrisiken — Cloud-Verstöße, Drittanbieter-Zugriff und netzwerkbasierte Angriffe auf die Sicherheitsplattform selbst.

---

## 6. Minimale Datenspeicherung

Nyroxis speichert nur:
- Verschlüsselte Sicherheitsereignisse
- Erkennungs- und Korrelationsergebnisse
- KI/ML-Analyseergebnisse
- Für Erkennung und Forensik benötigte Metadaten

Es speichert **nicht**:
- Persönliche Dokumente oder Dateien
- Browserverlauf
- Anmeldedaten oder Passwörter
- Standortdaten
- Inhalte, die nicht mit Sicherheitsereignissen zusammenhängen

---

## 7. Transparente Logik

Das Sicherheitsmodell ist absichtlich einfach und überprüfbar:
- Lokale Erfassung → lokale Verschlüsselung → lokale Erkennung → lokale KI → lokale Alarme
- Keine stillen Uploads, keine Telemetrie, keine versteckten Netzwerkverbindungen

Benutzer können das Verhalten der Plattform über das Dashboard und die System-Netzwerküberwachung verifizieren.

---

## Zusammenfassung

Nyroxis bietet ein starkes, datenschutzorientiertes und forensisch solides Sicherheitsmodell:
- AES-256 verschlüsselte Ereignisspeicherung
- Hash-verketteter Manipulationsschutz
- Ausschließlich lokale KI/ML
- Plattformwächter für Resilienz
- Keine Cloud-Risiken, keine Telemetrie, keine externen Abhängigkeiten
