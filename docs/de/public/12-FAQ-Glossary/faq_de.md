# Häufig Gestellte Fragen

## Allgemein

**Was ist Nyroxis?**
Nyroxis ist ein persönliches Endpoint-SIEM — eine leichtgewichtige, offline-fähige Cybersicherheitsplattform, die SOC-grade Überwachung, Erkennung und forensische Beweise auf persönliche Geräte bringt. Es ist für Führungskräfte, Rechtsanwälte, Familien und Sicherheitsexperten konzipiert, die Schutz auf Enterprise-Niveau ohne Enterprise-Komplexität benötigen.

**Für wen ist Nyroxis?**
Führungskräfte, leitende Manager, Richter, Rechtsanwälte, Ärzte, Journalisten, SOC-Administratoren, Familien, freie Mitarbeiter und Sicherheitsexperten — jeder, dessen persönliches Gerät ein potenzieller Angriffsvektor ist.

**Ist Nyroxis vollständig offline?**
Ja. Keine Cloud, keine Telemetrie, keine Datenübertragung jeglicher Art. Alle Überwachung, Erkennung, KI/ML-Analyse und Lizenzvalidierung erfolgen vollständig auf Ihrem Gerät.

**Welche Plattformen unterstützt Nyroxis?**
Derzeit Windows (v1.0). macOS- und Linux-Unterstützung befindet sich in aktiver Entwicklung.

**Welche Sprachen unterstützt das Dashboard?**
Englisch, Französisch und Deutsch.

---

## Erkennung & Regeln

**Wie viele Erkennungsregeln hat Nyroxis?**
Version 1.0 enthält 27 Erkennungsregeln, 12 Korrelationsregeln und 2 Kettenregeln. Die Bibliothek wächst kontinuierlich, da neue Bedrohungsmuster identifiziert werden.

**Was ist der Unterschied zwischen Erkennungs-, Korrelations- und Kettenregeln?**
- **Erkennung** — identifiziert bekannte Bedrohungsmuster in einzelnen Ereignissen
- **Korrelation** — verbindet zusammenhängende Ereignisse über Zeit und Quellen hinweg, um Muster aufzudecken, die kein einzelnes Ereignis enthüllen würde
- **Kette** — erkennt mehrstufige Angriffssequenzen, die über mehrere Ereignisse und Zeitfenster verteilt sind

**Können Sicherheitsexperten eigene Regeln hinzufügen?**
Ja. Die Regel-Engine ist vollständig erweiterbar. Sicherheitsexperten können benutzerdefinierte Regeln im JSON-Format schreiben und bereitstellen, ohne das Kernsystem zu modifizieren.

---

## Datenschutz & Daten

**Liest Nyroxis meine persönlichen Dateien?**
Nein. Nyroxis erfasst nur sicherheitsrelevante technische Ereignisse — Prozesse, Netzwerkverbindungen, Dateisystemaktivität und Berechtigungsaktionen. Es liest niemals den Inhalt Ihrer Dokumente, E-Mails, Fotos oder den Browserverlauf.

**Wo werden meine Daten gespeichert?**
Alle Daten werden lokal in einer AES-256-verschlüsselten SQLite-Datenbank auf Ihrem Gerät gespeichert. Sie verlassen Ihre Maschine niemals.

**Können Protokolle exportiert werden?**
Ja — vom Dashboard aus können Sie Befunde im PDF- oder CSV-Format für Berichte oder Gerichtsverfahren exportieren.

**Ist die KI/ML-Engine lokal?**
Zu 100 % lokal. Der Isolation Forest-Algorithmus ist in Rust ohne externe ML-Bibliothek implementiert. Es werden niemals Verhaltensdaten an einen Server gesendet.

**Kann ich meine Daten zurücksetzen?**
Ja. Vom Dashboard aus können Sie Ereignisprotokolle, Erkennungsbefunde, die KI-Verhaltens-Baseline und alle Metadaten jederzeit zurücksetzen.

---

## Lizenzierung

**Wie funktioniert die Lizenzierung?**
Jede Lizenz ist an Ihre Hardware (HWID) gebunden. Der kryptografische Schlüssel wird aus dem Hardware-Profil Ihres Geräts abgeleitet. Die Validierung ist vollständig offline — keine Internetverbindung erforderlich.

**Gibt es eine kostenlose Testversion?**
Ja. Jede neue Installation enthält einen Monat vollständigen Zugang ohne Einschränkungen. Keine Kreditkarte erforderlich.

**Was passiert, wenn meine Lizenz abläuft?**
Nyroxis System Guardian stoppt automatisch Nyroxis Agent und Nyroxis Intelligence, wenn die Lizenz abläuft oder für ungültig erklärt wird.

---

## Technisches

**Welche Ressourcen verwendet Nyroxis?**
- Nyroxis Agent: ~57 MB RAM, 0,1 % CPU
- Nyroxis Intelligence: ~87 MB RAM, 1,8 % CPU
- Nyroxis System Guardian: ~6,5 MB RAM, 0,1 % CPU
- Nyroxis Dashboard: ~32 MB RAM wenn geöffnet

**Was ist Nyroxis System Guardian?**
Eine stille Systemtray-Anwendung, die alle Plattformdienste alle 3 Sekunden überwacht, Sicherungen verwaltet, die HWID-basierte Lizenz offline validiert und auf Updates prüft. Sie stoppt automatisch Dienste, wenn die Lizenz abläuft.

**Mit welcher Technologie ist Nyroxis entwickelt?**
Kerndienste sind in Rust entwickelt. Das Dashboard verwendet Tauri + WebView. Die lokale Datenbank ist SQLite. Die Verschlüsselung verwendet AES-256, Ed25519-Signaturen und SHA-256-Hashing. Die KI/ML-Engine ist eine benutzerdefinierte Isolation Forest-Implementierung in Rust ohne externe ML-Bibliothek.

**Funktioniert Nyroxis in Air-Gapped-Umgebungen?**
Ja. Der vollständige Funktionsumfang erfordert null Internetkonnektivität — Überwachung, Erkennung, KI/ML-Analyse und Lizenzvalidierung funktionieren alle vollständig offline.
