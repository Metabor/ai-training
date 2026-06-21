# Fachliche Spezifikation: Sammlungs-Verwaltung

## Zweck dieser Spezifikation

Diese Spezifikation beschreibt eine generische Anwendung zur Verwaltung 
einer Sammlung. Sie ist bewusst technologie-offen formuliert. Die 
konkrete Umsetzung – Programmiersprache, Framework, Persistenz, UI – 
entscheidet der Umsetzende selbst.

Mögliche Einsatzszenarien:
- Als Einstieg in eine neue Technologie oder Sprache
- Als Spielwiese um einen neuen Stack auszuprobieren
- Als Basis für eine persönlich motivierte Anwendung 
  (Buchsammlung, Plattensammlung, Rezeptsammlung, Weinvorrat, 
  Werkzeug-Inventar, Filmliste, Gaming-Backlog, etc.)

---

## Teil 1: Basis-Funktionalität (für alle gleich)

Die folgenden Features bilden das Grundgerüst. Alles weitere baut 
darauf auf.

### 1.1 Datenmodell

Ein "Eintrag" in der Sammlung hat mindestens folgende Eigenschaften:

- **ID**: eindeutige Kennung, automatisch vergeben
- **Titel**: Kurzer Name oder Bezeichnung (Pflichtfeld)
- **Beschreibung**: Längerer Freitext (optional)
- **Erstelldatum**: Wann der Eintrag angelegt wurde 
  (automatisch gesetzt)

### 1.2 Basis-Operationen

Die Anwendung muss folgende Operationen unterstützen:

**Eintrag anlegen**
- Neuer Eintrag mit Titel und optionaler Beschreibung
- ID und Erstelldatum werden automatisch vergeben

**Einträge auflisten**
- Alle Einträge der Sammlung werden angezeigt
- Sortierung: neueste zuerst (Default)

**Eintrag ansehen**
- Alle Details eines einzelnen Eintrags werden angezeigt

**Eintrag bearbeiten**
- Titel und Beschreibung können geändert werden
- ID und Erstelldatum bleiben unverändert

**Eintrag löschen**
- Ein Eintrag kann aus der Sammlung entfernt werden
- Sicherheitsabfrage vor dem endgültigen Löschen

### 1.3 Suche

Einträge können über ihren Titel gesucht werden. Die Suche ist 
nicht case-sensitive und findet Teil-Treffer.

### 1.4 Persistenz

Die Sammlung muss gespeichert werden, sodass Einträge zwischen 
Anwendungsstarts erhalten bleiben. Die Art der Persistenz ist 
frei wählbar: Datei (JSON, CSV, SQLite), Datenbank, Browser 
Storage, Cloud – was immer passt.

### 1.5 Benutzungsschnittstelle

Die Art der Bedienung ist frei wählbar: CLI, TUI, Web-App, 
Desktop-App, Mobile-App. Wichtig ist nur, dass alle Basis-
Operationen zugänglich sind.

---

## Teil 2: Anpassung an den eigenen Anwendungsfall

Nach der Basis wird das Datenmodell um Felder erweitert, die zum 
eigenen Anwendungsfall passen. Beispiele:

- **Buchsammlung**: Autor, ISBN, Seitenzahl, gelesen ja/nein
- **Plattensammlung**: Künstler, Album, Jahr, Genre
- **Weinkeller**: Jahrgang, Region, Rebsorte, Trinkreife
- **Gaming-Backlog**: Plattform, Spielzeit, Status 
  (wartet/spielt/durch/abgebrochen)
- **Rezeptsammlung**: Zutaten, Zubereitungszeit, Schwierigkeit
- **Werkzeug-Inventar**: Standort, Zustand, letzte Wartung

Mindestens 2 eigene Felder ergänzen, passend zum gewählten 
Anwendungsfall.

---

## Teil 3: Feature-Katalog zur freien Auswahl

Aus den folgenden Features mindestens 2 auswählen und umsetzen. 
Die Auswahl sollte zum gewählten Anwendungsfall passen.

### Kategorisierung
- **Tags oder Kategorien**: Einträge können mit Schlagworten 
  versehen werden. Filterung nach Tag möglich.
- **Mehrere Sammlungen**: Parallele Sammlungen nebeneinander 
  (z.B. "Bücher" und "Hörbücher")

### Bewertung und Status
- **Bewertung**: Sterne (1-5), Punkte (1-100), oder eigene Skala
- **Status**: Zustand oder Fortschritt (z.B. "geplant", 
  "in Bearbeitung", "abgeschlossen")
- **Favoriten**: Markierung als Favorit, eigene Ansicht

### Zeitbezug
- **Datumsfelder**: Zusätzliche Daten wie "erworben am", 
  "zuletzt genutzt", "fällig bis"
- **Erinnerungen**: Warnung wenn Datum erreicht oder überschritten
- **History**: Änderungsprotokoll pro Eintrag

### Anhänge und Medien
- **Bilder**: Ein Bild pro Eintrag (Cover, Foto, Screenshot)
- **Dateien**: Beliebige Anhänge
- **Links**: Externe URLs mit Vorschau

### Verwaltung und Analyse
- **Statistiken**: Anzahl pro Kategorie, Durchschnittsbewertung, 
  Entwicklung über Zeit
- **Export**: Sammlung als CSV oder JSON speichern
- **Import**: Einträge aus CSV oder JSON einlesen
- **Duplikat-Erkennung**: Warnung bei ähnlichen Einträgen

### Erweiterte Struktur
- **Verknüpfungen**: Einträge können andere Einträge referenzieren
- **Hierarchie**: Einträge können Unter-Einträge haben
- **Notizen-Feld**: Markdown-fähiges Freitextfeld pro Eintrag

---

## Teil 4: Nicht-funktionale Anforderungen

### Verständlichkeit
Der Code muss lesbar sein. Funktionen und Variablen haben 
sprechende Namen.

### Robustheit
Die Anwendung stürzt nicht ab bei ungültigen Eingaben. 
Fehler werden dem Benutzer verständlich gemeldet.

### Wartbarkeit
Änderungen am Datenmodell oder am Verhalten sollen nicht die 
gesamte Anwendung erfordern. Eine sinnvolle Trennung von 
Datenhaltung, Logik und Darstellung wird empfohlen.

### Persistenz-Sicherheit
Daten dürfen bei normalen Operationen nicht verloren gehen. 
Ein Absturz während des Speicherns darf nicht zu korrupten 
Daten führen.

---

## Empfohlenes Vorgehen

1. Plan Mode in Claude Code aktivieren
2. Spezifikation gemeinsam mit dem Agent durchgehen
3. Technologie-Entscheidungen treffen und dokumentieren 
   (Sprache, Framework, Persistenz, UI)
4. Anwendungsfall wählen (Buchsammlung, Weinkeller, etc.)
5. Basis-Funktionalität planen und umsetzen
6. Eigene Felder ergänzen
7. Features aus dem Katalog auswählen und umsetzen
8. Am Ende das Ergebnis kurz vorstellen

Tipp: Die Spezifikation liest sich in jeder Sprache gleich. 
Wer Python will baut Python, wer Rust ausprobieren möchte baut 
Rust, wer nur einen Browser hat baut HTML/JS. Das Ergebnis ist 
immer eine Sammlungs-Verwaltung – aber die Umsetzung kann völlig 
unterschiedlich aussehen.

---

## Teil 5: Workshop-Leitfaden (Schritt für Schritt)

Dieser Leitfaden führt durch die Umsetzung und integriert dabei 
die Claude Code Konzepte aus der Schulung (CLAUDE.md, Rules Files, 
Skills, Sub-Agents, Plan Mode, Orchestrierung). Jeder Schritt 
baut auf dem vorherigen auf.

### Schritt 1: Setup und Planung (Plan Mode)

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

Plan durchgehen, bei Bedarf anpassen, bestätigen.

**Lernmoment:** Plan + Bestätigung. Der Agent fragt nach, 
bevor er implementiert. Bei komplexen Aufgaben immer erst 
planen lassen.

### Schritt 2: CLAUDE.md anlegen

Bevor die Implementierung startet, den Agent bitten, das 
bisher Besprochene festzuhalten.

**Prompt:**
```
Bevor wir mit der Implementierung starten, erstelle bitte eine 
CLAUDE.md im Projekt-Root mit:
- Dem gewählten Anwendungsfall
- Den Technologie-Entscheidungen
- Der gewählten Architektur (Trennung von Daten/Logik/UI)
- Naming Conventions die wir etablieren wollen
- Was der Agent NICHT tun soll (z.B. "keine Dependencies ohne 
  Rückfrage hinzufügen", "keine Änderungen am Datenmodell ohne 
  Migration")
```

**Lernmoment:** Kontext festhalten. Die CLAUDE.md ist das 
Onboarding-Dokument für jeden neuen Chat.

### Schritt 3: Basis implementieren

Aus dem Plan Mode heraus in den normalen Modus wechseln und 
die Basis umsetzen lassen.

**Prompt:**
```
Implementiere jetzt die Basis-Funktionalität gemäß dem Plan. 
Arbeite schrittweise und zeige mir nach jedem größeren Schritt 
den Zwischenstand, damit ich prüfen kann ob alles passt.
```

**Lernmoment:** First make it work, then make it beautiful. 
Erst funktionierende Basis, dann optimieren.

### Schritt 4: Rules File erstellen

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

**Lernmoment:** Dynamischer Kontext. Rules Files werden nur 
bei passenden Dateitypen geladen und sparen Tokens gegenüber 
einer überladenen CLAUDE.md.

### Schritt 5: Eigene Felder ergänzen (mit Review Sub-Agent)

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

**Lernmoment:** Confirmation Bias vermeiden. Der Primary-Agent 
übersieht eigene Fehler. Ein Sub-Agent mit frischem Kontext 
findet sie.

### Schritt 6: Erstes Feature aus dem Katalog

Ein Feature aus Teil 3 der Spezifikation auswählen und 
implementieren. Wieder mit Plan Mode starten.

**Prompt:**
```
Ich möchte jetzt das Feature "[Feature-Name]" hinzufügen.

Plan Mode: Erstelle einen Plan wie wir das Feature integrieren, 
unter Berücksichtigung der bestehenden Architektur und der 
Regeln in CLAUDE.md und im Rules File.
```

Plan bestätigen, implementieren lassen.

**Lernmoment:** Rules Files und CLAUDE.md werden bei jedem 
neuen Feature wieder relevant. Je besser der initiale Kontext, 
desto konsistenter bleibt der Code.

### Schritt 7: Skill erstellen für wiederkehrende Aufgaben

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

**Lernmoment:** Injiziertes Wissen für Standard-Workflows. 
Skills machen Wiederholung produktiv und konsistent.

### Schritt 8: Orchestrierung bei komplexem Feature

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

**Lernmoment:** Separation of Concerns. Jeder Agent hat seine 
Aufgabe, der Primary-Kontext bleibt schlank, Ergebnisse werden 
als kompakte Zusammenfassungen übergeben.

### Schritt 9: Reflexion und Continuous Improvement

Am Ende der Session.

**Prompt:**
```
Wir sind für heute fertig. Lass uns reflektieren:

1. Was lief gut?
2. Wo musste ich dich korrigieren?
3. Welche Regel fehlt in CLAUDE.md oder in den Rules Files, 
   die uns beim nächsten Mal helfen würde?
4. Aktualisiere CLAUDE.md und die Rules Files entsprechend.
```

**Lernmoment:** Continuous Improvement. Jede Session macht die 
Konfiguration besser. Der Fehler ist nicht das Problem – der 
Fehler ist die Chance.

### Schritt 10: Ergebnis vorstellen

Am Ende des Workshops zeigt jeder kurz:
- Welchen Anwendungsfall hat er gewählt
- Welche Technologie
- Welche Features hat er umgesetzt
- Was war der wichtigste Lernmoment
- Welche Skills / Sub-Agents / Rules Files sind entstanden

---

## Abkürzungen wenn die Zeit knapp wird

Wenn weniger Zeit zur Verfügung steht, können Schritte 
übersprungen werden – aber in dieser Priorität:

**Minimal (60 Min):**
Schritt 1, 2, 3 – Plan, CLAUDE.md, Basis

**Mittel (90 Min):**
Plus Schritt 4 und 6 – Rules File und erstes Feature

**Komplett (2-3 h):**
Alle Schritte inkl. Skill und Orchestrierung

Wichtig: Auch bei der Minimalversion sind Plan Mode, CLAUDE.md 
und die Basis die Fundamente. Alles andere baut darauf auf.
