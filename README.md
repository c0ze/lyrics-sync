# lyrics-sync

Manual lyric synchronization tool built as a lightweight local-first static web app.

The app lives in a single [`index.html`](./index.html) file and runs entirely in the browser with no build step, no dependencies, and no backend.

## Features

- Upload local audio files (`.mp3`, `.wav`)
- Upload lyric files as plain text (`.txt`) or LRC (`.lrc`)
- Ignore existing LRC timestamps and load only lyric text into the sync queue
- Stamp the active lyric line with the `Spacebar` while the track is playing
- Export synced lyrics as a standard `.lrc` file
- Reset timestamps and resync from the start

## Local Usage

1. Open [`index.html`](./index.html) in a browser.
2. Load an audio file.
3. Load a lyric file (`.txt` or `.lrc`).
4. Press play on the audio player.
5. Hit `Space` on each lyric line when it should appear.
6. Download the generated `.lrc` file.

You can also click any lyric line to move the active queue position before continuing.

## Deployment

This repository is intended to be deployed as a static GitHub Pages site at `lyrics-sync.arda.tr`.

### Repository Setup

1. Push the repository to GitHub.
2. In the repository settings, open `Pages`.
3. Set the site source to `GitHub Actions`.
4. Keep the included [`CNAME`](./CNAME) file committed so GitHub Pages preserves the custom domain.
5. Ensure `lyrics-sync.arda.tr` DNS is configured for GitHub Pages.

### Files Relevant to Deployment

- [`index.html`](./index.html): the application
- [`CNAME`](./CNAME): custom domain binding for GitHub Pages
- [`.nojekyll`](./.nojekyll): disables Jekyll processing for the static site
- [`.github/workflows/deploy-pages.yml`](./.github/workflows/deploy-pages.yml): deploys the static site on pushes to `main`

## Project Structure

```text
.
├── .github/
│   └── workflows/
│       └── deploy-pages.yml
├── .gitignore
├── .nojekyll
├── CNAME
├── README.md
└── index.html
```
