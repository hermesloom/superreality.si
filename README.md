# BOOTSTRAP — A Manifesto for the Free Human

Single-page website for the manifesto. Static HTML and CSS, no build step. The only script is the Vercel Web Analytics snippet.

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

Built for Vercel. With the Vercel CLI: `vercel` for a preview, `vercel --prod` for production.

Analytics: the page loads `/_vercel/insights/script.js`, which Vercel serves once **Web Analytics** is enabled for the project (Vercel dashboard → project → Analytics → Enable). On any other host the request 404s harmlessly.
