# KI-Erkennungen

Die KI-Erkennungsansicht zeigt Anomalien, die von der lokalen KI/ML-Engine identifiziert wurden — wenn diese ungewöhnliche oder verdächtige Aktivitäten auf dem Gerät basierend auf Verhaltensanalyse und statistischer Bewertung erkennt.
Alle Erkennungen werden lokal generiert, ohne Cloud-Verarbeitung oder Datenweitergabe.

---

## Zweck der KI-Erkennungen

Die KI-Engine erkennt:
- Verhaltensanomalien — Abweichungen von der etablierten Gerätbasislinie
- Verdächtige Aktivitätssequenzen
- Seltene oder unerwartete Muster
- Statistische Ausreißer über Verhaltensmerkmale hinweg
- Hochrisikoabweichungen, die durch Isolation-Forest-Bewertung identifiziert werden

Diese Erkennungen ergänzen die regelbasierten Ergebnisse von Nyroxis Intelligence und fügen eine Schicht verhaltensbasierter Intelligenz hinzu, die nicht auf vordefinierten Regeln basiert.

---

## Arten von KI-Erkennungen

### 1. Anomaliebasierte Erkennungen
Ausgelöst, wenn der Isolation-Forest-Anomalie-Score 0,6 überschreitet — was bedeutet, dass das beobachtete Verhaltensmuster statistisch von der normalen Basislinie isoliert ist.

Beispielfälle:
- Ungewöhnliche Prozessaktivität zu unerwarteten Zeiten
- Unregelmäßige Netzwerkverbindungsmuster
- Unerwartete Dateiänderungsschübe
- Aktivität weit außerhalb der typischen Tageszeit- oder Wochentagsbasislinie

---

### 2. Statistische Ausreißer (Z-Score)
Ausgelöst, wenn ein bestimmtes Verhaltensmerkmal erheblich vom historischen Mittelwert abweicht:
- Kritisch: Z-Score > 3,0 (99,7 % Konfidenz)
- Hoch: Z-Score > 2,0 (95 % Konfidenz)
- Mittel: Z-Score > 1,5 (86 % Konfidenz)
- Niedrig: Z-Score > 1,0 (68 % Konfidenz)

---

### 3. Spike-Erkennungen
Ausgelöst, wenn eine überwachte Metrik plötzlich weit über ihren historischen Durchschnitt springt:
- Plötzlicher Ereignisschub pro Stunde
- Spike bei neuen Netzwerkzielen
- Schneller Anstieg eindeutiger Quellen

---

### 4. Persistente Anomalien
Langfristige Abweichungen, die sich im Laufe der Zeit ansammeln:
- Allmählicher Anstieg des Neue-Ziele-Verhältnisses
- Sich langsam aufbauende ungewöhnliche Aktivitätsmuster
- Wiederholte Anomalien mit niedrigem Score, die einen Trend bilden

---

## Erkennungsdetails

Jede KI-Erkennung enthält:
- Beschreibung der Anomalie
- Anomalie-Score (0,0 – 1,0)
- Schweregradklassifizierung
- Beitragende Merkmale — die spezifischen Verhaltensdimensionen, die am stärksten von der Basislinie abwichen, mit Z-Score-Werten
- Zeitstempel und Analysefenster

---

## 100 % Lokal & Privat

Alle KI-Erkennungen sind:
- Offline auf dem Gerät berechnet
- Lokal in der verschlüsselten Datenbank gespeichert
- Aus verschlüsselten Ereignisprotokollen abgeleitet
- Werden niemals auf Server hochgeladen oder mit Dritten geteilt

---

## Zusammenfassung

KI-Erkennungen liefern intelligente, datenschutzfreundliche Anomaliewarnungen, die die regelbasierte Erkennung ergänzen — und Benutzern helfen, gefährliche oder abnormale Aktivitäten frühzeitig zu erkennen, mit vollständig lokaler Verarbeitung und ohne Cloud-Abhängigkeit.
