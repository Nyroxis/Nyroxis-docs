# Verschlüsselungsmodell

Nyroxis implementiert ein striktes, mehrschichtiges Verschlüsselungsmodell, das sicherstellt, dass **keine lesbaren Daten jemals auf die Festplatte gelangen**, und dass alle Sicherheitsereignisse geschützt, privat und überprüfbar bleiben.

---

## Grundlegende Ziele

Die Nyroxis-Verschlüsselung erreicht:
- **Vertraulichkeit** — niemand kann Benutzerdaten lesen
- **Integrität** — niemand kann Protokolle unbemerkt ändern
- **Isolation** — Daten verlassen das Gerät niemals
- **Null-Klartext-Speicherung** — alles wird bei der Erfassung verschlüsselt
- **Offline-Betrieb** — keine Cloud-Schlüssel oder Server erforderlich

---

## 1. Verschlüsselung bei der Ereigniserfassung

Jedes Systemereignis wird in dem Moment verschlüsselt, in dem es von Nyroxis Agent erfasst wird.

Schritte:
1. Das Ereignis wird im Arbeitsspeicher serialisiert
2. Ein gerätespezifischer Schlüssel wird aus Hardware-Identifikatoren (HWID) abgeleitet
3. Das Ereignis wird mit AES-256 verschlüsselt
4. Nur der verschlüsselte Block wird in den Speicher geschrieben

Es werden niemals Klartextprotokolle geschrieben.

---

## 2. Verschlüsselte Lokale Datenbank

Alle Protokolle, Erkennungsbefunde, KI-Ergebnisse und Metadaten werden in einer sicheren SQLite-Datenbank gespeichert.

Funktionen:
- AES-256-verschlüsselte Datenseiten
- Verschlüsselte Metadaten
- Hash-verkettete Speicherblöcke
- Integritätsprüfung pro Datensatz
- Kein Klartext-Caching

Die Datenbank kann nicht außerhalb von Nyroxis geöffnet oder gelesen werden und kann auf einem anderen Gerät nicht entschlüsselt werden.

---

## 3. Entschlüsselung Nur im Arbeitsspeicher

Nyroxis entschlüsselt Datensätze *nur während ihrer Verarbeitung*:
- Die KI/ML-Engine entschlüsselt Ereignis-Batches im RAM während der Analyse
- Das Dashboard entschlüsselt nur das, was es anzeigen muss, im Arbeitsspeicher
- Nichts wird im Klartext zurückgeschrieben
- Speicherpuffer werden nach der Verwendung geleert

Dies eliminiert das Risiko der forensischen Wiederherstellung von Klartext von der Festplatte.

---

## 4. Gerätebezogene Schlüssel

Verschlüsselungsschlüssel sind:
- Aus den Hardware-Identifikatoren des Benutzers (HWID) abgeleitet
- Lokal auf dem Gerät generiert
- Niemals direkt in der Anwendung gespeichert
- Niemals an einen Server übertragen

Selbst wenn die Datenbankdatei auf ein anderes Gerät kopiert wird, kann sie nicht entschlüsselt werden — sie ist an die ursprüngliche Hardware gebunden.

---

## 5. Integritätsschutz — Hash-Kette

Jeder verschlüsselte Block enthält:
- Integritäts-Hash des Block-Inhalts
- Ereignis-Sequenzindex
- Hash des vorherigen Blocks

Dies bildet eine **Hash-Kette**, die aufdeckt:
- Protokolllöschung — der Vorherige-Hash des nächsten Blocks wird nicht übereinstimmen
- Protokollmodifikation — der Block-Hash wird nicht übereinstimmen
- Protokoll-Neuanordnung — der Sequenzindex wird falsch sein
- Protokollinjektion — Ketten- und Sequenzprüfungen werden fehlschlagen

Manipulationen sind sofort erkennbar.

---

## 6. Keine Cloud-Beteiligung

Nyroxis verwendet nicht:
- Cloud-Schlüsseltresore
- Entfernte Schlüsselserver
- Online-Aktivierung
- Telemetriesysteme

Alle Verschlüsselung, Schlüsselableitung und Integritätsprüfung erfolgen vollständig lokal.

---

## Zusammenfassung

Die Nyroxis-Verschlüsselung gewährleistet:
- Null-Klartext-Speicherung
- Überall-verschlüsselt-Design
- Gerätebezogene lokale Schlüssel
- Hash-verkettete, manipulationssichere Protokolle
- Entschlüsselung nur im Arbeitsspeicher

Ein modernes Verschlüsselungsmodell für persönliche Sicherheit und vollständige offline Autonomie.
