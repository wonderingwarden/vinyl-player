# Vinyl — A Local-First Record Player

A browser-based music player inspired by the physical ritual of playing a vinyl record. It combines a rotating record, animated tonearm, waveform, playlist, album-art color extraction, and a highly customizable visual environment.

**No build step. No framework. No account.** Open `index.html` in a modern browser and add audio files from your device.

## Preview

The application is designed around a dark, editorial interface with a record-player stage and a compact playlist sidebar. It also includes a light theme and custom colors.

> **Privacy by design:** audio files are selected from the user's device and played in the browser. The app does not include an upload service or backend. Browser-local object URLs are used to access selected files during the session.

## Features

- **Local audio playback** — select or drag in multiple audio files.
- **Playback controls** — play/pause, previous/next, shuffle, repeat, seeking, and volume.
- **Vinyl animation** — spinning record and tonearm movement while playing.
- **Playlist management** — select tracks, remove individual tracks, or clear the list.
- **Metadata and artwork** — reads supported embedded metadata where available; missing metadata falls back gracefully.
- **Dynamic visuals** — album-art color sampling, waveform animation, and decorative record skins.
- **Customization** — disc color, accent color, background scene, background color, and dark/light appearance.
- **Responsive layout** — adapts to smaller screens.
- **Keyboard shortcuts** — Space to play/pause, Left/Right Arrow for previous/next, and Up/Down Arrow for volume.
- **Reduced-motion support** — honors the operating system's reduced-motion preference.

Audio format support depends on the browser and operating system. The file picker accepts common audio formats, but accepting a file does not guarantee that a browser can decode it.

## Quick start

### Option 1 — Open locally

1. Download or clone this repository.
2. Open `index.html` in a current version of Chrome, Firefox, Edge, or Safari.
3. Drag audio files into **Your Music**, or click the upload area to choose files.
4. Use the playback controls and settings menu to personalize the player.

No Node.js installation, package manager, API key, or server is required for the core app.

### Option 2 — Run a local static server

A local server is useful for consistent browser behavior during development.

```bash
python -m http.server 8000
```

Then open <http://localhost:8000>.

## Keyboard shortcuts

| Key | Action |
| --- | --- |
| `Space` | Play / pause |
| `←` | Previous track |
| `→` | Next track |
| `↑` | Increase volume |
| `↓` | Decrease volume |

Shortcuts are intended for use when focus is not inside a text or file input.

## Project structure

```text
vinyl-player/
├── index.html        # Complete application (HTML, CSS, and JavaScript)
├── README.md         # Project overview and setup instructions
├── LICENSE           # MIT license
├── CONTRIBUTING.md   # Contribution workflow and quality guidelines
├── SECURITY.md       # Security reporting guidance
├── .gitignore        # Common local/editor artifacts
└── .github/
    ├── ISSUE_TEMPLATE/
    │   ├── bug_report.md
    │   └── feature_request.md
    └── pull_request_template.md
```

## Technical overview

The project is a dependency-free, client-side application built with semantic HTML, CSS, and vanilla JavaScript. The Web Audio playback surface is an HTML `<audio>` element; the rest of the interface synchronizes its state with the browser's media events.

- **UI:** HTML and CSS, including custom properties for theme tokens.
- **Playback:** native browser audio playback.
- **Metadata/artwork:** parsed from supported embedded audio metadata when present.
- **Persistence:** theme settings may be stored in browser local storage; imported audio is not uploaded to a server.
- **Visual effects:** CSS animations and inline SVG artwork.

## Browser compatibility and limitations

- Use a modern browser with HTML audio support.
- Playback compatibility varies by codec and browser.
- Album art and metadata depend on the format and embedded tags in the selected file.
- This repository does not provide streaming, a cloud library, authentication, or server-side storage.
- Google Fonts are loaded from Google Fonts when a network connection is available; system fallbacks are used otherwise.
- Playlist files are session-local. Refreshing the page may require selecting them again.

## Development and quality checks

This is a static project with no build system. Before submitting a change:

1. Open the app and verify the primary controls.
2. Test at desktop and narrow mobile widths.
3. Test with files that have metadata and files that do not.
4. Verify dark/light themes and customization settings.
5. Check the browser console for errors.
6. Confirm keyboard and reduced-motion behavior where applicable.

The responsive rules and metadata added to this repository improve presentation and discoverability, but the application should still be manually tested in target browsers before being described as production-ready.

## Deploy with GitHub Pages

1. Push the repository to GitHub.
2. Open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select the `main` branch and `/ (root)`, then save.
5. Wait for GitHub Pages to publish the site; the URL will appear in the Pages settings.

Because the app is static, no server-side environment variables are needed. GitHub Pages deployment availability depends on repository and account settings.

## Privacy

The app does not contain an application backend or a file-upload endpoint. Selected files are handled in the browser for playback. Avoid adding analytics or third-party scripts without documenting their data collection and obtaining appropriate consent.

## License

Distributed under the MIT License. See [`LICENSE`](LICENSE).
