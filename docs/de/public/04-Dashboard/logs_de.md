# Protokolle & Suche

Der Protokolle-Bereich des Nyroxis-Dashboards bietet eine klare, durchsuchbare und strukturierte Ansicht aller sicherheitsrelevanten Ereignisse, die vom Nyroxis Agent gesammelt wurden.
Er ist der forensische Kern der Plattform — darauf ausgelegt, sowohl nicht-technischen Benutzern als auch Sicherheitsprofis sofortige Sichtbarkeit darüber zu geben, was auf ihrem Gerät passiert.

---

## Zweck der Protokollansicht

Das Protokollmodul hilft Benutzern zu verstehen:
- Welche Ereignisse wann stattgefunden haben
- Welche Prozesse, Dateien oder Netzwerkverbindungen beteiligt waren
- Ob die Aktivität normal oder verdächtig erscheint
- Den vollständigen Kontext eines jeden Ereignisses für forensische Untersuchungen

Es wandelt rohe verschlüsselte Ereignisdaten in lesbare, mit Zeitstempeln versehene, durchsuchbare Einträge um.

---

## Ereigniskategorien

Nyroxis organisiert Protokolle in intuitive Gruppen:

### 1. Prozessereignisse
- Prozessstart und -stopp
- Eltern-/Kind-Beziehungen
- Ausführungspfade und Befehlszeilenparameter

### 2. Netzwerkereignisse
- Ausgehende und eingehende Verbindungen
- IP-Adressen und Port-Details
- Protokolltypen

### 3. Dateisystemereignisse
- Dateierstellung, -änderung und -löschung
- Zugriff auf sensible Verzeichnisse
- Registrierungsänderungen

### 4. Berechtigungs- & Sicherheitsereignisse
- Erhöhungsversuche
- Zugriff auf eingeschränkte Ressourcen
- Systemrichtlinienänderungen
- Anmeldeinformationsbezogene Aktivitäten

### 5. Systemaktivität
- Dienststarten und -stoppen
- Treiberladen
- Windows-Ereignisprotokolleinträge (Sicherheit, System, Anwendung)
- PowerShell- und Skriptausführung

---

## Suche & Filterung

Die Protokollschnittstelle enthält ein leistungsstarkes Filterpanel:

### Verfügbare Filter
- Datums- und Zeitbereich
- Ereigniskategorie
- Schweregrad (Kritisch / Hoch / Warnung / Info)
- Quelle und Kanal
- Prozessname
- Dateipfad
- Netzwerkendpunkt
- Schlüsselwörter

### Suchfunktionen
- Echtzeitfilterung
- Mehrfeld-Suche
- CSV-Export für rechtliche Dokumentation oder externe Analyse

Für Einsteiger und professionelle Analysten gleichermaßen konzipiert.

---

## Ereignisdetails

Ein Klick auf ein Ereignis öffnet ein Detailpanel mit:
- Vollständigen Ereignismetadaten
- Prozessherkunft
- Zugehörige Dateien oder Netzwerkverbindungen
- Schweregradwert
- Details der rohen Nutzlast

---

## Datenschutz & Offline-First

Alle Protokolle:
- Werden lokal in der verschlüsselten SQLite-Datenbank gespeichert
- Sind vollständig verschlüsselt (AES-256)
- Verlassen das Gerät nie
- Werden ohne jegliche Cloud-Interaktion verarbeitet

---

## Zusammenfassung

Das Modul Protokolle & Suche bietet eine transparente, organisierte und vollständig private Möglichkeit, Systemaktivitäten zu erkunden — und gibt Benutzern echte forensische Sichtbarkeit, ohne Daten extern preiszugeben.
