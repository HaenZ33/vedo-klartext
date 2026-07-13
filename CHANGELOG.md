# Changelog – VEDO KLARTEXT

Alle Änderungen an der Firmware für das ESP32-P4 Kombiinstrument.
Die aktuell installierte Version steht im Boot-Screen und unten im Menü.

---

## v1.1 (Beta) – 13.07.2026

Großes Funktions-Update gegenüber der ersten Version vom April.
Neu sind vor allem das Bedien-Menü, die Uhr, GPS/SD-Logging und
deutlich mehr Sensorik.

### Neu

**Bedien-Menü**
- Komplettes Menü, bedienbar über den Dreh-Encoder
- Untermenüs für Sensorik, Anzeige und Einstellungen
- Unten wird immer die laufende Version eingeblendet

**Uhr / Standby**
- Uhren-Screen mit großer 7-Segment-Anzeige
- Dient als Standby-Anzeige; Rückkehr per Joystick/Encoder
- Zeitzone über UTC-Offset im Menü einstellbar

**GPS und Datenaufzeichnung**
- GNSS-Empfang (Position, Geschwindigkeit, Uhrzeit)
- SD-Karten-Unterstützung
- Datenlogger schreibt Messwerte auf die SD-Karte
- GPS-Track-Aufzeichnung

**Mehr Sensorik**
- Öl: Öldruck-Sensor, zwei Öldruck-Schalter (0,3 bar und 0,9 bar)
  und Öltemperatur – inklusive überarbeiteter Warnschwellen
- Außentemperatur über DS18B20 (1-Wire-Fühler)
- Chip-Temperatur des ESP32-P4

**Diagnose**
- Debug-Screen mit CPU-Auslastung und Task-Übersicht
- Status-LED signalisiert den Systemzustand

### Verbessert

- **Drehzahl deutlich stabiler:** Neuer Glitch-Filter (Auswertung der
  fallenden Flanke, Plausibilitätsprüfung gegen den Vorwert). Zappelnde
  oder ausreißende Drehzahlwerte sollten damit der Vergangenheit angehören.
- Encoder-Drehrichtung korrigiert und Menüführung neu strukturiert
- Zweiter Screen überarbeitet
- Anzeige-Refresh entzerrt (Race-Condition beim Neuzeichnen behoben)

### Hinweise

- Die Firmware-Datei heißt jetzt `vedo_klartext_v1.1.bin`
  (vorher `p4_instrument_cluster.bin`). Die Flash-Adressen sind
  unverändert – siehe [README.md](README.md).
- Nach dem Flashen im Boot-Screen prüfen, ob dort **v1.1** steht.
- Status: **Beta.** Nicht alle Sensor-Kombinationen sind im Fahrbetrieb
  langzeiterprobt.

---

## v1.0 – 07.04.2026

- Erste veröffentlichte Version
- Grundlegende Instrumenten-Anzeige auf dem 720x720-Display
- Basis-Sensorik
