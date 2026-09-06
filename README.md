# Modern C++ Programming Lectures

This repository contains the Slidev source for the Modern C++ Programming lecture series. Lecture 0 is in [`0-intro/slides.md`](backup/0-intro/slides.md); its checked-in PDF and PowerPoint exports are public release artifacts.

## Environment

- Node.js 20 or later (the project is tested with Node.js 24)
- npm 10 or later

Install the pinned project dependencies from the repository root:

```console
npm install
```

The Slidev theme packages the presentation fonts locally: Inter for Latin text, Noto Sans SC for Chinese text, and JetBrains Mono for code. No system-font setup is required.

Slidev uses Chromium to create PDF and PowerPoint exports. If its first export reports that no browser is installed, run:

```console
npx playwright install chromium
```

## Authoring and previewing

Start the lecture 0 development server:

```console
npm run dev
```

Edit [`0-intro/slides.md`](backup/0-intro/slides.md) and save; Slidev refreshes the browser preview automatically. Shared visual rules live in [`0-intro/style.css`](backup/0-intro/style.css).

## Publishing artifacts

Build the static web presentation:

```console
npm run build
```

Export the public PDF and PowerPoint files:

```console
npm run export
```

The static preview is generated in `0-intro/dist/` and is intentionally untracked. In contrast, [`0-intro/0-intro.pdf`](backup/0-intro/0-intro.pdf) and [`0-intro/0-intro.pptx`](backup/0-intro/0-intro.pptx) are release artifacts and must remain tracked.
