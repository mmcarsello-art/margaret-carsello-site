# Margaret Carsello — site prototype (Claude Code + GitHub version)

This is a working sketch of what your portfolio site could be as actual code,
instead of a Wix template. It's built as a **Jekyll site**, which matters for
one practical reason: GitHub Pages builds Jekyll sites automatically, for
free, with zero configuration — you don't need to install anything to make
this go live.

## What's in here

```
_config.yml              site title/description
_data/collections.yml    every series, grouped — the single source of truth
_layouts/default.html    the page shell: <head>, nav, footer (every page uses this)
_includes/nav.html       the nav bar + mega-menu, built FROM collections.yml
_includes/footer.html    the footer
assets/css/style.css     all the styling
assets/js/main.js        nav toggles, scroll animation
index.html               homepage content
about.md                 stub — needs your real bio
contact.md               stub — already has your real email
work/vessels.md          one example series page (template for the other 11)
```

## Why this is different from the single HTML file I showed you first

In that version, the nav menu and the "full archive" list at the bottom of
the homepage were both hand-typed — if you added a new series, you'd have to
update the text in two places and remember to keep them in sync.

Here, both are generated from `_data/collections.yml`. Add a new series to
that one file, with a title and a slug, and it appears in the nav dropdown
*and* the homepage archive automatically. This is the actual advantage of
"site as code" over a page builder: logic like this is trivial once, instead
of needing a plugin or a paid feature.

## Getting this live (no local setup required)

1. Create a new repository on GitHub (e.g. `margaret-carsello-site`).
2. Upload all the files in this folder, keeping the folder structure intact.
3. In the repo's **Settings → Pages**, set Source to "Deploy from a branch,"
   branch `main`, folder `/ (root)`. Save.
4. GitHub builds it automatically. Your site appears at
   `https://yourusername.github.io/margaret-carsello-site/` within a minute
   or two. A custom domain (margaretcarsello.com) can be pointed at this
   later from the same Pages settings screen.

## How Claude Code fits in after that

Once this is in a GitHub repo, you'd open that folder with Claude Code
(either the desktop app's Code tab, or the terminal/VS Code version) and just
describe changes in plain English:

- "Add a new series called Glaze Studies under Material & surface, slug
  glaze-studies"
- "Make the accent color a deep green instead of clay"
- "Add a contact form using Formspree" (static sites can't process form
  submissions on their own — they need a small third-party service like this)
- "Build out the real Noble Women Reframed page using these images" (you'd
  drop the images into the conversation or the repo first)

Claude Code edits the actual files, shows you the diff, and once you're happy
you commit and push — the live site updates within a minute. No dashboard,
no plugin marketplace, no monthly builder fee. The tradeoff honestly named:
you're the one responsible for backups and security being "fine" (GitHub
Pages itself is static and very low-risk), and there's no visual drag-and-
drop editor — changes happen by describing them to Claude Code or by hand.

## Honest gaps in this prototype, before it's a real site

- Images are currently hot-linked from your existing Wix media library —
  that's fine for previewing, but for a real launch they should be
  downloaded and committed into an `assets/images/` folder so the site
  doesn't depend on Wix staying up.
- `about.md`, `contact.md`, and the series pages are placeholders.
- Only one series page (`vessels.md`) exists as a template — the other 11
  follow the exact same pattern and are quick to generate once you're happy
  with this one's layout.
