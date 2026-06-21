# Schritt 1: Setup und Planung (Plan Mode)

Claude Code im gewünschten Verzeichnis starten. Plan Mode 
aktivieren (Shift+Tab zweimal).

**Prompt:**
```
Ich möchte eine Sammlungs-Verwaltung bauen. Ich habe eine 
Spezifikation, die ich dir gleich gebe.

Mein Anwendungsfall: [z.B. Plattensammlung, Weinkeller, 
Buchsammlung, Gaming-Backlog]

Meine Technologie-Präferenz: [z.B. Python mit CLI, 
Node.js mit Web-UI, Rust, HTML/JS im Browser, oder "egal, 
schlag etwas vor"]

Bitte lies die Spezifikation und erstelle einen Plan für die 
Basis-Implementierung. Stelle Rückfragen falls etwas unklar ist.

[Hier den Inhalt von Teil 1 der Spezifikation einfügen]
```

Den Inhalt von Teil 1 findest du in `00_spezifikation.md`.

Plan durchgehen, bei Bedarf anpassen, bestätigen.

**Merke:** Plan + Bestätigung. Der Agent fragt nach, bevor er 
implementiert. Lass dir bei komplexen Aufgaben immer erst einen 
Plan erstellen, bevor Code geschrieben wird.
