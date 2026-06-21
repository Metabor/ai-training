# Schritt 5: Eigene Felder ergänzen (mit Review Sub-Agent)

Die Basis um die anwendungsfall-spezifischen Felder erweitern.

**Prompt:**
```
Erweitere das Datenmodell um folgende Felder passend zu meinem 
Anwendungsfall: [Felder aufzählen]

Stelle sicher dass:
- Die Felder in allen Operationen (anlegen, bearbeiten, anzeigen) 
  berücksichtigt werden
- Die Persistenz angepasst wird
- Bestehende Daten weiterhin funktionieren (Migration falls nötig)
```

Welche Felder zu deinem Anwendungsfall passen, steht in Teil 2 
der Spezifikation (`00_spezifikation.md`).

Nach der Implementierung:

**Prompt:**
```
Lass einen Review-Sub-Agent mit leerem Kontext die Änderungen 
prüfen. Er soll:
- Konsistenz mit dem bestehenden Code prüfen
- Potentielle Fehler finden
- Einen kurzen Report erstellen

Falls noch kein Review-Sub-Agent existiert, erstelle ihn unter 
.claude/agents/code-reviewer.md.
```

**Merke:** Vermeide Confirmation Bias. Der Primary-Agent übersieht 
eigene Fehler. Ein Sub-Agent mit frischem Kontext findet sie.
