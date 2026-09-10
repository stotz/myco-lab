# AI Instruktion

[README.md](../README.md)
[AI_TODO.md](AI_TODO.md)

---

**Workflow zwischen AI und Betreiber für myco-lab**

Diese Anweisung gilt global für dieses Projekt und für alle zugehörigen Chats.
Sie ist die myco-lab-Fassung des Software-Workflows, angepasst an ein öffentliches Repository und an Laborbetrieb statt Softwareentwicklung.

Regel:
Triff nie automatische Annahmen.
Bei Unklarheiten oder Verbesserungsideen: immer explizit im Chat besprechen, bevor gehandelt wird.

```
project=myco-lab
repo=https://github.com/ursstotz/myco-lab
version=<version steht in docs/AI_TODO.md>
```

## Grundsatz

Das öffentliche Git-Repository ist die einzige gültige Quelle (Single Source of Truth).
Die AI kann das Repository direkt lesen (github.com, raw.githubusercontent.com).
Es gibt keine zweite Wahrheit, keine impliziten Annahmen und keine Rekonstruktionen.

Regel:
Die AI rekonstruiert niemals Dateiinhalte aus dem Gedächtnis.
Bei Unklarheit wird der aktuelle Stand aus dem Repo gelesen oder im Chat nachgefragt.

Zusatzregel:
docs/AI_Instruktion.md ist ein Vertrag und wird vom Betreiber gepflegt.
Die AI darf diese Datei nicht eigenmächtig ändern.
Änderungsvorschläge werden im Chat besprochen; der Betreiber committet.

## Session-Start

Zu Beginn einer Arbeitssession liest die AI direkt aus dem Repo (Branch master):

- README.md
- docs/AI_Instruktion.md und docs/AI_TODO.md
- die für die Aufgabe relevanten Protokolle und CSVs

Danach:

- Bestätigung des Standes in 5-10 Zeilen, inklusive gelesenem Commit-Bezug
- offene Fragen gesammelt und strukturiert im Chat
- keine Änderungsvorschläge vor bestätigtem Verständnis

Weicht der Repo-Stand von Aussagen im Chat ab, gilt das Repo; die AI fragt nach.

## Lieferung

Jede Lieferung der AI ist ein Download: ein vollständiges Projektarchiv.

Archivname exakt: `${project}_v${version}.tar.bz2`
Archiv-Inhalt: das komplette Projekt mit Pfad myco-lab/*.
Chat-Ausgabe exakt:

```
archive: ${project}_v${version}.tar.bz2
sha256:  <sha256checksum>
```

Zusätzlich liefert die AI die notwendigen Git-Befehle (git add, git rm, git mv),
wenn Dateien neu hinzukommen, entfernt oder umbenannt werden.
Dateien werden nur nach expliziter Absprache umbenannt oder gelöscht.

## Versionierung

Die Versionsnummer ist strikt vierstellig (0001, 0002, ...).
Sie kennzeichnet Arbeits-Steps zwischen AI und Betreiber und wird ausschliesslich von der AI vergeben.
Die Datenhistorie (Messwerte, Commits) läuft unabhängig davon über Git.
Jeder Step wird in docs/AI_TODO.md dokumentiert (Stand, Arbeit, TODO, History).

## Ausgabe-Regeln

Protokoll-Ausschnitte, CSV-Zeilen und Rezepte dürfen im Chat zur Diskussion gezeigt werden.
Vollständige Dateien werden ausschliesslich über das Projektarchiv geliefert.
Tabellen im Chat sind erlaubt, wenn sie der Klarheit dienen.

## Sprach- und Stilregeln

- Chat und alle Markdown-Dateien: Deutsch
- Schweizer Rechtschreibung: ss statt Eszett, deutsche Umlaute (ä, ö, ü) werden verwendet
- Fachbegriffe dürfen Englisch bleiben (Spawn, Flush, Leading Edge)
- Datumsformate immer ISO-8601: YYYY-MM-DD
- Zeilenenden immer LF, Encoding UTF-8
- Keine Emojis in CSVs und Datendateien; in Markdown nur sparsam

## Anti-Marketing-Regeln

Markdowns enthalten ausschliesslich Fakten, Entscheidungen, Begründungen,
Konsequenzen, TODOs, konkrete Werte und Arbeitsschritte.

Verboten: wertende Marketingbegriffe (robust, powerful, state-of-the-art, best, modern),
Floskelsätze, Zusammenfassungsfloskeln.

Kernregel Messwerte:
Erträge, Zeiten, BE-Werte und Klimadaten werden nur angegeben, wenn sie gemessen wurden
(Quelle: runs/, climate/). Literatur- und Community-Werte werden immer als solche markiert.
Geschätzte Werte sind als Schätzung zu kennzeichnen.

## Versuchs-Regeln

Labor-Äquivalent zu TDD: Versuchsdesign vor Durchführung.
Vor jedem Versuchszyklus stehen in decisions.md:

- Fragestellung und Stufen
- Replikate und Randomisierung
- Messgrössen
- Abbruchkriterien

Ereignisse werden mit Datum geloggt, nie als Dauern (runs/events.csv).
Ereignisdefinitionen stehen in protocols/events.md und werden nicht stillschweigend geändert.

Grundsatz für Optimierungen:
Änderungen, die Arbeitsschritte oder Risiken entfernen, werden bevorzugt geprüft.
Änderungen, die Komplexität hinzufügen, brauchen eine explizite Begründung
und werden zuerst als Einzeltest neben der Hauptlinie gefahren.
Pro Zyklus wird höchstens ein Parameter geändert.

## Dokumentationskonventionen

Ein neues Markdown wird nur erstellt, wenn ein Thema abgeschlossen und eigenständig ist.
Bestehende Markdowns werden erweitert, wenn es inhaltlich verwandte Ergänzungen sind.
Alle Markdowns werden im README.md unter `## Documents` verlinkt.
Jedes Markdown verlinkt oben und unten auf README.md.

## Dokumentation durch die AI

Die AI führt docs/AI_TODO.md auf Deutsch:
aktueller Stand, aktuelle Arbeit, offene TODOs, History pro Version.
Die Datei wird so geführt, dass ein neuer AI-Chat ohne Informationsverlust übernehmen kann.
Der Abschnitt Beschreibung am Ende der Datei darf von der AI nicht bearbeitet werden.

---

[README.md](../README.md)
