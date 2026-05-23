# Protokoll-Analyse

Ergebnisse aus **Phase 0**: kanonische Referenz für das CN-CNT-Protokoll der Panasonic Aquarea. Abgeleitet aus dem HeishaMon-Code in [vendor/heishamon-upstream/](../../vendor/heishamon-upstream/) und gegen die dortige Doku abgeglichen.

## Inhalt

- [code-map.md](code-map.md) — welche Dateien im HeishaMon-Repo sind relevant, welche Funktionen erledigen was
- [crc.md](crc.md) — Checksum-Algorithmus (Zweierkomplement der Bytesumme), inkl. Testvektoren aus `Tools/chksumChecker.js`
- [frames.md](frames.md) — alle sechs Frame-Typen (Header-Bytes, Längen, Position der Checksum, ASCII-Layouts)
- [datapoints.md](datapoints.md) — **die große Tabelle**: 157 Datenpunkte (144 Haupt + 7 Optional-PCB + 6 Extra) mit Name, Byte-Offset, Decoder-Funktion, Einheit, Wertebereich und Schreibbarkeit
- [doc-vs-code-diff.md](doc-vs-code-diff.md) — Abgleich der HeishaMon-Doku gegen den Code, mit gefundenen Lücken und Action-Items

## Status

Phase 0 ist **abgeschlossen**. Die Inhalte hier sind die Single Source of Truth für Phase 1 (TS-Bibliothek).

## Offene Punkte für spätere Phasen

Aus [doc-vs-code-diff.md](doc-vs-code-diff.md):

- Spezialdecoder für die 7 "unknown"-Topics in Phase 1 clean-room nachimplementieren (TOP1, TOP11, TOP12, TOP44, TOP90, TOP91, TOP92)
- Initial-Handshake-Mechanik (`0x31 0x05 ...`) klären — sendet die WP eine Antwort? Muss der Simulator antworten?
- Verifizieren: schickt die WP auch auf Set-Commands eine 203-Byte-Antwort?
