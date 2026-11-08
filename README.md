# autocorrect-models

Model files for the Autocorrect Android keyboard. They're published as release assets of
[`models-v1`](../../releases/tag/models-v1). The keyboard downloads them on first run and checks each file against the
SHA-256 in `manifest.json`.

| file | what it is |
|---|---|
| `manifest.json` | file list with sizes and SHA-256, step-graph layout, decode parameters per model |
| `m2.step.int4m.ort` | m2 (106M Block AttnRes decoder LM, 32k vocab), int4 weights, pre-optimized onnxruntime format (default) |
| `m2.step.int8.ort` | the same model with int8 weights |
| `lm_block4.step.int8.ort` | 34M Block AttnRes LM, int8 weights (battery saver) |
| `vocab_m2.json`, `vocab.json` | SentencePiece vocabularies for m2 / the 34M model |
| `lexicon.tsv` | 100k-word frequency lexicon used for candidate generation (known misspellings removed) |

This repo has no code and no training data, only the exported weights and the vocab/lexicon files the keyboard needs.

## License

Copyright © Mostlime12195. You may download and use these files with the Autocorrect keyboard. No other license is
granted yet.
