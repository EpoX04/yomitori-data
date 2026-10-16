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
| [Jitendex](https://jitendex.org) | CC BY-SA 4.0 |
| [Jiten-Häufigkeitsliste](https://jiten.moe/frequency-dictionaries) | CC BY-SA 4.0 |
| [Kanjium](https://github.com/mifunetoshiro/kanjium) (Tonhöhenakzent) | CC BY-SA 4.0 |
| [Tatoeba](https://tatoeba.org) (Beispielsätze) | CC BY 2.0 FR |

Die Datenbank als Ganzes wird als abgeleitetes Werk unter **CC BY-SA 4.0** weitergegeben; die
enthaltenen Tatoeba-Sätze bleiben CC BY 2.0 FR.

## Modelle (ONNX)

| Dateien | Herkunft | Lizenz |
|---|---|---|
| `manga-ocr__*` | [kha-white/manga-ocr-base](https://huggingface.co/kha-white/manga-ocr-base), ONNX-Export [onnx-community/manga-ocr-base-ONNX](https://huggingface.co/onnx-community/manga-ocr-base-ONNX) | Apache-2.0 |
| `paddle__*` | PaddleOCR PP-OCRv6 (Erkennung), ONNX von [RapidOCR](https://www.modelscope.cn/models/RapidAI/RapidOCR) | Apache-2.0 |
| `detector__detector-v4-s_int8.onnx`, `detector__config.json`, `detector__preprocessor_config.json` | [ogkalu/comic-text-and-bubble-detector](https://huggingface.co/ogkalu/comic-text-and-bubble-detector) | Apache-2.0 |
| `detector__PP-OCRv6_det_small.onnx` | PaddleOCR PP-OCRv6 (Detektion), ONNX von RapidOCR | Apache-2.0 |

Die Modelle sind unverändert weitergegeben (nur umbenannt: `ordner__datei`).
