# Event Collector

Der Event Collector ist das Modul innerhalb des Nyroxis Agents, das für die kontinuierliche Erfassung sicherheitsrelevanter Ereignisse verantwortlich ist.  
Er stellt sicher, dass alle Aktivitäten auf dem Gerät strukturiert, zuverlässig und vollständig lokal registriert werden.

## Erfasste Kategorien
Der Collector sammelt unter anderem:
- Prozessstarts und -beendigungen  
- Netzwerkverbindungen  
- Dateiänderungen und Dateizugriffe  
- Berechtigungs- und Sicherheitsereignisse  
- Aktivitäten des Systems und installierter Software  

## Verarbeitung
Sobald ein Ereignis erkannt wird:
- wird es klassifiziert  
- wird es mit Zeitstempel versehen  
- wird es an die Verschlüsselungsschicht weitergegeben  
- wird es lokal gespeichert  

Die Erfassung erfolgt vollständig offline und ohne externe Weiterleitung.
