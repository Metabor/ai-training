# Fachliche Spezifikation: Sammlungs-Verwaltung

## Zweck dieser Spezifikation

Diese Spezifikation beschreibt eine generische Anwendung zur Verwaltung 
einer Sammlung. Sie ist bewusst technologie-offen formuliert. Die 
konkrete Umsetzung – Programmiersprache, Framework, Persistenz, UI – 
entscheidest du selbst.

Mögliche Einsatzszenarien:
- Als Einstieg in eine neue Technologie oder Sprache
- Als Spielwiese um einen neuen Stack auszuprobieren
- Als Basis für eine persönlich motivierte Anwendung 
  (Buchsammlung, Plattensammlung, Rezeptsammlung, Weinvorrat, 
  Werkzeug-Inventar, Filmliste, Gaming-Backlog, etc.)

Diese Datei ist die **Referenz**. Die Schritt-Dateien (`01_…` bis `09_…`)
verweisen darauf – wenn ein Schritt „Inhalt von Teil 1 einfügen" sagt, ist
der entsprechende Abschnitt aus dieser Datei gemeint.

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

Die einzelnen Schritte der Umsetzung findest du in den Dateien 
`01_…` bis `09_…`. Gib sie nacheinander an Claude Code.
