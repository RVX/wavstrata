# Wavstrata

**A browser-based geological visualization and sonification studio.**

Wavstrata turns terrain surfaces and point clouds into an interactive 3D view and evolving sound. It is designed for classroom exploration: students can load a model, inspect and transform its shape, experiment with sound profiles, and export an audio file with a metadata sidecar.

![Wavstrata running with the dark ambient drone profile](./wavstrata-screenshot.png)

The screenshot shows the app running with the **Dark Ambient** profile, 18 voices, a 12-cent beating setting, and 82% stereo width.

## Open the app

### Try it locally

1. Download `Wavstrata.html`.
2. Open it in a current version of Chrome, Edge, or Firefox.
3. Keep an internet connection available so the page can load its visualization, interface, and icon libraries from their CDNs.

No build step, package installation, account, or server is required for local use.

### Make it available to students with GitHub Pages

GitHub Pages can serve this static app directly; no backend is needed.

1. Create a GitHub repository and upload `Wavstrata.html`, `README.md`, and `wavstrata-screenshot.png` to the repository root.
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select the `main` branch and `/ (root)`, then save.
4. When GitHub Pages finishes publishing, share:

   `https://<github-username>.github.io/<repository-name>/Wavstrata.html`

The page can take a few minutes to appear after the first deployment. Anyone with the link can use it if the repository and Pages site are public. Keep the `.html` filename in the link; the app intentionally remains a single HTML file rather than adding a second `index.html`.

## Classroom workflow

1. Open a sample preset or load a supported terrain model.
2. Inspect the surface and adjust position, axis rotations, or crop bounds.
3. Choose a sound profile:
   - **Terrain** maps the geometry into the standard synthesis options.
   - **Strata Drone** makes a slower, low-register layered drone.
   - **Dark Ambient** offers 6–24 voices, adjustable beating/detuning, and stereo width.
4. Compare **Option A** and **Option B**, then play the result.
5. Add site information in the metadata panel if appropriate. Use **WAV** and **JSON** to download the audio and its matching metadata sidecar as separate files. Both filenames share the same base name; download them individually to avoid browser restrictions on multiple automatic downloads.

The metadata sidecar records the audio format, sound settings, model name and transforms, site metadata, and the playback reverb settings. The canyon reverb, low-pass filter, and master-volume controls are for preview and are not applied to the exported WAV.

## Features

- Interactive Three.js 3D terrain and point-cloud viewer.
- OBJ, STL, PLY, and XYZ input support; PLY support is for ASCII files.
- Terrain, strata-drone, and configurable dark-ambient sound profiles.
- Audio preview controls, canyon reverb with mix, pre-delay and decay settings, plus a low-pass filter.
- 16-bit and 24-bit PCM WAV export and its matching JSON metadata sidecar as separate downloads.
- Site metadata saved in the current browser and exportable as JSON.

## Privacy and practical notes

- Wavstrata has no server or analytics backend. Models are processed in the browser; site metadata is stored in that browser's local storage unless exported.
- The page loads third-party libraries and fonts from CDNs, so an internet connection is needed. Avoid entering sensitive site information on a shared device.
- Large geometry files and long, high-resolution drone renders need more browser memory and processing time. Start with a preset or a shorter duration if a device struggles.
- The WAV contains the generated synthesis buffer. Playback-only controls such as the canyon reverb, low-pass filter, and master volume are not baked into the exported audio; the JSON sidecar records the reverb settings.

## Files

- `Wavstrata.html` — the standalone application.
- `wavstrata-screenshot.png` — screenshot of the running application.
- `README.md` — usage and GitHub Pages instructions.
