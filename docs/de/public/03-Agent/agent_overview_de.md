# Nyroxis Agent — Übersicht

Der Nyroxis Agent ist die zentrale Überwachungs- und Erfassungskomponente der Plattform.
Er läuft lokal auf dem Gerät des Benutzers, erfasst und normalisiert dabei still Sicherheitsereignisse, verschlüsselt sie und speichert sie in einer manipulationsresistenten lokalen Datenbank — alles mit minimalem Ressourcenverbrauch.

---

## Was der Agent tut

Der Agent beobachtet kontinuierlich die Systemaktivität und erstellt eine strukturierte, verschlüsselte Sicherheitszeitlinie.

Er überwacht:
- Prozesserstellung und -beendigung
- Netzwerkverbindungen und Datenverkehrsmetadaten
- Dateiänderungen und Registrierungsänderungen
- Berechtigungsaktionen und Zugriffsversuche auf Anmeldeinformationen
- System- und Sicherheitsereignisse (Windows-Ereignisprotokolle)
- PowerShell- und Skriptausführung

Alle Ereignisse werden **privat und lokal** erfasst — nichts wird extern übertragen.

---

## Erfassungs-Pipeline

1. **Erfassung** — Ereignisse werden gleichzeitig aus mehreren Systemkanälen aufgenommen
2. **Normalisierung** — Rohdaten werden angereichert und für die Erkennungs-Engine standardisiert
3. **Verschlüsselung** — Die Nutzlast wird vor jedem Schreibvorgang mit AES-256 verschlüsselt
4. **Speicherung** — Verschlüsselte Ereignisse werden in die lokale SQLite-Datenbank geschrieben
5. **Einspeisung** — Daten fließen zur Nyroxis Intelligence für die Regelauswertung in Echtzeit

---

## Datenschutzorientierter Betrieb

Der Agent lädt niemals Protokolle hoch oder sendet Ereignisdaten an externe Server.
Alles verbleibt auf dem Gerät und ist:
- Im Moment der Erfassung verschlüsselt
- Durch hash-verkettete Ereignisblöcke gegen Manipulation geschützt
- In einer sicheren lokalen SQLite-Datenbank gespeichert
- Jederzeit unter der alleinigen Kontrolle des Benutzers

---

## Leichtgewichtig durch Design

Der Agent ist für minimalen Ressourcenverbrauch optimiert:
- ~57 MB RAM
- ~0,1 % CPU
- Stiller Hintergrundbetrieb als Windows-Dienst
- Geeignet für den Dauerbetrieb auf persönlichen Laptops ohne Beeinträchtigung der täglichen Produktivität

---

## Widerstandsfähig und manipulationsbewusst

Der Agent beinhaltet Schutzmechanismen, um sicherzustellen:
- Erfasste Ereignisdaten können nicht unbemerkt verändert oder gelöscht werden
- Angreifer können ihre Aktivitäten nicht still löschen
- Hash-verkettete Ereignisblöcke decken jeden Lösch-, Änderungs- oder Injektionsversuch auf

Nyroxis System Guardian überwacht den Betriebsstatus des Agents kontinuierlich und ergreift Korrekturmaßnahmen, wenn der Dienst unerwartet stoppt.

---

## Funktioniert vollständig offline

Keine Internetverbindung erforderlich für:
- Überwachung
- Normalisierung und Verschlüsselung
- Datenspeicherung
- Einspeisung in Nyroxis Intelligence

Nyroxis ist in isolierten oder air-gapped Umgebungen vollständig funktionsfähig.

---

## Zusammenfassung

Der Nyroxis Agent bietet kontinuierliche, verschlüsselte Offline-Überwachung — gibt Benutzern Transparenz auf Unternehmensebene, ohne ihre Daten Dritten preiszugeben, und liefert forensisch-geeignete Beweise für rechtliche und behördliche Verfahren.
