# autocorrect-models

Model files for the Autocorrect Android keyboard. They're published as release assets: the current set is
[`models-style1`](../../releases/tag/models-style1) (the earlier [`models-v1`](../../releases/tag/models-v1) has the
pre-style models; its `manifest.json` is kept in sync with the newest one). The keyboard downloads them on first run and
checks each file against the SHA-256 in `manifest.json`.

| file | what it is |
|---|---|
| `manifest.json` | file list with sizes and SHA-256, step-graph layout, decode parameters per model |
| `m2s.step.int4m.ort` | m2 style (106M Block AttnRes decoder LM, 32k vocab, trained on 9B tokens with casual / standard / formal style tokens), int4 weights, pre-optimized onnxruntime format (default) |
| `m2s.step.int8.ort` | the same style model with int8 weights |
| `m2.step.int4m.ort` | m2 (106M, 3B tokens, no style tokens), int4 weights |
| `m2.step.int8.ort` | m2 with int8 weights |
| `lm_block4.step.int8.ort` | 34M Block AttnRes LM, int8 weights (battery saver) |
| `vocab_m2.json`, `vocab.json` | SentencePiece vocabularies for m2 / m2s and the 34M model |
| `lexicon.tsv` | 100k-word frequency lexicon used for candidate generation (known misspellings removed) |

Style tokens (m2s only): the context starts with `[EOS, id]`, where id is 249 for casual, 250 for standard and 251 for formal.

This repo has no code and no training data, only the exported weights and the vocab/lexicon files the keyboard needs.

## License

Copyright © Mostlime12195. The model files are licensed under
[Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE).
