# Nova — Sonic AI

Nova is a browser-based AI workspace. Sonic runs an open-weight language model locally in the browser through WebLLM and WebGPU; it does not call an AI inference API.

## Publish the website with GitHub Pages

Nova's complete website is in `index.html` at the root of the `main` branch.

In the repository, open **Settings → Pages** and choose:

1. **Source:** Deploy from a branch
2. **Branch:** `main`
3. **Folder:** `/(root)`
4. Press **Save**

GitHub will then publish this repository at:

https://superninja7667-byte.github.io/Nova-AI/

This repository uses branch publishing instead of a GitHub Actions deployment workflow. That avoids the earlier `configure-pages` error when the repository's Pages site has not been created yet.

## Sonic local AI requirements

- A secure HTTPS website (GitHub Pages provides HTTPS).
- Browser support for WebGPU.
- Internet access for the first download of the local model and runtime.
- Sufficient device GPU memory.

After the model is downloaded, inference runs on the user's device. Device capability varies; Nova checks WebGPU before trying to load the model. Model weights are downloaded by WebLLM when the selected model is initialized.

## Installable web app

Nova includes a web app manifest and a small service worker for caching the app shell. The service worker does not cache large model weights; WebLLM manages model caching in browser storage.

## Development

Edit `index.html` and push changes to `main`. GitHub Pages will publish changes from the root of the branch.
