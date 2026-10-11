# BOOTSTRAP — A Manifesto for the Free Human

Single-page website for the manifesto. Static HTML and CSS, no build step, no JavaScript.

```
index.html     the page
styles.css     styles (design tokens on :root, dark scheme, print)
fonts/         Jost (regular, italic, bold) as woff2, self-hosted
favicon.svg    Jost "B" on red
og.png         social preview, 1200×630
```

The manifesto was written in German; the page carries the English translation.

## Preview locally

```
python3 -m http.server 8000
```

then open http://localhost:8000.

## Deploy

Any static host works. With the Vercel CLI: `vercel` for a preview, `vercel --prod` for production.
