# Schutzkern

Der Schutzkern ist das Sicherheits-Rückgrat des Nyroxis Agents.
Er stärkt die Integrität der Überwachung, gewährleistet verschlüsselte Ereignisverarbeitung und verhindert, dass Angreifer Protokolle manipulieren oder die Plattform deaktivieren.

Sein Design folgt strengen Datenschutz-First- und Offline-First-Prinzipien.

---

## Kernziele

Der Schutzkern stellt sicher:
- Sicherheitsereignisse können nicht unbemerkt verändert oder gelöscht werden
- Protokolle bleiben von der Quelle bis zur Speicherung verschlüsselt
- Die Plattform kann nicht stillschweigend deaktiviert werden
- Sensible Komponenten sind vor unbefugten Änderungen geschützt

Dies schafft Vertrauen in die Sichtbarkeits- und forensische Schicht.

---

## 1. Lokale Ende-zu-Ende-Verschlüsselung

Jedes von Nyroxis erfasste Ereignis wird:
- Sofort im Moment der Erfassung verschlüsselt
- Nur in verschlüsselter Form auf die Festplatte geschrieben (AES-256)
- Mit Zeitstempeln und Metadaten indiziert
- Niemals im Klartext gespeichert

Das Verschlüsselungsmodell verhindert, dass Angreifer den Ereignisverlauf lesen oder ändern können.

---

## 2. Integritätsschutz — Hash-verkettete Ereignisblöcke

Nyroxis speichert Ereignisse in einer hash-verketteten Struktur, bei der jeder Block enthält:
- Verschlüsselte Nutzlast
- Integritäts-Hash
- Sequentiellen Index
- Verknüpfung zum vorherigen Block

Dies macht Manipulation sofort erkennbar:
- **Löschung** — der vorherige Hash des nächsten Blocks wird nicht übereinstimmen
- **Änderung** — der Hash des geänderten Blocks wird nicht übereinstimmen
- **Injektion** — Sequenznummern und Ketten-Hashes werden fehlschlagen

Jede Manipulation wird als Sicherheitsereignis gemeldet.

---

## 3. Plattform-Dienstschutz

Nyroxis System Guardian ist dafür verantwortlich sicherzustellen, dass Nyroxis Agent und Nyroxis Intelligence jederzeit in Betrieb bleiben.

Kontinuierlich überprüft Guardian den Betriebsstatus beider Dienste. Wenn einer der Dienste unerwartet stoppt — aufgrund eines Systemereignisses, eines Absturzes oder absichtlicher Einwirkung — erkennt Guardian dies sofort und ergreift Korrekturmaßnahmen.

Abschaltversuche werden als Sicherheitsereignisse protokolliert, um Beweise für Einwirkungen zu sichern.

---

## 4. Offline-Sicherheit

Der Schutzkern benötigt niemals:
- Cloud-Validierung
- Externe APIs
- Remote-Server

Alle Integritätsprüfungen und Verifizierungen erfolgen **100 % offline**.
Die Lizenzvalidierung läuft ebenfalls vollständig offline über AES-GCM-Verschlüsselung und HMAC-Verifizierung.

---

## 5. Sichere Interaktion mit dem Dashboard

Das Dashboard greift auf Ereignisdaten über folgende Wege zu:
- Verifizierte sichere Lesepfade
- Nur-Lese-Zugriff auf Protokolle
- Strikte Trennung zwischen Visualisierung und Ereignisspeicherung

Dies verhindert, dass Angriffe auf UI-Ebene echte Daten modifizieren können.

---

## Zusammenfassung

Der Schutzkern — kombiniert mit Nyroxis System Guardian — stellt sicher, dass Überwachung, Verschlüsselung und Ereignisintegrität auch in feindlichen Umgebungen vertrauenswürdig bleiben, während alle Daten privat, lokal und forensisch zuverlässig gehalten werden.
