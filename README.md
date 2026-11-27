# Nova — Sonic AI

Nova is a browser-based AI workspace. Sonic runs an open-weight language model locally in the browser through WebLLM and WebGPU; it does not call an AI inference API.

## Website

The site is served from `index.html` with GitHub Pages. The workflow in `.github/workflows/deploy.yml` deploys every push to `main`.

Website URL: https://superninja7667-byte.github.io/Nova-AI/

The repository's Pages publishing source must be set to **GitHub Actions** in Settings → Pages.

## Sonic local AI requirements

- A secure HTTPS website (GitHub Pages provides HTTPS).
- Browser support for WebGPU.
- Internet access for the first download of the local model and runtime.
- Sufficient device GPU memory.

After the model is downloaded, inference runs on the user's device. Device capability varies; Nova checks WebGPU before trying to load the model. Model weights are not stored in this repository; WebLLM downloads the selected model when Sonic is initialized.

## Installable web app

Nova includes a web app manifest and a service worker for caching the app shell. The service worker does not cache large model weights; WebLLM manages model caching in browser storage.

## Development

Edit `index.html` and push changes to `main`. GitHub Actions deploys the updated website.
