# Schritt 8: Orchestrierung bei komplexem Feature

Für ein komplexeres Feature (z.B. Import/Export, Statistiken, 
Duplikat-Erkennung) die volle Sub-Agent-Orchestrierung nutzen.

**Prompt:**
```
Ich möchte das Feature "[Feature-Name]" hinzufügen. Das ist 
komplexer, deshalb gehen wir strukturiert vor:

1. Explorer-Sub-Agent: Analysiere die aktuelle Codebase und 
   identifiziere alle Stellen die betroffen sein könnten. 
   Liefere eine kompakte Zusammenfassung zurück.

2. Plan-Sub-Agent: Basierend auf der Analyse einen 
   detaillierten Implementierungsplan erstellen.

3. Ich bestätige den Plan.

4. Primary-Agent: Implementierung.

5. Review-Sub-Agent: Abschließende Prüfung mit leerem Kontext.
```

**Merke:** Separation of Concerns. Jeder Agent hat seine Aufgabe, 
der Primary-Kontext bleibt schlank, Ergebnisse werden als 
kompakte Zusammenfassungen übergeben.
