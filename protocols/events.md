# Ereignisdefinitionen (runs/events.csv)

[README.md](../README.md)

---

Grundregel: Ereignisse werden mit Datum geloggt, nie als Dauern.
Dauern rechnet die Auswertung aus Datumsdifferenzen. Einträge entstehen
am Objekt (Folienstift, Datum im Moment des Ereignisses); Übertrag ins
CSV gesammelt einmal pro Woche.

Schema: `id,event,date,note`

- id: Objekt-Code nach Code-System (siehe unten)
- event: einer der definierten Ereignistypen
- date: ISO-8601 (YYYY-MM-DD)
- note: optional; bei flush_harvest das Frischgewicht in Gramm

## Ereignistypen

| event | Definition |
|-------|------------|
| plated | Platte gegossen und beimpft |
| transferred | Keil/Sektor auf neue Platte übertragen |
| colonized_plate | Front erreicht Plattenrand |
| banked | Slants/Glycerin aus dieser Kultur angelegt |
| lc_inoculated | LC-Glas beimpft |
| lc_harvested | Spritzenzug komplett (note: Anzahl Spritzen) |
| inoculated | Kornbeutel beimpft (Keil oder LC) |
| shaken | Beutel geschüttelt |
| colonized | Beutel zu 100 % besiedelt |
| spawned | Box angelegt (Spawn + Substrat gemischt) |
| colonized_box | Substratoberfläche zu 100 % weiss |
| consolidated | Oberfläche geschlossen und verdichtet |
| plugs_swapped | PE-Stopfen gegen Milbenstopfen getauscht |
| pins | erste Pins sichtbar |
| flush_harvest | Flush geerntet (note: Gramm frisch, z. B. 412g) |
| dunked | Box gedunkt |
| aborted | Box abgebrochen (note: Grund, z. B. konti_f2, ertrag) |
| refreshed | Bank-Slant auf frische Platte reaktiviert |

Definitionen werden nicht stillschweigend geändert; Änderung = Eintrag
in decisions.md, sonst sind Zyklen nicht vergleichbar.

## Code-System

`Linie-TypGeneration-Datum[.Nr]`

- Linie: A, B, C ... (Zuordnung im Kopf von lineage/cultures.csv)
- Typ: P Platte, S Slant, L Liquid Culture, K Kornbeutel, M Monotub
- Generation: Passagen seit Ursprung; wandert mit
  (Korn aus P2 ist K2, LC aus P2 ist L3-Logik: LC zählt als Passage)
- Datum: MMTT; Slants mit Jahr (JJMMTT)
- Laufende Nummer bei mehreren gleichen Objekten am selben Tag: .1, .2

Beispiele:

```
A-P1-0910      Linie A, Erstplatte
A-P2-0921      Transfer davon
A-S2-260921    Slant von dieser Platte (Archiv)
A-K2-0928.1    Kornbeutel 1, beimpft von P2
M-A1           Monotub, Kurzform fuer Boxen (Linie-Boxnummer)
SUB-260915.3   Substratglas 3 vom 15.09.2026
```

Beschriftung: Platten auf den Boden, Beutel vor dem Autoklavieren,
Gläser auf den Deckel, Boxen auf die Stirnseite.

---

[README.md](../README.md)
