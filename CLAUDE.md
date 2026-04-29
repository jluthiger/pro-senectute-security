# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a documentation-only repository containing workshop materials for a **5-hour computer security course** aimed at seniors (Senioren), produced for Pro Senectute Switzerland. There are no build tools, tests, or deployable code.

All content is written in **German (Swiss German context)**.

## Build

The build is automated via GitHub Actions on push to `main`. To build locally:

```bash
mkdir -p build
find docs -name "*.adoc" -exec asciidoctor -D build {} \;
cp build/kursprogramm.html build/index.html
```

Requires `asciidoctor` (`brew install asciidoctor` on macOS).

## File Formats

- `*.md` — Markdown (reference material, scenarios, topic content)
- `*.adoc` — AsciiDoc (course program and exercise sheets in `docs/`)
- `.github/workflows/asciidoctor.yml` — Builds and deploys to GitHub Pages on push to `main`
- `build/` — Generated HTML output (not committed, produced by CI)

## Content Structure

| File | Purpose |
|------|---------|
| `docs/kursprogramm.adoc` | Main course program: 2 × 2.5h on two days (min. 1 week apart), 4 modules |
| `docs/uebung-modul-1.adoc` | Exercise sheet: judging emails and links (Modul 1) |
| `docs/uebung-modul-2.adoc` | Exercise sheet: phone fraud and pop-up scams (Modul 2) |
| `docs/uebung-modul-3.adoc` | Exercise sheet: creating secure passwords (Modul 3) |
| `docs/uebung-modul-4.adoc` | Exercise sheet: trust fraud + personal security plan (Modul 4) |
| `szenarien.md` | 12 realistic attack scenarios — source material for course content |
| `themen.md` | In-depth topic content: password managers, email attachments, link verification |
| `docs/02-grundlagen.adoc` | Lesson 2 — internet security basics (earlier draft) |

## Audience & Tone Guidelines

Content targets **non-technical seniors** — write at an accessible level:
- Avoid jargon or define it immediately when unavoidable
- Prefer concrete examples and analogies over abstract explanations
- Use simple, direct sentences
- Swiss context: reference Swiss institutions (PostFinance, NCSC, SwissTransfer) and CHF amounts where relevant
- Psychological framing matters: explain *why* seniors are targeted without implying blame ("weniger Erfahrung" not "Leichtgläubigkeit")
