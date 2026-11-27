# Nova — Sonic AI

Nova is a browser-based AI workspace. Sonic runs an open-weight language model locally in the browser through WebLLM and WebGPU; it does not call an AI inference API.

## Website

The site is published with GitHub Pages from `index.html`. The GitHub Actions workflow in `.github/workflows/deploy.yml` deploys each push to `main`.

### One-time Pages setup

In this repository, open **Settings → Pages → Build and deployment → Source**, then choose **GitHub Actions**. GitHub requires this repository setting before the Pages workflow can publish the site.

After that, every push to `main` automatically updates the website.

The project site URL will be:

https://superninja7667-byte.github.io/Nova-AI/

## Sonic local AI requirements

- A secure HTTPS website (GitHub Pages provides HTTPS).
- Browser support for WebGPU.
- Internet access for the first download of the local model and runtime.
- Sufficient device GPU memory.

After the model is downloaded, inference runs on the user's device. Device capability varies; Nova checks WebGPU before trying to load the model. Model weights are not included in this repository.

## Installable web app

Nova includes a web app manifest and a small service worker for caching the app shell. This does not cache the large model weights itself; WebLLM manages model caching in browser storage.

## Development

Edit `index.html` and push changes to `main`. GitHub Actions will deploy the updated site.
