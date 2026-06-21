# Schritt 7: Skill erstellen für wiederkehrende Aufgaben

Beim zweiten Feature aus dem Katalog wird oft klar: "Das 
Muster habe ich schon mal gemacht." Genau dann lohnt sich 
ein Skill.

**Prompt:**
```
Ich habe jetzt das zweite Feature hinzugefügt. Die Vorgehens-
weise war bei beiden ähnlich: neues Feld zum Modell, Persistenz 
anpassen, UI erweitern, Tests.

Erstelle einen Skill unter .claude/skills/feature-hinzufuegen/SKILL.md, 
der diesen Prozess als wiederverwendbares Template festhält.

Die SKILL.md soll:
- Im Frontmatter beschreiben wann der Skill aktiviert werden soll
- Die Schritte als Checkliste enthalten
- Auf Patterns im bestehenden Code verweisen
- Hinweise enthalten was dabei NICHT gemacht werden soll

Nutze den Claude Code Guide Sub-Agent.
```

Als Vorlage, wie eine fertige `SKILL.md` aussieht, dient 
`07_beispiel_skill_neues_feld.md`.

**Merke:** Injiziertes Wissen für Standard-Workflows. Skills 
machen Wiederholung produktiv und konsistent.
