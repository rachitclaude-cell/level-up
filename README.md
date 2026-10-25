# Level-Up website files

Everything in this folder is the website. Upload it as it is; no build step and no server code.

## Put it on GitHub Pages (free)

1. On GitHub, open your repository (or make a new one called `level-up`).
2. **Add file → Upload files.** Drag in everything from this folder: `index.html`, the `lang` folder, the `models` folder, the icons, `manifest.webmanifest` and `.nojekyll`. Every file is under 5 MB, so the web upload works.
3. Click **Commit changes.**
4. **Settings → Pages → Branch: main, folder: / (root) → Save.** The site appears at `https://<your-name>.github.io/level-up/` within about 10 minutes.

When you change the app later, run `tools/build-site.ps1` again and upload the changed files the same way.

## What works where

| | Inside Claude | On the website |
| --- | --- | --- |
| Plan, tracker, rewards, 5 languages | yes | yes |
| Camera form check | upload a video | **live camera** |
| Guided workout (voice) | yes | yes |
| Built-in coach (offline) | yes | yes |
| AI coach | Claude | **AI on the phone** (one-time download) |

## The AI coach on the phone

On the website, the Coach tab offers **Download the small coach (about 400 MB)** or the better one (about 1 GB). The phone downloads the model once from Hugging Face and keeps it; after that the AI works offline and nothing typed leaves the phone. It needs a recent Chrome and a phone with WebGPU; others get the built-in coach.

If Hugging Face is slow or blocked for your users, host the model yourself: put the model's files in `ai/<model id>/` next to `index.html` (for example `ai/Qwen2.5-0.5B-Instruct-q4f16_1-MLC/` with its `mlc-chat-config.json`, `tensor-cache.json`, `params_shard_*.bin` and tokenizer files from `https://huggingface.co/mlc-ai/<model id>/tree/main`). The app uses that copy automatically. Note: those shard files are 14–65 MB each, so they need GitHub Desktop or the `git` command rather than the web uploader.
