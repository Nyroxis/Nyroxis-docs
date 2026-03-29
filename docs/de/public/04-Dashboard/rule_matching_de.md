# Regelabgleich & Erkennung

Das Regelabgleichsmodul ist die Art und Weise, wie Nyroxis Intelligence Sicherheitsereignisse bewertet und Alarme generiert.
Es bringt SIEM-ähnliche Erkennungslogik auf persönliche Geräte — vollständig offline, datenschutzorientiert und von Sicherheitsprofis erweiterbar.

---

## Was der Regelabgleich tut

Nyroxis Intelligence bewertet Ereignisse anhand von drei Schichten lokaler Regeln, um Folgendes zu identifizieren:
- Bekannte Bedrohungsmuster in einzelnen Ereignissen
- Verdächtige Beziehungen zwischen Ereignissen über die Zeit
- Mehrstufige Angriffssequenzen

Keine Regeln oder Protokolle werden jemals online gesendet.

---

## Drei Erkennungsschichten

### Schicht 1 — Erkennungsregeln (27 Regeln)
Mustererkennung gegen einzelne Ereignisse.

**Auslösertypen:**
- Verdächtige Prozessausführung
- Nicht autorisierte Dienstinstallation
- Abnormales Netzwerkverhalten
- Versuche des Zugriffs auf Anmeldeinformationen
- Indikatoren bekannter Malware-Aktivität

Wenn eine Erkennungsregel ausgelöst wird, wird sofort ein Alarm generiert und in der Erkennungsdatenbank gespeichert.

---

### Schicht 2 — Korrelationsregeln (12 Regeln)
Mustererkennung über verwandte Ereignisse hinweg, über Zeit und Quellen.

**Auslösertypen:**
- Fehlgeschlagene Anmeldung gefolgt von einer erfolgreichen von einem anderen Standort
- Neuer Prozess, der unmittelbar nach USB-Geräteanschluss startet
- Wiederholte fehlgeschlagene Verbindungen gefolgt von einem erfolgreichen ausgehenden Anruf
- Skriptausführung gefolgt von Dateisystemänderung

Korrelationsregeln enthüllen Bedrohungsmuster, die kein einzelnes Ereignis allein aufdecken würde.

---

### Schicht 3 — Kettenregeln (2 Regeln)
Erkennung mehrstufiger Angriffssequenzen, die sich über mehrere Ereignisse und Zeitfenster erstrecken.

Kettenregeln sind die Alarme mit höchster Priorität im System. Sie repräsentieren koordinierte, progressive Einbrüche — die Art, die für Advanced Persistent Threats charakteristisch ist.

Jeder Kettenfund umfasst eine vollständige Rekonstruktion der erkannten Angriffssequenz.

---

## Erweiterbar durch Sicherheitsprofis

Die Regel-Engine ist vollständig für Erweiterungen offen. Sicherheitsprofis können:
- Benutzerdefinierte Erkennungs-, Korrelations- oder Kettenregeln im JSON-Format schreiben
- Sie direkt in das System einsetzen, ohne Kernkomponenten zu ändern
- Regeln gegen bestehende Ereignisdaten vor der Bereitstellung testen
- Ihre benutzerdefinierte Regelbibliothek versionieren und verwalten

Dies ermöglicht es, Nyroxis an spezifische Umgebungen, Bedrohungsmodelle oder organisatorische Anforderungen anzupassen.

---

## Wie die Engine Regeln bewertet

Nyroxis Intelligence gleicht Regeln ab gegen:
- Ereignismetadaten und -inhalt
- Zeitstempel und Zeitfenster
- Prozessherkunft
- Netzwerkendpunkte
- Schweregradangaben
- Ereignisübergreifende Beziehungen

Alle Auswertungen erfolgen in Echtzeit und vollständig lokal.

---

## Wenn eine Regel ausgelöst wird

Wenn eine Regel übereinstimmt, führt Nyroxis folgende Aktionen durch:
- Sofortiger Alarm wird ausgelöst
- Der Befund wird in der dedizierten Erkennungsdatenbank gespeichert
- Die übereinstimmenden Ereignisse, der Schweregrad und die Regeldetails werden aufgezeichnet
- Der Befund wird in der Erkennungs-, Korrelations- oder Kettenansicht des Dashboards sichtbar gemacht

---

## Datenschutzgarantie

Alle Regelabgleiche:
- Erfolgen lokal auf dem Gerät
- Kommunizieren nicht mit externen Diensten
- Verwenden ausschließlich verschlüsselte Ereignisdaten
- Laden niemals Protokolle, Regeln oder Musterübereinstimmungen hoch

---

## Zusammenfassung

Die Regelabgleichs-Engine von Nyroxis bringt strukturierte, SIEM-ähnliche Erkennung auf persönliche Endpunkte — über drei Schichten, kontinuierlich wachsend und von Sicherheitsprofis erweiterbar — ohne Cloud-Abhängigkeit oder Datenschutzkompromisse.
