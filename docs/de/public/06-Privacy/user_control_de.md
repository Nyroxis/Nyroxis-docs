# Benutzerkontrolle & Transparenz

Nyroxis ist darauf ausgelegt, Benutzern die vollständige Kontrolle über ihre Sicherheitsdaten, das Systemverhalten und die Datenschutzeinstellungen zu geben.
Keine versteckten Prozesse, keine Hintergrund-Uploads, keine Cloud-Verbindungen — alles ist transparent und lokal verwaltet.

---

## Grundprinzipien der Benutzerkontrolle

Nyroxis stellt sicher, dass Benutzer:
- Sehen können, was überwacht wird
- Kontrollieren können, was gespeichert wird und wie lange
- Daten jederzeit zurücksetzen oder löschen können
- Überprüfen können, dass die Plattform offline arbeitet
- Verstehen können, wie KI/ML-Entscheidungen getroffen werden

Der Benutzer behält immer die Kontrolle.

---

## 1. Keine stille Datenerfassung

Nyroxis erfasst **nur**, was für die Sicherheitsanalyse notwendig ist:
- Protokolle von Prozessen und Diensten
- Netzwerkverbindungsereignisse
- Dateisystem- und Registrierungsänderungen
- Berechtigungsaktionen
- Windows-Ereignisprotokolleinträge

Keine persönlichen Dateien, Fotos, Nachrichten, Browserdaten oder Anmeldedaten werden jemals erfasst.
Alles Erfasste ist in dieser Dokumentation dokumentiert.

---

## 2. Vollständige Datenzurücksetzung

Benutzer können jederzeit vom Dashboard aus zurücksetzen:
- Ereignisprotokolle
- Erkennungs- und Korrelationsergebnisse
- KI/ML-Verhaltensbasislinie
- Alle Metadaten

Eine vollständige Zurücksetzung stellt Nyroxis in einen sauberen Zustand ohne Überreste wieder her.

---

## 3. Ausschließlich lokale Speicherung

Alle Daten sind:
- Lokal in der verschlüsselten SQLite-Datenbank gespeichert
- Vollständig verschlüsselt (AES-256)
- Niemals extern übertragen
- Unter der alleinigen Kontrolle des Benutzers

Benutzer sind nicht auf Cloud-Konten, Online-Authentifizierung oder Remote-Speicherung angewiesen.

---

## 4. Transparente KI/ML

Der KI/ML-Motor bietet:
- Klaren Anomalie-Score mit Schweregradklassifizierung
- Beitragende Merkmale — die spezifischen Verhaltensdimensionen, die die Erkennung ausgelöst haben, mit Z-Score-Werten
- Szenariobasierte Begründungszusammenfassungen

KI-Entscheidungen sind darauf ausgelegt, verständlich und erklärbar zu sein — keine Black Box.

---

## 5. Anpassungsoptionen

Benutzer können über die Einstellungsansicht anpassen:
- Datenbankdateipfad und Speicherort
- Dashboard-Aktualisierungsintervall
- Standard-Rückblickfenster für Ereignisabfragen
- Standard-Stichprobenlimit
- Schnittstellensprache: Englisch, Französisch, Deutsch
- Theme-Konfiguration

Alle Einstellungen sind lokal.

---

## 6. Backup-Kontrolle

Aus dem Backup-Bereich können Benutzer:
- Automatische Backups planen
- On-Demand-Backups ausführen
- Backup-Verlauf mit Zeitstempeln und Dateigrößen überprüfen
- Alle Backups sind verschlüsselt und lokal gespeichert

---

## 7. Überprüfung des Offline-Betriebs

Das Dashboard und Nyroxis System Guardian zeigen Indikatoren, die Benutzern ermöglichen zu überprüfen:
- Keine ausgehenden Netzwerkverbindungen von Nyroxis-Prozessen
- Keine Hintergrundtelemetrie
- Keine Cloud-Abhängigkeit
- Agent- und Intelligence-Dienststatus in Echtzeit

Vertrauen ist messbar — nicht angenommen.

---

## Zusammenfassung

Nyroxis gibt Benutzern die vollständige Kontrolle über ihre Daten, vollständige Transparenz seiner Operationen und die Möglichkeit, alles lokal zu verwalten, zurückzusetzen, zu sichern oder zu überprüfen — ohne Cloud-Abhängigkeit oder versteckte Prozesse.
