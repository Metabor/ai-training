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
du selbst. Die Aufgabe ist in einzelne Dateien aufgeteilt, damit du jeden
Schritt **nacheinander** an Claude Code geben kannst.

### Referenz

- **`00_spezifikation.md`** – die fachliche Aufgabe (was die Sammlungs-Verwaltung
  können muss: Datenmodell, Operationen, eigene Felder, Feature-Katalog,
  nicht-funktionale Anforderungen). Das ist die Nachschlage-Datei; die
  Schritt-Dateien verweisen darauf.

### Die Schritte (nacheinander an Claude Code geben)

Jede dieser Dateien enthält einen fertigen **Prompt** plus einen kurzen
**Merke:**-Hinweis. Reihenfolge von oben nach unten:

- **`01_setup_und_planung.md`** – Claude Code starten, Plan Mode aktivieren,
  Anwendungsfall und Technologie wählen, einen Plan erstellen lassen.
- **`02_claude_md_anlegen.md`** – eine `CLAUDE.md` für dein Projekt anlegen, die
  die getroffenen Entscheidungen festhält.
- **`03_basis_implementieren.md`** – die Basis-Funktionalität umsetzen lassen.
- **`04_rules_file_erstellen.md`** – aus dem etablierten Code-Stil ein Rules File
  ableiten.
- **`05_eigene_felder_ergaenzen.md`** – das Datenmodell um eigene Felder
  erweitern und von einem Review-Sub-Agent prüfen lassen.
- **`06_erstes_feature.md`** – das erste Feature aus dem Katalog einbauen.
- **`07_skill_erstellen.md`** – aus einem wiederkehrenden Ablauf einen eigenen
  Skill erstellen.
- **`07_beispiel_skill_neues_feld.md`** – ein fertiger Beispiel-Skill als
  **Vorlage**, wie eine `SKILL.md` aufgebaut ist. Gehört zu Schritt 7.
- **`08_orchestrierung.md`** – ein komplexeres Feature mit mehreren Sub-Agents
  strukturiert umsetzen.
- **`09_reflexion.md`** – am Ende reflektieren und die Konfiguration verbessern.

## So legst du los

1. **Material holen.** Lade das Repo als ZIP herunter (auf GitHub:
   *Code → Download ZIP*) oder hole dir die Markdown-Dateien einzeln.
2. **Eigenen Ordner anlegen** und Claude Code darin starten:
   ```bash
   mkdir meine-sammlung && cd meine-sammlung
   claude
   ```
3. **Schritt für Schritt arbeiten.** Beginne mit `01_setup_und_planung.md` und
   gib die Schritte der Reihe nach an Claude Code. Wo ein Schritt „Teil 1/2/3
   der Spezifikation" erwähnt, schlägst du in `00_spezifikation.md` nach.
4. **Skill als Vorlage nutzen.** In Schritt 7 dient
   `07_beispiel_skill_neues_feld.md` als Muster für deinen eigenen Skill.

## Technologie-offen

Die Spezifikation schreibt **keine** Technologie vor. Sprache, Framework, Art
der Speicherung und Benutzungsoberfläche entscheidest du selbst. Die Spec liest
sich in jeder Sprache gleich – wer Python will, baut Python; wer Rust
ausprobieren möchte, baut Rust; wer nur einen Browser hat, baut HTML/JS.

## Lizenz

Das Workshop-Material steht unter der [Creative Commons Attribution 4.0
International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
Details siehe [`LICENSE`](LICENSE).
