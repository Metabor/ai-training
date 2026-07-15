# Schritt 4: Rules File erstellen

Sobald die Basis läuft und ein Code-Stil etabliert ist.

**Prompt:**
```
Wir haben jetzt eine Basis. Analysiere den Code-Stil den wir 
etabliert haben und erstelle daraus ein Rules File unter 
.claude/rules/[sprache].md.

Das Rules File soll:
- Automatisch laden wenn an Dateien der entsprechenden Sprache 
  gearbeitet wird (paths im Frontmatter setzen)
- Unsere Naming Conventions festhalten
- Unsere Architektur-Entscheidungen dokumentieren
- Konkrete Beispiele enthalten (so machen wir es / so nicht)

Das Frontmatter sieht so aus:
---
paths:
  - "**/*.php"
---

Prüfe mit /memory ob die Regel geladen wird.
```

**Merke:** Dynamischer Kontext. Rules Files werden nur bei 
passenden Dateitypen geladen und sparen Tokens gegenüber einer 
überladenen CLAUDE.md.

**Merke:** Prüfe die Wirkung, nicht die Absicht. Ein Rules File, das
nicht lädt, sagt nichts — es schweigt. `/memory` listet auf, was
tatsächlich geladen ist. Ein Sub-Agent kann Syntax bestätigen, die
es nicht gibt; die laufende Instanz kann es nicht.
