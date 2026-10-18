# Yomitori – Daten

Wörterbuch und Modelle für [Yomitori](https://github.com/EpoX04/Yomitori), die die App beim ersten
Start herunterlädt (Einstellungen → Einrichtung). Die Dateien liegen in den
[Releases](../../releases); `manifest.json` nennt für jede Datei Ziel, Größe und SHA-256.

Dieses Repository enthält nur weitergegebene Daten Dritter. Sie stehen unter den Lizenzen ihrer
Urheber, nicht unter der MIT-Lizenz von Yomitori.

## Wörterbuch (`dict.sqlite.gz`)

Eine SQLite-Datenbank, gebaut mit `pnpm dict:build` aus:

| Quelle | Lizenz |
|---|---|
| [JMdict](https://www.edrdg.org/jmdict/j_jmdict.html), [KANJIDIC2](https://www.edrdg.org/wiki/index.php/KANJIDIC_Project), [JMnedict](https://www.edrdg.org/enamdict/enamdict_doc.html), KRADFILE – © Electronic Dictionary Research and Development Group | [CC BY-SA 4.0](https://www.edrdg.org/edrdg/licence.html) |
| [Jitendex](https://jitendex.org) – © Stephen Kraus | CC BY-SA 4.0 |
| [Jiten-Häufigkeitsliste](https://jiten.moe/frequency-dictionaries) – Sirus (jiten.moe) | CC BY-SA 4.0 |
| [Kanjium](https://github.com/mifunetoshiro/kanjium) (Tonhöhenakzent) – Uros O. (mifunetoshiro) | CC BY-SA 4.0 |
| [Tatoeba](https://tatoeba.org) (Beispielsätze) – © die jeweiligen Autoren | CC BY 2.0 FR |

Die Datenbank als Ganzes wird als abgeleitetes Werk unter **CC BY-SA 4.0** weitergegeben; die
enthaltenen Tatoeba-Sätze bleiben CC BY 2.0 FR.

**Tatoeba-Autoren:** Jeder Satz behält in der Tabelle `examples` seine Tatoeba-ID (`id`). Autor und
Lizenz des einzelnen Satzes stehen unter `https://tatoeba.org/sentences/show/<id>`. Yomitori
verlinkt jeden angezeigten Beispielsatz dorthin.

**Aktualität:** Die EDRDG-Lizenz verlangt, die Daten regelmäßig zu aktualisieren. Ein fester Takt
für neue Releases und die Aktualisierung in der App sind in Arbeit
([Yomitori#99](https://github.com/EpoX04/Yomitori/issues/99)). Stand dieses Releases: JMdict und
Jitendex vom Oktober 2026.

## Modelle (ONNX)

| Dateien | Herkunft | Lizenz |
|---|---|---|
| `manga-ocr__*` | [kha-white/manga-ocr-base](https://huggingface.co/kha-white/manga-ocr-base), ONNX-Export [onnx-community/manga-ocr-base-ONNX](https://huggingface.co/onnx-community/manga-ocr-base-ONNX) | Apache-2.0 |
| `paddle__*` | PaddleOCR PP-OCRv6 (Erkennung), ONNX von [RapidOCR](https://www.modelscope.cn/models/RapidAI/RapidOCR) | Apache-2.0 |
| `detector__detector-v4-s_int8.onnx`, `detector__config.json`, `detector__preprocessor_config.json` | [ogkalu/comic-text-and-bubble-detector](https://huggingface.co/ogkalu/comic-text-and-bubble-detector) | Apache-2.0 |
| `detector__PP-OCRv6_det_small.onnx` | PaddleOCR PP-OCRv6 (Detektion), ONNX von RapidOCR | Apache-2.0 |

Die Modelle sind unverändert weitergegeben (nur umbenannt: `ordner__datei`).

## Änderungen

- **Wörterbuch:** Die Quelldateien wurden mit `pnpm dict:build` (siehe Yomitori, `packages/dict`)
  in eine SQLite-Datenbank umgewandelt: Einträge, Lesungen, Bedeutungen (Englisch, Deutsch),
  Kanji-Angaben, Namen, Häufigkeiten und Tonhöhenakzente wurden ausgewählt und neu
  strukturiert; Tatoeba-Sätze wurden auf Sätze mit englischer oder deutscher Übersetzung
  beschränkt und den Wörterbucheinträgen zugeordnet (höchstens 30 je Eintrag). Inhalte
  wurden nicht umformuliert.
- **Modelle:** unverändert; nur die Dateinamen tragen den Zielordner als Präfix.

## Lizenztexte

- Apache License 2.0: [`LICENSES/Apache-2.0.txt`](LICENSES/Apache-2.0.txt) (liegt auch dem Release bei)
- CC BY-SA 4.0: https://creativecommons.org/licenses/by-sa/4.0/legalcode
- CC BY 2.0 FR: https://creativecommons.org/licenses/by/2.0/fr/legalcode
- EDRDG-Lizenzerklärung: https://www.edrdg.org/edrdg/licence.html

Die Daten werden ohne Gewähr weitergegeben. Rechte und Urheberschaft bleiben bei den genannten
Projekten.
