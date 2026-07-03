# Glossar

**AES-256** — Advanced Encryption Standard mit einem 256-Bit-Schlüssel. Wird verwendet, um alle Nyroxis-Ereignisprotokolle und den Datenbankspeicher im Ruhezustand zu verschlüsseln.

**Agent** — Siehe *Nyroxis Agent*.

**Anomalie-Score** — Ein Wert zwischen 0,0 und 1,0, der von der Isolation Forest-Engine erzeugt wird. Höhere Werte weisen auf anomaleres Verhalten hin. Werte über 0,6 lösen eine Erkennung aus.

**Verhaltens-Baseline** — Ein lokales Profil der normalen Geräteaktivität, das von der KI/ML-Engine im Laufe der Zeit aufgebaut wird und zur Identifizierung von Abweichungen dient.

**Kettenregel** — Eine Erkennungsregel, die auf mehrstufige Angriffssequenzen abzielt, die über mehrere Ereignisse und Zeitfenster verteilt sind. Nyroxis v1.0 enthält 2 Kettenregeln.

**Korrelationsregel** — Eine Erkennungsregel, die zusammenhängende Ereignisse über Zeit und Quellen hinweg verbindet, um Muster aufzudecken, die kein einzelnes Ereignis enthüllen würde. Nyroxis v1.0 enthält 12 Korrelationsregeln.

**Erkennungsregel** — Eine Regel, die bekannte Bedrohungsmuster in einzelnen Ereignissen anvisiert. Nyroxis v1.0 enthält 27 Erkennungsregeln.

**Forensische Beweise** — Manipulationssichere, verschlüsselte Ereignisprotokolle, die von forensischer Qualität und für Sicherheitsuntersuchungen geeignet sind.

**Hash-Kette** — Eine kryptografische Struktur, bei der jeder Ereignisblock den Hash des vorherigen Blocks enthält, wodurch Löschung, Modifikation, Injektion oder Neuanordnung sofort erkennbar werden.

**HMAC** — Hash-based Message Authentication Code. Wird bei der Nyroxis-Lizenzvalidierung verwendet, um die Dateiintegrität offline zu verifizieren.

**HWID** — Hardware-Identifikator (Hardware Identifier). Ein eindeutiger Wert, der aus den physischen Eigenschaften eines Geräts abgeleitet wird und verwendet wird, um eine Nyroxis-Lizenz an eine bestimmte Maschine zu binden und Verschlüsselungsschlüssel abzuleiten.

**Isolation Forest** — Ein Machine-Learning-Algorithmus, der Anomalien erkennt, indem er zufällige Entscheidungsbäume aufbaut und misst, wie schnell jeder Datenpunkt isoliert wird. In Nyroxis in Rust ohne externe ML-Bibliothek implementiert.

**IQR** — Interquartilbereich (Interquartile Range). Eine statistische Methode zur Ausreißererkennung, die in der Nyroxis-statistischen Analyse-Engine verwendet wird.

**Nyroxis Agent** — Der Kern-Überwachungsdienst. Erfasst, normalisiert, verschlüsselt und speichert Sicherheitsereignisse lokal (~57 MB RAM, 0,1 % CPU).

**Nyroxis Dashboard** — Die Benutzeroberfläche für Sichtbarkeit, forensische Analyse, KI/ML-Einblicke und Berichte.

**Nyroxis Intelligence** — Die Erkennungs- und Korrelations-Engine. Arbeitet mit 27 Erkennungsregeln, 12 Korrelationsregeln und 2 Kettenregeln (~87 MB RAM, 1,8 % CPU).

**Nyroxis System Guardian** — Der Plattformwächter. Überwacht alle Dienste kontinuierlich, verwaltet Sicherungen, validiert die Lizenz offline und prüft auf Updates (~6,5 MB RAM, 0,1 % CPU).

**Regel-Engine** — Die Komponente innerhalb von Nyroxis Intelligence, die eingehende Ereignisse in Echtzeit gegen Erkennungs-, Korrelations- und Kettenregeln auswertet.

**SIEM** — Security Information and Event Management. Ein System, das Sicherheitsereignisse sammelt, korreliert und analysiert. Nyroxis funktioniert als persönliches Endpoint-SIEM.

**SQLite** — Die lokale Datenbank-Engine, die von Nyroxis zum Speichern verschlüsselter Ereignisprotokolle und Erkennungsbefunde verwendet wird.

**Manipulationsschutz** — Mechanismen einschließlich hash-verketteter Ereignisblöcke und Integritätsprüfung, die Angreifer daran hindern, Protokolle unbemerkt zu löschen, zu modifizieren oder zu injizieren.

**Z-Score** — Ein statistisches Maß dafür, wie viele Standardabweichungen ein Wert vom Mittelwert entfernt ist. Von Nyroxis verwendet, um den Anomalie-Schweregrad zu klassifizieren: Kritisch (>3,0), Hoch (>2,0), Mittel (>1,5), Niedrig (>1,0).
