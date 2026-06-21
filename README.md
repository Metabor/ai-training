# AI-Training: Sammlungs-Verwaltung mit einer Coding-AI bauen

Ein Hands-on-Workshop. Jede:r baut mit einer Coding-AI – hier **Claude Code** –
eine kleine **Sammlungs-Verwaltung** in der bevorzugten Programmiersprache.
Was am Ende entsteht, ist immer eine Sammlungs-Verwaltung, aber die Umsetzung
darf völlig unterschiedlich aussehen: Python-CLI, Web-App, Rust, HTML/JS im
Browser – ganz nach Geschmack.

Der Workshop richtet sich an ein gemischtes Publikum (Entwicklung, QA, Doku,
PM). Programmier-Vorkenntnisse sind hilfreich, aber nicht zwingend – die AI
übernimmt das Tippen, du gibst die Richtung vor.

## Voraussetzungen

- Ein **Terminal** mit installiertem und authentifiziertem **Claude Code**.
- Ein **lokaler, leerer Projektordner**, in dem deine App entsteht.

> **Wichtig:** Der Agent (Claude Code) läuft **lokal im Terminal**. Die App,
> die du baust, darf später im Browser laufen – der Agent selbst nicht.

## Inhalt dieses Repos

Das Repo enthält das Workshop-Material – noch keinen Anwendungscode. Den baust
du selbst.

- **`spezifikation_sammlungs_verwaltung.md`** – die fachliche Aufgabe. Sie
  beschreibt, was die Sammlungs-Verwaltung können muss, und enthält einen
  Schritt-für-Schritt-Workshop-Leitfaden, der durch die wichtigsten
  Claude-Code-Konzepte führt (Plan Mode, CLAUDE.md, Rules Files, Skills,
  Sub-Agents, Orchestrierung).
- **`SKILL_neues_feld_hinzufuegen.md`** – ein Beispiel-Skill. Er zeigt, wie ein
  wiederverwendbarer Arbeitsablauf aussieht, und dient als **Vorlage** für
  eigene Skills.

## So legst du los

1. **Material holen.** Lade das Repo als ZIP herunter (auf GitHub:
   *Code → Download ZIP*) oder hole dir die beiden Markdown-Dateien einzeln.
2. **Eigenen Ordner anlegen** und Claude Code darin starten:
   ```bash
   mkdir meine-sammlung && cd meine-sammlung
   claude
   ```
3. **App bauen.** Gib Claude Code die Spezifikation und lass dir zuerst einen
   Plan erstellen (Plan Mode), bevor implementiert wird. Der Workshop-Leitfaden
   in der Spezifikation führt dich durch die einzelnen Schritte.
4. **Skill als Vorlage nutzen.** Wenn du einen wiederkehrenden Ablauf
   automatisieren willst, orientiere dich an `SKILL_neues_feld_hinzufuegen.md`.

## Technologie-offen

Die Spezifikation schreibt **keine** Technologie vor. Sprache, Framework, Art
der Speicherung und Benutzungsoberfläche entscheidest du selbst. Die Spec liest
sich in jeder Sprache gleich – wer Python will, baut Python; wer Rust
ausprobieren möchte, baut Rust; wer nur einen Browser hat, baut HTML/JS.

## Lizenz

Das Workshop-Material steht unter der [Creative Commons Attribution 4.0
International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
Details siehe [`LICENSE`](LICENSE).
