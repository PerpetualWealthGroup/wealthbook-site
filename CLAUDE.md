# wealthbook-site — the front website

This repo IS the site. GitHub Pages serves `main` as it stands: no build,
no framework, no dependencies. A push to `main` is live within about half
a minute. That is the whole deploy (the Family Capital site works the
same way, and this is its twin).

## How it is worked

- Ian never edits this repo by hand. He lands each page's look in Claude
  Design; the finished page comes to the Claude Code session and Claude
  puts it here in the house's real tokens.
- **The website has a staging twin** (12 Sep 2026: "when we go live with
  this people will see it straight away"):
  `PerpetualWealthGroup/wealthbook-site-staging`, served at
  https://perpetualwealthgroup.github.io/wealthbook-site-staging/. The
  two words mean here what they mean for the app: **"Ship it"** = push
  the page to the staging repo's `main`, reply "on staging"; **"Merge
  it"** = push the same files to THIS repo's `main`, which is
  wealthbook.co.uk, reply "live at hh:mm BST". Nothing else moves
  anything. The artifact sketch is where ideas are argued about before
  either.
- The app repo is `PerpetualWealthGroup/wealthbook`; this one is
  `PerpetualWealthGroup/wealthbook-site`. Every session starts from the
  group, never from an alias.

## The clothes

`css/site.css` carries the house's tokens, copied from the app's
`apps/web/app/globals.css :root` so the website and the book are one
hand: Cormorant Garamond for display, Instrument Sans for text, the
paper `#fcfbf9`, the ink `#1a1815`, two radii and no more. Change a
token in the app first; this file follows.

## The cache

GitHub Pages sends every file with `max-age=600`, and a browser keeps it
for those ten minutes. So a push that changes `css/site.css` or
`js/entry.js` must also bump the `?v=` on their links in `index.html`,
or the reader gets the new page in the old clothes (12 Sep 2026: the
hero went live naked on Ian's screen). Claude bumps it on every push
that touches them; never publish a stylesheet change without it.

## Files

- `index.html` — the home page.
- `css/site.css` — the tokens and the page's dress.
- `.nojekyll` — tells Pages to serve the files as they are.
- `CNAME` — the domain, once Ian names it (absent until then).
