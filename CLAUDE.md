# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A single static page for "Laboratorio de Futuros / La Huella del Panadero" — a Spanish-language one-page document presenting the project (concept, format, roles, hitos, audience). Content language is Spanish; preserve it when editing copy.

Deployed via GitHub Pages from `main` at the repo root → https://uffdg.github.io/labfuturos/. There is no build step, no framework, no package manager, and no test suite. Edits to [index.html](index.html) go live on push.

## Files

- [index.html](index.html) — the live page. Self-contained: inline `<style>`, inline base64 logo images, Google Fonts (Syne + Inter) via `<link>`. No JS in the current version.
- [_index.html](_index.html) — an older, much longer variant kept as a backup. It included a nav bar with a mobile hamburger toggle and inline `<script>`. Do not edit it for live changes; treat it as reference/history only.

## Editing conventions

The current page is intentionally document-style (single column flow, no nav, no scripts). When making changes:

- **Design tokens live in `:root`** ([index.html](index.html) `--ink`, `--muted`, `--accent` navy, `--teal`, `--rule`, `--surface`, `--paper`, `--display` = Syne, `--body` = Inter). Use these vars rather than hardcoding colors/fonts.
- **Section rhythm**: sections are separated by `<hr class="rule">` and introduced by `<div class="sec-label">…</div>`. Keep this pattern when adding sections.
- **Grid primitives**: `.two-col`, `.three-col`, `.roles-grid` (3×2). Reuse them instead of inventing new layouts; the `@media(max-width:640px)` block already collapses all three to a single column.
- **Typography scale is tight** (body ~12.5px, labels ~9–10px uppercase with `.12–.18em` letter-spacing). New copy should match the existing size/weight/letter-spacing pattern of the surrounding section.
- The current `index.html` has no JavaScript. If you need to add interactivity, confirm with the user first — the rewrite away from `_index.html` removed the nav/script deliberately.

## Preview locally

Just open [index.html](index.html) in a browser, or serve the directory with any static server, e.g. `python3 -m http.server 8000` then visit http://localhost:8000/.
