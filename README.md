# noted-site

The website for **Noted** — a privacy-first, local-only note-taking app.

Live at **https://n8codes.github.io/noted-site/**, served as static files by
GitHub Pages. No build step, no JavaScript, no third-party fonts, scripts, or
trackers — fitting for an app whose whole point is that your data never leaves
your device.

## About Noted

Noted is a local-only notebook: there's no account, no server, and no cloud —
everything you write, draw, and record is encrypted and stays on your own
device. Core features:

- **Notes & collections** — markdown entries with images, drawings, and audio
- **Inline drawings** — sketch inside an entry with brushes, fill, text, undo/redo
- **Voice memos** — record and play back audio attached to any entry
- **Real markdown** — CommonMark + GitHub-flavored tables, task lists, code blocks
- **Encrypted at rest** — AES-256 database plus per-file encryption for media
- **Export & import** — encrypted or plain backups, single-entry markdown round-trip
- **No tracking** — no analytics, no telemetry, no crash reporting, no ads

Noted is available on Android, with desktop betas for **macOS** and **Linux**
in development.

## What's in this repo

| File / dir       | Purpose                                                       |
|------------------|---------------------------------------------------------------|
| `index.html`     | **Privacy policy** — served at the site root.                 |
| `privacy.md`     | Markdown source of the privacy policy (kept in sync).         |
| `home.html`      | Landing page: intro to Noted, download links, site nav.       |
| `about.html`     | About page.                                                   |
| `styles.css`     | Shared styles for `home.html`, `about.html`, and `index.html`.|
| `icon.png`       | Site icon / favicon — the Noted app icon (512px).             |

> **Why the privacy policy is the root page:** the Noted Android app links to the
> bare site root (`https://n8codes.github.io/noted-site/`) for its in-app privacy
> policy, and that URL is already shipped in released builds. `index.html` must
> stay the privacy policy so existing app installs keep resolving correctly. The
> landing page therefore lives at `home.html`.

## Developing

Edit the HTML/CSS directly and open the files in a browser to preview, or serve
the folder locally:

```bash
python3 -m http.server   # then visit http://localhost:8000/home.html
```

## Deploy

Push to `main`. GitHub Pages publishes the files as-is — there is nothing to build.

## License

Copyright © 2026 Nathanial W. Heard. All rights reserved.
