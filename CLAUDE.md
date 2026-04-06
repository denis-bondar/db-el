# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static site for Greek language lecture notes (Греческий язык — Конспект лекций). Content is in Russian, teaching Ancient/Modern Greek.

## Architecture

- **`index.html`** — Single-page app with collapsible sections. Self-contained: all CSS and JS are inline (no build step, no dependencies). Supports light/dark mode via `prefers-color-scheme`. Content is organized into expandable `<details>` sections. The HTML is an editorially condensed version of the markdown (transliterations removed, text shortened, sections restructured/split, some detailed tables expanded with stress rules).
- **`lecture notes.md`** — Copy of the source material from `C:\Data\Src\learn-lang\lecture notes.md`, kept here for change tracking. When updating the HTML, read from this file. The source of truth is the learn-lang repo; copy it here before updating.
- **`favicon.svg`** — SVG favicon (Greek Sigma on blue background).

## Development

No build tools, package manager, or test framework. Open `index.html` directly in a browser to preview. Deploy via Vercel (project: `db-el`).

## Conventions

- Content language: Russian (lang="ru")
- Greek text uses actual Greek Unicode characters
- CSS uses custom properties for theming (dark/light mode)
