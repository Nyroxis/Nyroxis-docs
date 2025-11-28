# Architektur – Komponenten

Nyroxis besteht aus mehreren klar definierten, voneinander getrennten Komponenten, die zusammen eine vollständig lokale, datenschutzorientierte Sicherheitsplattform bilden.  
Jedes Modul ist so konzipiert, dass es unabhängig funktioniert, minimale Angriffsfläche bietet und keinerlei Cloud-Abhängigkeit besitzt.

## 1. Nyroxis Agent
Der Agent ist die Hauptkomponente, die direkt auf dem Endgerät läuft und für folgende Aufgaben verantwortlich ist:
- Erfassung sicherheitsrelevanter Ereignisse  
- Strukturierung der Daten  
- sofortige Verschlüsselung  
- zuverlässige Speicherung in der lokalen Datenbank  
- Weitergabe relevanter Informationen an Analyse- und Erkennungsmechanismen  

Er arbeitet leichtgewichtig, stabil und vollständig offline.

## 2. Lokale verschlüsselte Datenbank
Alle Daten werden gespeichert in:
- einem lokalen Speicherbereich  
- vollständig verschlüsselt  
- manipulationsresistent  
- ohne Klartextzugriffe  

Die Datenbank besteht nur aus sicherheitsbezogenen Ereignissen und minimalen Metadaten.

## 3. Analyse-Engine
Die Analyse-Engine verarbeitet:
- Zeitreihen  
- Sequenzen  
- Metadaten  
- Prozess- und Netzwerkzusammenhänge  

Sie bewertet Ereignisse anhand lokaler Regeln und Heuristiken.

## 4. KI-Modul (NyXIA)
NyXIA ist das leichte, lokale KI-Modul, das:
- Verhaltensmuster erkennt  
- Anomalien identifiziert  
- Szenarien erzeugt  
- Risikoindikatoren liefert  

Alles wird offline ausgeführt, basierend auf lokal verschlüsselten Ereignissen.

## 5. Dashboard
Die Benutzeroberfläche zeigt:
- Logs  
- Diagramme  
- Detektionen  
- Szenarien  
- Regelübereinstimmungen  
- Einstellungen  

Das Dashboard ist der zentrale Punkt für Transparenz und Benutzerkontrolle.

## 6. Secure Storage Layer
Diese Schicht sorgt für:
- Integrität der Datenspeicherung  
- hashverkettete Ereignisse  
- Anti-Tamper-Schutz  
- sichere Lese- und Schreiboperationen  

## Zusammenfassung
Die Komponentenarchitektur von Nyroxis ermöglicht vollständige lokale Sicherheit, klare Aufteilung der Verantwortlichkeiten und maximale Privatsphäre — ohne Cloud-Abhängigkeit.
