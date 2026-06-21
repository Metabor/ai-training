# Schritt 4: Rules File erstellen

Sobald die Basis läuft und ein Code-Stil etabliert ist.

**Prompt:**
```
Wir haben jetzt eine Basis. Analysiere den Code-Stil den wir 
etabliert haben und erstelle daraus ein Rules File unter 
.claude/rules/[sprache].mdc.

Das Rules File soll:
- Automatisch laden wenn an Dateien der entsprechenden Sprache 
  gearbeitet wird (globs im Frontmatter setzen)
- Unsere Naming Conventions festhalten
- Unsere Architektur-Entscheidungen dokumentieren
- Konkrete Beispiele enthalten (so machen wir es / so nicht)

Nutze den Claude Code Guide Sub-Agent um die Syntax zu prüfen.
```

**Merke:** Dynamischer Kontext. Rules Files werden nur bei 
passenden Dateitypen geladen und sparen Tokens gegenüber einer 
überladenen CLAUDE.md.
