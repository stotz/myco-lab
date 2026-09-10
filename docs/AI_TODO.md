# AI TODO

[README.md](../README.md)
[AI_Instruktion.md](AI_Instruktion.md)

---

## Aktueller Stand (v0001)

Projektstruktur angelegt. Alle in der Planungsphase erarbeiteten Standards sind
als Protokolle dokumentiert. Noch keine Messdaten; Laborbetrieb hat nicht begonnen.

Infrastruktur (beschafft oder bestellt):

- Flow Hood (erhalten), Presto 01781, AME24 Wasserbad-Autoklav
- Inkubator: Kibernetik KS240L + Inkbird ITC-308 (Sollwert 23 °C)
- Gläser: UNiTWIST Runda 1053/1035 (Substrat), Runda 390 TO70 (LC)
- 6x IRIS 20 L Monotubs, PE-LD-Stopfen 23.5/25, Milbenstopfen 28x25
- LC-Deckel-Bauteile: PP-Luer-Paneelanschluss 4.0 mm, VMQ O-Ringe CS1.5,
  PTFE-Spritzenfilter 25 mm 0.22 um hydrophob, Silikon-Vialstopfen 20 mm
- Archiv: 100x 15-ml-PP-Röhrchen (122 °C / -80 °C), Edelstahl-Rack 40x19 mm
- Sensorik: 4x SwitchBot IP65 + Hub Mini
- 20x PP-Container 6.6x2.5 cm als Arbeits-Plattenformat (PP-Verifikation offen)

## Aktuelle Arbeit

v0001: Grundgerüst

- Verzeichnisstruktur: docs/, protocols/, lineage/, runs/, climate/
- 7 Protokolle aus der Planungsphase übertragen
- CSV-Schemas definiert (cultures, events, boxes)
- AI_Instruktion als myco-lab-Fassung erstellt (Freigabe durch Betreiber offen)
- README mit Documents-Index, Titel-Tippfehler (nyco) korrigiert

## TODO

- Betreiber: AI_Instruktion.md prüfen und freigeben
- Wareneingangstests: PTFE-Filter (Tropfentest), Silikonstopfen (Dehnung, Kreuz),
  PP-Container (Presto-Einzeltest), Röhrchen (Presto-Probelauf)
- AME24-Kalttest: 8er-Ringpackung Runda 1053, beide Lagen
- KS240L: Innenmasse nachmessen, 48-h-Logger-Testlauf
- Erste Platten aus Alt-Spritzen (MYA), danach lineage/cultures.csv beginnen
- SwitchBot-Sensoren nach Code-System benennen, ersten CSV-Export ablegen

## History

| Version | Aenderungen |
|---------|------------|
| v0001 | Initiale Projektstruktur, Protokolle, CSV-Schemas, AI_Instruktion (Entwurf) |

## Beschreibung

Dieser letzte Abschnitt (Beschreibung) **darf nicht durch die AI bearbeitet werden.**
Diese Datei ist die technische Arbeits- und Entscheidungshistorie.
Sie wird eigenständig durch die AI-Versionierung verwaltet.
Die AI hält sich dabei strikt an den Workflow gemäss docs/AI_Instruktion.md.
Sie wird so geführt, dass ein neuer AI-Chat ohne Informationsverlust weiterarbeiten kann.

---

[README.md](../README.md)
