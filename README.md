# thesis-&lt;slug&gt;

A single thesis site. Plain static HTML that deploys to its **own** GitHub Pages
and is indexed by the lab's `thesis-collection` portal.

> Made from the **thesis-template**. Click **“Use this template” → Create a new
> repository**, name it `thesis-<slug>`, then follow the three steps below.

## Quick start (3 steps)

1. **Edit the page.** Replace `index.html` (and add any `assets/`) with your
   thesis content. It can be anything static — plain HTML, a framework export,
   slides, a demo.
2. **Fill in `thesis.json`.** This is the metadata the portal turns into a card.
   `slug`, `title`, and `url` are required; the rest is optional. Set `url` to
   this site's live address, `https://nycu-icclab.github.io/thesis-<slug>/`, and
   replace the `REPLACE-ME` placeholders.
3. **Enable Pages.** Settings → Pages → **Source: GitHub Actions** (one-time).
   Every push to `main` then deploys automatically via
   `.github/workflows/deploy.yml`.

## Get listed on the portal

- **Submodule (recommended, auto-synced).** In the `thesis-collection` repo:
  ```bash
  git submodule add https://github.com/nycu-icclab/thesis-<slug> theses/<slug>
  git commit -am "Add thesis: <slug>"
  git push
  ```
  The portal rebuilds and your card appears — no manual edits needed.
- **External / link-only.** Add one entry to the portal's `data/manual.json`.

## `thesis.json` contract

```json
{
  "slug": "thesis-<slug>",
  "title": "Your Thesis Title",
  "subtitle": "One-line description",
  "authors": ["Your Name (你的名字)"],
  "advisor": "Advisor Name (指導教授)",
  "year": 2026,
  "institution": "NYCU · Your Institute",
  "tags": ["tag1", "tag2"],
  "abstract": "Short summary.",
  "url": "https://nycu-icclab.github.io/thesis-<slug>/",
  "repo": "https://github.com/nycu-icclab/thesis-<slug>",
  "archive": false
}
```

`slug`, `title`, `url` are required; everything else is optional and collapses
gracefully on the card if omitted. `source` and `archiveUrl` are added by the
portal build — don't set them here.
