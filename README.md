# Thomas Prata — Portfolio Website

Built with [Quarto](https://quarto.org) and deployed via GitHub Pages.

**Live site:** https://tprata24.github.io
**Repo:** https://github.com/tprata24/tprata24.github.io

## Pages

| Page | File |
|---|---|
| Home | `index.qmd` |
| Projects | `projects.qmd` + `projects/*.qmd` |
| Dashboard | `dashboard.qmd` (Quarto Dashboard, Python + Plotly) |
| Presentation | `presentation.qmd` (Reveal.js) |
| Résumé | `resume.qmd` + `resume/Resume.pdf` |

Google Analytics 4 (GA4) is wired in via `includes/ga-head.html`, injected into every page through `_quarto.yml`.

## One-Time Local Setup

1. **Install Quarto** — download the installer for your OS from https://quarto.org/docs/get-started/ and follow the prompts. Verify with:
   ```bash
   quarto check
   ```
2. **Install Python packages** used by the dashboard:
   ```bash
   pip install -r requirements.txt
   ```
3. Clone this repo (or the one you create from this project):
   ```bash
   git clone https://github.com/tprata24/tprata24.github.io.git
   cd tprata24.github.io
   ```

## Preview Locally

```bash
quarto preview
```

This opens a live-reloading local server so you can see edits instantly.

## Render the Full Site

```bash
quarto render
```

Output goes to `_site/`.

## Publishing to GitHub Pages

**Option A — one command (recommended for your first push):**

```bash
quarto publish gh-pages
```

This renders the site and pushes it to a `gh-pages` branch, then walks you through enabling GitHub Pages on that branch (Settings → Pages → Source: `gh-pages` branch).

**Option B — automatic on every push (already set up in this repo):**

A GitHub Actions workflow at `.github/workflows/publish.yml` automatically renders and publishes the site to the `gh-pages` branch every time you push to `main`. After the first run, go to your repo's **Settings → Pages** and set the source to the `gh-pages` branch if it isn't already selected.

## Repo Name Matters for the URL

- If your repo is named `tprata24.github.io` (a *user site*), your live URL is exactly `https://tprata24.github.io`.
- If you name it something else, e.g. `portfolio-website`, your live URL will be `https://tprata24.github.io/portfolio-website/` — update `site-url` in `_quarto.yml` to match.

## Editing Content

- **Home page copy:** `index.qmd`
- **Add/edit a project:** add a new `.qmd` file to `projects/` with the same YAML front-matter pattern (`title`, `description`, `date`, `image`, `categories`) — it'll automatically appear in the `projects.qmd` grid.
- **Dashboard data:** edit the `pandas` DataFrames at the top of `dashboard.qmd`.
- **Presentation slides:** each `##` (level-2 heading) in `presentation.qmd` is a new Reveal.js slide; `---` also creates a slide break.
- **Colors/fonts:** `theme.scss`
- **GA4 ID:** `includes/ga-head.html`
