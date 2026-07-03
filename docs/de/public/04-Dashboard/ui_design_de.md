# Dashboard-UI-Design

Das Nyroxis-Dashboard ist darauf ausgelegt, Benutzern — sowohl nicht-technischen als auch professionellen — eine klare, intuitive und handlungsorientierte Ansicht des Sicherheitszustands ihres Geräts zu geben.
Sein Design folgt Prinzipien der Klarheit, des Minimalismus, des Datenschutzes und der Echtzeit-Bewusstsein.

---

## Designphilosophie

### Klarheit vor Komplexität
Sicherheitsdaten sollten den Benutzer niemals überfordern.
Das Dashboard wandelt rohe Protokolle in lesbare Einblicke um — mit übersichtlichen Layouts, farbcodierten Schweregradanzeigen und einfachen Erklärungen.

### Datenschutzorientierte Visualisierung
Alle im Dashboard angezeigten Daten:
- Stammen aus dem lokalen verschlüsselten Speicher
- Verlassen das Gerät nie
- Werden vollständig offline verarbeitet

### Einheitliche UX für alle Personas
Die Oberfläche bedient nicht-technische Führungskräfte, Juristen, Familien und Cybersicherheitsanalysten gleichermaßen — jeder erhält dasselbe klare, strukturierte Layout.

---

## Kern-Dashboard-Bereiche

### 1. Hauptübersicht
Der Einstiegspunkt — bietet einen Schnellüberblick über die aktuelle Sicherheitslage:
- Gesamtzahl der in den letzten 24 Stunden gesammelten Ereignisse
- Aktive Alarme nach Schweregrad: Kritisch, Hoch, Warnung, Info
- Ereigniszeitachse in Echtzeit
- Diagramm zur Schweregradverteilung
- Systemstatus: Agent-Zustand, Datenbankgröße, Regel-Engine-Gesundheit, Lizenzgültigkeit, Sicherungsstatus

### 2. Ereignisse
Der forensische Kern des Dashboards:
- Vollständiger Zugriff auf die rohe Ereignisdatenbank
- Suche über alle Ereignisfelder: Quelle, Kanal, Schweregrad, Inhalt
- Filterung nach Zeitbereich, Schweregrad, Quelle und Kanal
- Forensische Inspektion einzelner Ereignisse mit vollständigem Nutzlastdetail
- CSV-Export für rechtliche Dokumentation

### 3. Erkennung
Alle Ergebnisse aus der 27-Regel-Erkennungsschicht von Nyroxis Intelligence:
- Regel, die den Alarm ausgelöst hat
- Spezifische Ereignisse, die übereinstimmten
- Schweregradklassifizierung und Zeitstempel
- Direkter Link zu den zugrundeliegenden rohen Ereignissen für forensische Analyse

### 4. Korrelation
Ergebnisse der 12-Regel-Korrelations-Engine:
- Muster, die aus Beziehungen zwischen Ereignissen über die Zeit entstehen
- Zeitfenster und Quellenzuordnung
- Wo isolierte Signale zu verwertbaren Erkenntnissen werden

### 5. Kette
Ergebnisse der 2-Regel-Kettenerkennungsschicht:
- Erkennung mehrstufiger Angriffssequenzen
- Alarme mit höchster Priorität im System
- Vollständige Rekonstruktion der erkannten Angriffssequenz

### 6. Berichte
Strukturierte, exportierbare Dokumentation:
- Konfigurierbare Zeitfenster
- PDF- und CSV-Export
- Geeignet für interne Überprüfung oder Sicherheitsuntersuchung

### 7. KI / ML-Analyse
Zugang zur lokalen Machine-Learning-Engine:
- Anomalieerkennungsergebnisse mit Aufschlüsselung der beitragenden Merkmale
- Z-Score-Klassifizierungen: Kritisch / Hoch / Mittel / Niedrig
- Verfolgung der Entwicklung der Verhaltensbasislinie
- Identifikation statistischer Ausreißer und Spitzen
- Alle Analysen werden lokal durchgeführt — keine Daten verlassen das Gerät

### 8. Einstellungen
Vollständige Plattformkonfiguration:
- Datenbankdateipfad und Speicherverwaltung
- Dashboard-Aktualisierungsintervall
- Standard-Rückblickfenster und Stichprobenlimit
- Auswahl der Schnittstellensprache: Englisch, Französisch, Deutsch
- Themenkonfiguration
- Hardware-ID-Anzeige für Lizenzreferenz

### 9. Sicherung
Direkte Verwaltung der Datenbanksicherungsoperationen:
- Geplante und bedarfsgesteuerte Ausführung
- Sicherungsverlauf mit Zeitstempeln und Dateigrößen
- Alle Sicherungen verschlüsselt und lokal gespeichert

---

## Visueller Stil

- **Rot / Kritisch:** kritische Schweregradalarme
- **Bernstein / Orange:** hoher und Warnungs-Schweregrad
- **Blau:** informative Ereignisse
- **Grün:** normaler / sicherer Status

---

## Reaktionsfähigkeit

Das Dashboard ist für Desktops und Laptops optimiert:
- 13"-Laptops bis Ultrawide-Monitore
- Hochauflösende Bildschirme

---

## Zusammenfassung

Das Nyroxis-Dashboard fordert seine Benutzer nicht auf, zwischen Leistung und Einfachheit zu wählen. Sicherheitsprofis haben die forensische Tiefe, die sie benötigen. Nicht-technische Benutzer haben die Klarheit, die sie benötigen. Schutz auf Unternehmensebene, für jeden zugänglich, den er schützt.
