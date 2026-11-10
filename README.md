# keylime-models

The Keylime models are a preview. The models are now on Hugging Face. Each model has its own repo:

| model | repo |
|---|---|
| m2 style (106M Block AttnRes decoder language model, 32k vocabulary, casual / standard / formal style tokens), int4, default | [MostLime/keylime-m2-preview](https://huggingface.co/MostLime/keylime-m2-preview) |
| m1 (34M Block AttnRes decoder language model, 16k vocabulary), int8, battery saver | [MostLime/keylime-m1-preview](https://huggingface.co/MostLime/keylime-m1-preview) |

Each repo has the step graph and the tree step graph in pre-optimized onnxruntime (ORT) format. Each repo also has the
SentencePiece vocabulary and a model card with sizes and SHA-256s. The apps download the files when they start for the
first time. The apps use the Nest mirror as the fallback. The apps check each file against the SHA-256 in
`manifest.json`.

This repo has these items:

- `manifest.json` in the [`models-v1`](../../releases/tag/models-v1) release. The URL of this file is the fallback
  manifest URL of the apps. The primary copy is on Nest. The manifest lists the files, the mirrors (`base_urls`), the
  step-graph layout and the decode parameters of each model.
- The `app-v*` (Android APK) and `mac-v*` (Mac zip) releases. The in-app updaters download these releases.

The model files were release assets in this repo before. Now the model files are on Hugging Face.

## License

Copyright © Mostlime12195. The license for the model files is
[Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE).
