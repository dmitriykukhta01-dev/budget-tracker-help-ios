# Family Budget Tracker — Legal & Support site

Static Jekyll site that hosts the app's **Privacy Policy** and **Support** pages,
required for App Store / Google Play submission.

## Files

| File | Output URL (once deployed) | Purpose |
|------|----------------------------|---------|
| `index.md` | `/` | Landing page linking to both |
| `privacy.md` | `/privacy.html` | Privacy Policy (**Privacy Policy URL** in App Store Connect) |
| `support.md` | `/support.html` | Support & Help (**Support URL** in App Store Connect) |
| `_layouts/default.html` | — | Shared theme (styling, header, footer) |
| `_config.yml` | — | Jekyll config (kramdown, auto-TOC) |

Edit content in the `.md` files. Styling lives in `_layouts/default.html`.
No plugins are used, so it builds on GitHub Pages as-is.

## Deploy on GitHub Pages (simplest — no CI)

1. Commit and push this `docs/` folder to your default branch.
2. On GitHub: **Settings → Pages**.
3. **Source:** "Deploy from a branch". **Branch:** your default branch, **Folder:** `/docs`. Save.
4. Wait ~1 minute. Your pages are live at:
   - `https://<username>.github.io/<repo>/privacy.html`
   - `https://<username>.github.io/<repo>/support.html`

## Alternative — dedicated `gh-pages` branch

From the repo root:

```bash
git subtree push --prefix docs origin gh-pages
```

Then set **Settings → Pages → Source:** `gh-pages` branch, `/ (root)`.
Re-run the command after each change to `docs/`.

## Preview locally (optional)

```bash
cd docs
bundle exec jekyll serve      # requires Ruby + jekyll installed
# → http://localhost:4000/
```
