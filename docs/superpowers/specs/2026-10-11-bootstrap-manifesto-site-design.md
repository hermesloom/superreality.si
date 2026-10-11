# BOOTSTRAP manifesto website — design spec

Date: 2026-10-11
Status: written autonomously (no interactive review was possible); decisions below are assumptions to be confirmed by the author.

## Goal

Publish the manifesto "BOOTSTRAP — Manifest für den freien Menschen" (written in German) as a single-page website in **English**. The page should read like a printed manifesto poster: typographic, uncompromising, fast, with no dependencies.

## Content

- The full text is translated into English by hand, preserving the author's line breaks, section breaks, and emphasis (bold = assertion, italic = aside).
- Title: "BOOTSTRAP". Subtitle: "A Manifesto for the Free Human" (for "Manifest für den freien Menschen").
- The "Sie sagen / Wir sagen" refrain is typeset as a dialogue with hanging labels ("They say" / "We say"), which mirrors the source's bold-vs-regular contrast.
- No author byline (the text speaks as "we").

## Design

- Typeface: **Jost** (the author's typeface; a Futura revival, which ties the page to the Bauhaus-era manifesto tradition). Self-hosted as woff2 (regular, italic, bold) to avoid third-party font requests. System monospace for small labels (section numbers, metadata) as a nod to the text's code metaphors.
- Palette: warm paper background, near-black ink, one red accent used sparingly (the "We say" label, section rules, the blinking caret). Dark scheme follows `prefers-color-scheme`.
- Layout: a poster-like header (small monospace top bar, the title "BOOTSTRAP" set edge to edge as an inline SVG wordmark, a rule, the subtitle), with the opening "They say / We say" pair anchored at the bottom of the first screen as the lede. Below it, a single centered column with a short measure (36rem) so the author's short lines stay short. Sections are numbered 01–10; on wide screens the numbers hang in the left margin. The closing "BOOTSTRAP." is an SVG that fills the column width, followed by a red block cursor, bookending the title.
- Motion: a blinking caret (top bar and after the final "BOOTSTRAP.") and a short fade-up of the header on load. Both disabled under `prefers-reduced-motion`.
- Print stylesheet: black on white, no caret, no decoration.

## Architecture

Static files only, no build step, no JavaScript required for reading:

```
index.html            the page (semantic: header / main > article > section × 10)
styles.css            all styles, design tokens on :root
fonts/*.woff2         Jost regular / italic / bold (+ OFL license)
favicon.svg           Jost Bold "B" on a red square
apple-touch-icon.png  same mark, 180×180
og.png                1200×630 social preview (rendered from the same styles)
```

Deployable to any static host (Vercel, Netlify, GitHub Pages, nginx). Canonical URL assumed to be `https://superreality.si/` from the repository name.

## Verification (done 2026-10-11)

Rendered headlessly with Chromium at 320, 390, 820, 1440 and 1920px wide, light and dark, plus print emulation. Fonts load (checked via `document.fonts`), no horizontal overflow at any width, the title and closing wordmarks fill their containers exactly, carets render, print output is clean black on white. Every paragraph of the German original has a counterpart on the page; the translation itself still needs the author's review.

## Out of scope (possible follow-ups)

German original as a second page / language toggle; share buttons; analytics; a PDF download.
