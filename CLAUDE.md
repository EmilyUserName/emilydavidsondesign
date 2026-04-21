# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

Static portfolio website for Emily Davidson. Single-file architecture — all HTML, CSS, and JS live in `index.html`. The other HTML files (`Emily_Website_v2.html`, `this this this final Emily_Website_v2 (3).html`, `THIS ONE - Emily Website v1.html`, `Emily_Davidson_Brand_Book (1).html`) are earlier design iterations; **`index.html` is the live site**.

No build step, no dependencies, no package manager. Open `index.html` directly in a browser to develop.

## Architecture

Everything is in one file, organized in this order:

1. **`<head>`** — Google Fonts (DM Serif Display, DM Sans), all CSS in a `<style>` block
2. **HTML sections** — `nav`, `#hero`, `#work`, `#about`, `#contact`, `footer`
3. **`<script>`** at the bottom — hamburger menu toggle, Formspree AJAX contact form

### Design tokens (CSS variables on `:root`)
| Token | Value | Usage |
|-------|-------|-------|
| `--navy` | `#0d2136` | Primary dark background |
| `--rust` | `#c45c2e` | Accent / CTA color |
| `--teal` | `#6aabae` | Secondary accent |
| `--gold` | `#f5c842` | Hover highlights |
| `--fog`  | `#f4f1eb` | Page background |

### Contact form
Uses [Formspree](https://formspree.io) for form handling. The form `action` is currently set to `https://formspree.io/f/YOUR_FORM_ID` — replace with a real Formspree endpoint before deploying. The JS intercepts submit, posts via `fetch`, and swaps the form for a success message on `res.ok`.

## Key details
- **Contact email:** `hello@emilydavidsondesign.com` — appears in two places in `index.html` (form note + footer)
- **Resume link:** `/emily-davidson-resume.pdf` (served from root, not in this repo)
- Mobile nav uses a hamburger drawer (`#hamburger` / `#drawer`) that locks body scroll when open
