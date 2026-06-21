---
name: neues-feld-hinzufuegen
description: Use when the user wants to add a new field or property to an existing data model in the application. Triggers on phrases like "füge ein Feld hinzu", "neues Attribut", "erweitere das Modell", "add a field", "new property", "extend the model". Guides through the full workflow from model update to UI and persistence, followed by validation steps.
---

# Neues Feld zum Datenmodell hinzufügen

Dieser Skill führt durch den vollständigen Workflow beim Hinzufügen 
eines neuen Feldes. Er ist technologie-neutral und funktioniert 
unabhängig von der gewählten Sprache, dem Framework oder der Art 
der Persistenz.

## Schritte

### 1. Feld-Definition klären

Bevor etwas geändert wird, folgende Fragen mit dem Benutzer klären:

- Wie heißt das Feld?
- Welcher Datentyp (Text, Zahl, Datum, Boolean, Liste, Referenz)?
- Ist es Pflicht oder optional?
- Gibt es einen Standardwert?
- Gibt es Validierungsregeln (Bereich, Format, erlaubte Werte)?
- Wie verhalten sich bestehende Einträge, die dieses Feld noch 
  nicht haben?

### 2. Datenmodell erweitern

Das zentrale Datenmodell um das neue Feld ergänzen. Dabei die 
bestehenden Konventionen des Projekts beachten (Naming, Typ-Deklaration, 
Dokumentation).

### 3. Persistenz anpassen

Sicherstellen, dass das neue Feld gespeichert und gelesen wird. 
Je nach Persistenz-Art:
- Bei Datenbanken: Schema-Änderung / Migration
- Bei JSON/CSV-Dateien: Serialisierung anpassen
- Bei localStorage im Browser: Struktur beim Lesen/Schreiben 
  erweitern
- Bei Backend-APIs: Request/Response-Schemata anpassen

### 4. Abwärtskompatibilität sicherstellen

Bestehende Daten müssen weiterhin funktionieren. Das bedeutet:
- Beim Lesen: Fehlende Felder mit Standardwerten auffüllen
- Bei Datenbanken: Migration schreiben oder nullable setzen
- Bei Dateien: Alte Einträge beim ersten Laden migrieren
- Bei localStorage: Defensive Reads mit Fallback-Werten

### 5. Operationen erweitern

Alle Stellen anpassen, die das Modell nutzen:
- Anlegen: Neues Feld in der Erfassung berücksichtigen
- Anzeigen: Neues Feld in allen Ansichten darstellen
- Bearbeiten: Neues Feld editierbar machen
- Validierung: Regeln aus Schritt 1 umsetzen

### 6. UI anpassen

Die Benutzungsschnittstelle erweitern – unabhängig davon ob CLI, 
TUI, Web-UI, Desktop-App. Das neue Feld muss:
- Beim Erfassen eingebbar sein
- In Übersichten sichtbar oder bei Details verfügbar sein
- Beim Bearbeiten änderbar sein

### 7. Tests oder Validierungsschritte

Je nachdem ob im Projekt automatisierte Tests existieren, 
entweder Tests schreiben oder manuelle Validierungsschritte 
durchführen (siehe nächster Abschnitt).

### 8. Dokumentation aktualisieren

Wenn im Projekt eine Dokumentation der Datenstruktur existiert 
(README, CLAUDE.md, API-Doku), diese ergänzen.

## Validierung nach der Änderung

Die folgenden Schritte müssen nach dem Hinzufügen durchlaufen 
werden. Sie funktionieren in jeder Umgebung – auch im Browser 
mit localStorage.

### Validierung 1: Bestehende Daten funktionieren noch

Mit Daten arbeiten, die VOR der Änderung erstellt wurden:
- Anwendung starten / Seite neu laden
- Bestehende Einträge anzeigen
- **Erwartung:** Keine Fehler, alle Einträge werden dargestellt, 
  neues Feld zeigt Standardwert oder leer

### Validierung 2: Neuer Eintrag mit neuem Feld

Einen neuen Eintrag anlegen und das neue Feld setzen:
- Eintrag mit Wert für das neue Feld erstellen
- Eintrag speichern
- Anwendung neu starten / Seite neu laden
- Eintrag wieder öffnen
- **Erwartung:** Der Wert des neuen Feldes ist erhalten

### Validierung 3: Neuer Eintrag ohne neues Feld

Prüfen was passiert wenn das Feld nicht gesetzt wird:
- Neuen Eintrag anlegen und das neue Feld leer lassen 
  (falls optional) oder den Standardwert nutzen
- Eintrag speichern und neu laden
- **Erwartung:** Kein Absturz, Standardwert oder Leer-Wert 
  wird korrekt behandelt

### Validierung 4: Bestehenden Eintrag bearbeiten

Einen alten Eintrag nachträglich mit dem neuen Feld versorgen:
- Eintrag aus Validierung 1 öffnen
- Neues Feld setzen und speichern
- Anwendung neu starten / Seite neu laden
- **Erwartung:** Der gesetzte Wert ist erhalten

### Validierung 5: Grenzfälle

Die Validierungsregeln aus Schritt 1 testen:
- Ungültige Eingaben versuchen (falls es Regeln gibt)
- Extremwerte testen (leer, sehr lang, negativ, Sonderzeichen)
- **Erwartung:** Verständliche Fehlermeldung, kein Absturz, 
  keine korrupten Daten

### Validierung 6: Persistenz-Integrität

Nur wenn technisch zugänglich:
- Bei Dateien: Die Datei öffnen und prüfen ob das neue Feld 
  drin steht und alte Einträge korrekt sind
- Bei localStorage: In den DevTools den Storage öffnen und 
  die Struktur prüfen
- Bei Datenbanken: Direkt auf der DB prüfen ob Schema und 
  Daten stimmen
- **Erwartung:** Struktur ist wie erwartet, keine unerwarteten 
  Nebeneffekte

## Hinweise

- Nach jedem Schritt kurz prüfen ob die Anwendung noch startet 
  bzw. läuft. Kleine Schritte, frühe Fehler.
- Bei Browser-Anwendungen mit localStorage: Im Zweifel den 
  Storage zurücksetzen und frisch testen, aber dabei bewusst 
  sein dass das die Migration nicht testet.
- Vor größeren Änderungen an bestehenden Daten: Export oder 
  Backup machen, falls möglich.

## Was dieser Skill NICHT macht

- Dieser Skill schreibt keinen Code direkt. Er führt durch den 
  Prozess. Die tatsächliche Umsetzung passiert im Hauptkontext.
- Dieser Skill trifft keine Technologie-Entscheidungen. Er nutzt 
  was im Projekt etabliert ist.
- Dieser Skill ersetzt keine vorhandene Test-Suite. Wenn Tests 
  existieren, werden sie zusätzlich ausgeführt.
