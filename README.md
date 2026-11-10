# keylime-models

The Keylime models (a preview) now live on Hugging Face, one repo per model:

| model | repo |
|---|---|
| m2 style (106M Block AttnRes decoder LM, 32k vocab, casual / standard / formal style tokens), int4, default | [MostLime/keylime-m2-preview](https://huggingface.co/MostLime/keylime-m2-preview) |
| m1 (34M Block AttnRes decoder LM, 16k vocab), int8, battery saver | [MostLime/keylime-m1-preview](https://huggingface.co/MostLime/keylime-m1-preview) |

Each repo has the step graph and the tree step graph in pre-optimized onnxruntime (ORT) format, the SentencePiece
vocab, and a model card with sizes and SHA-256s. The apps download them on first run (Nest mirror as the fallback) and
check each file against the SHA-256 in `manifest.json`.

This repo keeps:

- `manifest.json` in the [`models-v1`](../../releases/tag/models-v1) release: the apps' fallback manifest URL (the
  primary copy is on Nest). It lists each model's files, its mirrors (`base_urls`), step-graph layout and decode
  parameters.
- the `app-v*` (Android APK) and `mac-v*` (Mac zip) releases the in-app updaters download.

The model files that used to be release assets here have moved to Hugging Face.

## License

Copyright © Mostlime12195. The model files are licensed under
[Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE).
