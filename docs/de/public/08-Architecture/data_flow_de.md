# Datenfluss — Übergeordnete Übersicht

Dieser Abschnitt erklärt, wie Daten innerhalb von Nyroxis fließen — von der Ereigniserfassung über die KI-Analyse bis zur Dashboard-Anzeige — während sie an jedem Schritt vollständig verschlüsselt, offline und privat bleiben.

---

## 1. Ereigniserfassung (Nyroxis Agent)

Der Fluss beginnt mit Nyroxis Agent, der überwacht:
- Prozesse und Dienste
- Netzwerkverbindungen und Datenverkehrs-Metadaten
- Dateisystemoperationen und Registrierungsänderungen
- Berechtigungsaktionen
- Windows-Ereignisprotokolleinträge (Sicherheit, System, Anwendung)
- PowerShell- und Skriptausführungen

Jedes Ereignis wird **in Echtzeit** erfasst.

Unmittelbar nach der Erfassung:
- Das Ereignis wird normalisiert und mit Kontext angereichert
- Verschlüsselt mit dem lokalen, vom HWID des Geräts abgeleiteten Schlüssel (AES-256)
- Für die Speicherung vorbereitet

Kein Klartext berührt jemals die Festplatte.

---

## 2. Verschlüsselte Speicherung (Lokale Datenbank)

Nach der Verschlüsselung werden Ereignisse geschrieben in:
- Die sichere lokale SQLite-Datenbank
- Hash-verkettete Ereignisstrukturen
- Geschützte Schreibpfade

Jeder Eintrag enthält:
- Zeitstempel
- Verschlüsselte Nutzlast
- Integritäts-Hash
- Sequenziellen Index, verknüpft mit dem vorherigen Block
- Metadaten, die für die Regelauswertung und KI-Analyse erforderlich sind

Alle Daten verbleiben auf dem Gerät des Benutzers — niemals synchronisiert oder hochgeladen.

---

## 3. Regelauswertung (Nyroxis Intelligence)

Nyroxis Intelligence liest aus der verschlüsselten Datenbank und bewertet Ereignisse auf drei Ebenen:
- **27 Erkennungsregeln** — Mustererkennung einzelner Ereignisse
- **12 Korrelationsregeln** — Multi-Ereignis-Muster über Zeit und Quellen hinweg
- **2 Kettenregeln** — Erkennung mehrstufiger Angriffssequenzen

Wenn eine Regel ausgelöst wird:
- Wird sofort eine Warnung ausgelöst
- Der Befund wird in eine dedizierte Erkennungsdatenbank geschrieben
- Der Benutzer wird über das Dashboard benachrichtigt

---

## 4. Lokale KI/ML-Verarbeitung

Parallel dazu liest die KI/ML-Engine Ereignisse aus der Datenbank:
- Nur im Arbeitsspeicher entschlüsselt — niemals im Klartext zurückgeschrieben
- Verarbeitet durch den Isolation Forest-Algorithmus
- Ausgewertet durch Z-Score-, IQR- und Spitzenwert-Erkennungsmethoden

Ausgaben:
- Anomalie-Score (0,0–1,0)
- Schweregrad-Klassifizierung
- Beitragende Merkmale mit Z-Score-Werten
- Aktualisierung der Verhaltens-Baseline

Kein Teil der KI erfordert Cloud-Zugang oder externe Kommunikation.

---

## 5. Dashboard-Anzeige (Lokale Benutzeroberfläche)

Das Dashboard ruft ausschließlich ab:
- Im Arbeitsspeicher entschlüsselte Zusammenfassungen
- Erkennungs-, Korrelations- und Kettenbefunde
- KI/ML-Ergebnisse mit Aufschlüsselung der beitragenden Merkmale
- Diagramme und Trenddaten

Alle UI-Darstellungen erfolgen lokal ohne externe Kommunikation.

---

## 6. Benutzeraktionen

Benutzer können:
- Verschlüsselte Protokolle durchsuchen (während der Suche im Arbeitsspeicher entschlüsselt)
- Befunde im PDF- oder CSV-Format exportieren
- Daten jederzeit löschen oder zurücksetzen
- Sicherungsvorgänge über den Sicherungsbereich verwalten
- Einstellungen und Aufbewahrung über die Einstellungsansicht anpassen

Alle Aktionen bleiben lokal und privat.

---

## Datenschutz durch Architektur

Jeder Schritt stellt sicher:
- Keine Cloud-Nutzung
- Keine Telemetrie
- Kein Fernzugriff
- Keine Online-Abhängigkeiten

Nyroxis gewährleistet vollständige Privatsphäre durch Architektur — nicht nur durch Konfiguration.

---

## Zusammenfassung

```
Ereignis erfasst      →  sofort verschlüsselt
Sicher gespeichert    →  hash-verkettet, integritätsgeschützt
Regelauswertung       →  27 Erkennung + 12 Korrelation + 2 Kette
KI/ML-Analyse         →  Isolation Forest + statistische Engine
Lokal angezeigt       →  Dashboard, Forensik, Berichte
Keine Cloud           →  kein Upload, keine Exposition, niemals
```
