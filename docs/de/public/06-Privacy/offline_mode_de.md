# Offline-Modus

> **Eine optionale Ausnahme:** Der **AI Copilot** ist eine in der EU gehostete Cloud-Funktion, auf Aktivierung. Wenn Sie ihn bewusst aktivieren und eine bestimmte Warnung analysieren, werden die Daten dieser Warnung an nyroxis.ai gesendet. Er ist standardmäßig deaktiviert. Alles auf dieser Seite bezieht sich auf den Offline-Kern, der ohne jegliche Konnektivität funktioniert. Siehe die Seite *AI Copilot*.

Nyroxis ist von Grund auf für den vollständig offline Betrieb ausgelegt — ohne Cloud-Zugang, Remote-Authentifizierung oder externe APIs zu benötigen.
Dieses Design gibt Benutzern Sicherheit, Privatsphäre und volle Autonomie über ihr Gerät.

---

## Warum Offline wichtig ist

Der Offline-Betrieb gewährleistet:
- **Keine Daten verlassen das Gerät** — jemals
- **Keine Exposition gegenüber Cloud-Verstößen** oder Ausfällen von Drittanbieter-Infrastrukturen
- **Keine Abhängigkeit von externen Servern** für Überwachung oder Erkennung
- **Kein Risiko der Drittanbieter-Überwachung** oder Verhaltensprofilierung
- **Volle Funktionalität auch ohne Internet** — einschließlich in air-gapped Umgebungen

Benutzer behalten die vollständige Kontrolle über ihre Sicherheitsdaten.

---

## 1. Vollständiger lokaler Betrieb

Jede Funktion der Nyroxis-Plattform arbeitet lokal:
- Ereigniserfassung und -normalisierung (Nyroxis Agent)
- Erkennung, Korrelation und Kettenregelauswertung (Nyroxis Intelligence)
- Dienstüberwachung, Backup und Lizenzvalidierung (Nyroxis System Guardian)
- KI/ML-Anomalieerkennung und statistische Analyse
- Dashboard-Visualisierung und Berichterstattung

Nichts wird hochgeladen. Nichts wird übertragen.

---

## 2. Kein Cloud, keine Server

Nyroxis verwendet nicht:
- Cloud-Verarbeitung oder -Speicherung
- Telemetrie oder Nutzungsverfolgung
- Remote-Protokollierung
- Online-Scanning oder Bedrohungsintelligenz-Feeds
- Externe Authentifizierungsdienste

Dies eliminiert ganze Klassen von Datenschutz- und Angriffsrisiken.

---

## 3. Offline-Lizenzvalidierung

Nyroxis System Guardian validiert die HWID-basierte Lizenz vollständig offline:
- Keine Internetverbindung erforderlich
- Die Validierung verwendet AES-GCM-Verschlüsselung und HMAC-Verifizierung lokal
- Die Lizenzintegrität wird ohne Kontaktaufnahme mit einem externen Server durchgesetzt

---

## 4. Lokaler KI/ML-Motor

Der Isolation-Forest- und Statistikanalysemotor läuft vollständig offline:
- Erkennung von Verhaltensanomalien
- Z-Score-Klassifizierung
- Spitzenerkennung und Basislinienvergleich

Alles wird direkt aus verschlüsselten lokalen Ereignissen berechnet — keine Cloud-Inferenz, keine Modellaktualisierungen über das Netzwerk.

---

## 5. Update-Prüfung (optional)

Nyroxis System Guardian kann Updates in konfigurierbaren Intervallen prüfen.
Die Update-Installation bleibt manuell — es gibt keine erzwungenen oder automatischen Cloud-Verbindungen.
Die Plattform arbeitet unabhängig vom Update-Status mit voller Kapazität.

---

## 6. Transparente Architektur

Nyroxis zeigt im Dashboard klare Indikatoren, die Benutzern ermöglichen zu überprüfen:
- Keine ausgehenden Netzwerkverbindungen von Nyroxis-Prozessen
- Keine Hintergrundtelemetrie
- Keine Cloud-Abhängigkeit

Vertrauen ist messbar — nicht angenommen.

---

## Zusammenfassung

Der Offline-Modus garantiert, dass Nyroxis privat, verschlüsselt, autonom und vollständig lokal bleibt — eine Sicherheitsplattform, die darauf ausgelegt ist, Benutzer zu schützen, ohne ihre Daten jemals preiszugeben.
