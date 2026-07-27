# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a GitHub profile repository (`zZMathSP/zZMathSP`). The README.md is rendered on the GitHub profile page.

## Structure

- **README.md** — Profile page content (bio, shields.io stack badges, snake animation)
- **.github/workflows/cobrinha.yml** — GitHub Actions workflow that generates the contribution grid snake animation using `Platane/snk@v3`, published to the `output` branch

## Notes

- The snake SVGs are served from the `output` branch via `raw.githubusercontent.com` — **not** `github.com/.../blob/...`, which returns `text/html` and renders as a broken image
- Two variants are generated (`github-contribution-grid-snake.svg` and `-dark.svg`) and selected in the README with `<picture>` + `prefers-color-scheme`
- `Platane/snk` must be pinned to `@v3` or newer; `@master` generates a degenerate SVG with an empty contribution grid
- The workflow uses `GITHUB_TOKEN` (automatic secret) — no manual secrets required
- The `push` trigger on `main` exists partly to keep the schedule alive: GitHub disables scheduled workflows after 60 days of repository inactivity
- Avoid `github-readme-stats.vercel.app` — the public instance is unreliable (returned HTTP 503 consistently as of Jul 2026). Self-host it if those cards are wanted
