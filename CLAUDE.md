# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static site for Greek language lecture notes (Греческий язык — Конспект лекций). Content is in Russian, teaching Ancient/Modern Greek.

## Architecture

- **`index.html`** — Single-page app with collapsible sections. Self-contained: all CSS and JS are inline (no build step, no dependencies). Supports light/dark mode via `prefers-color-scheme`. Content is organized into expandable `<details>` sections. The HTML content mirrors the markdown structure directly.
- **`lecture notes.md`** — Copy of the source material from `C:\Data\Src\learn-lang\lecture notes.md`, kept here for change tracking. When updating the HTML, read from this file. The source of truth is the learn-lang repo; copy it here before updating.
- **`favicon.svg`** — SVG favicon (Greek Sigma on blue background).

## Update workflow

When the user says "обнови" / "update", run these steps **in this exact order**:

1. **Update markdown first**: copy `lecture notes.md` from `C:\Data\Src\learn-lang\lecture notes.md` to this repo
2. Diff the local copy against the previous version to identify changes
3. Update `index.html` to match the new markdown content
4. **Deploy to Vercel**: `npx vercel --prod --yes` (auto-deploy from GitHub is not set up; manual deploy required via Vercel CLI)
5. **Commit and push** to GitHub last

Order matters: md → html → deploy → commit/push.

## Development

No build tools, package manager, or test framework. Open `index.html` directly in a browser to preview. Deploy via Vercel (project: `db-el`, URL: `https://db-el.vercel.app`).

## Conventions

- Content language: Russian (lang="ru")
- Greek text uses actual Greek Unicode characters
- CSS uses custom properties for theming (dark/light mode)
