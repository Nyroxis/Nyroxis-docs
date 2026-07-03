# AI Copilot — Optionale cloudgestützte Analyse

Der **AI Copilot** ist eine optionale, ausdrücklich zu aktivierende Funktion, die Ihnen eine natürlichsprachliche Erklärung einer bestimmten Warnung im Expertenstil liefert — was sie bedeutet, wie schwerwiegend sie ist und welche Maßnahmen als Nächstes zu ergreifen sind.

Anders als die lokale KI/ML-Engine (die vollständig auf Ihrem Gerät läuft) ist der AI Copilot **cloudgestützt**: Er sendet die Details einer einzelnen Warnung an einen in der EU gehosteten Dienst (nyroxis.ai), der ein großes Sprachmodell zur Erstellung der Analyse nutzt. Da dies das Senden von Daten außerhalb des Geräts beinhaltet, behandelt Nyroxis diese Funktion als bewusste, transparente Entscheidung — sie ist **standardmäßig deaktiviert** und läuft niemals automatisch.

---

## Lokale KI vs. AI Copilot

Nyroxis verfügt über zwei eigenständige, klar verschiedene Intelligenzschichten. Es ist wichtig, sie nicht zu verwechseln:

| | Lokale KI/ML-Engine | AI Copilot |
|---|---------------------|------------|
| Wo sie läuft | Vollständig auf Ihrem Gerät | In der EU gehosteter Cloud-Dienst (nyroxis.ai) |
| Netzwerk | Keines — vollständig offline | Sendet die Daten einer Warnung über HTTPS |
| Wann sie läuft | Bei Bedarf, lokal | Nur wenn Sie auf „Analysieren“ klicken |
| Standardmäßig aktiviert | Ja (offline) | Nein — nur auf Aktivierung |
| Was sie tut | Anomalieerkennung (Isolation Forest + Statistik) | Natürlichsprachliche Erklärung einer einzelnen Warnung |

Die lokale Engine wird auf den Seiten **Lokale KI** beschrieben. Diese Seite behandelt ausschließlich den optionalen Cloud-Copilot.

---

## Funktionsweise

1. Sie verbinden ein AI-Copilot-Konto über **Einstellungen → AI Copilot** und setzen ein ausdrückliches Einwilligungshäkchen.
2. Sie öffnen eine bestimmte Warnung und klicken auf **Analysieren**.
3. Das Dashboard sendet die Informationen dieser einen Warnung an nyroxis.ai.
4. Der Dienst gibt eine natürlichsprachliche Analyse in Ihrer Oberflächensprache (Englisch, Französisch oder Deutsch) zurück, einschließlich MITRE-ATT&CK-Kontext und empfohlener nächster Schritte.

Es gibt keine Übertragung im Hintergrund, keinen Massen-Upload und keine automatische Analyse. Jede Analyse betrifft eine einzelne Warnung, die nur gesendet wird, wenn Sie es anfordern. Sie können sich jederzeit trennen, wodurch die lokale Anmeldeinformation entfernt wird.

---

## Was gesendet wird — und was nicht

Wenn Sie eine Warnung analysieren, sendet das Dashboard an nyroxis.ai:

- Die Warnungs-Metadaten (Regel, Schweregrad, Kanal, Zeitstempel, Status)
- Die der Warnung zugeordnete Quell-IP-Adresse
- Ihre eigene Notiz zur Warnung (falls vorhanden)
- Die Definition der übereinstimmenden Regel

**Niemals gesendet:** Ihre rohen Windows-Ereignisprotokolle, die verschlüsselte Ereignisdatenbank oder Ergebnisse der lokalen KI/ML-Engine.

Serverseitig wird nyroxis.ai auf EU-Infrastruktur gehostet. Bevor ein Analyse-Datensatz gespeichert wird, wird die Quell-IP-Adresse durch einen Einweg-Hash ersetzt, und gängige Pfad-/Benutzernamenmuster in der Notiz werden maskiert. Zur Erstellung seiner Analyse verarbeitet der Dienst tatsächlich die oben beschriebenen Warnungsinformationen — dies ist der inhärente Kompromiss jeder cloudgestützten Analyse und genau der Grund, warum die Funktion auf ausdrücklicher Aktivierung und einer Verarbeitung pro Warnung beruht und nicht automatisch erfolgt.

---

## Tarife

Der AI Copilot ist ein separates, optionales Abonnement mit einer kostenlosen Stufe, sodass Sie ihn kostenlos ausprobieren können:

| Tarif | Preis | Analysen pro Monat |
|-------|-------|--------------------|
| Free | 0 € | 30 |
| Pro | 29 € / Monat | 1.000 |
| Team | 59 € / Monat | 5.000 |
| Business | 149 € / Monat | 15.000 |

Alle AI-Copilot-Tarife werden in der EU gehostet und sind DSGVO-konform ausgerichtet. Die Nyroxis-Desktop-Plattform und das AI-Copilot-Abonnement sind unabhängig voneinander — die Plattform ist ohne jegliches AI-Copilot-Abonnement voll funktionsfähig. Siehe die Seite *AI Copilot*. Preise und Limits sind Richtwerte und können sich ändern; aktuelle Angaben finden Sie unter [www.nyroxis.com](https://www.nyroxis.com).

---

## Zusammenfassung

Der AI Copilot bringt eine fachkundige, natürlichsprachliche Zweitmeinung zu jeder Warnung — transparent angeboten, in der EU gehostet, auf Aktivierung und vollständig unter Ihrer Kontrolle. Wenn Sie eine vollständig offline betriebene Konfiguration bevorzugen, lassen Sie ihn einfach deaktiviert: Alles andere in Nyroxis funktioniert weiterhin auf dem Gerät.
