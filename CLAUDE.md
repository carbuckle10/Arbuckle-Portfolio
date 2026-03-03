# Portfolio — Claude Context

## Project Overview
Quarto website portfolio for Carson Arbuckle. Deployed to Vercel via GitHub.

- **Repo:** https://github.com/carbuckle10/Arbuckle-Portfolio
- **Live site:** Vercel (auto-deploys on push to `main`)

## Tech Stack
- **Framework:** Quarto (static site generator)
- **Theme:** Cosmo + custom `styles.css`
- **Fonts:** Syne, Manrope (Google Fonts)
- **Icons:** Font Awesome 6.4.0
- **Deployment:** GitHub → Vercel, output directory: `_site`

## Important: Build & Deploy Workflow
Quarto is not available on Vercel — the site must be built locally before pushing.

```bash
# Build the site
/Applications/RStudio.app/Contents/Resources/app/quarto/bin/quarto render

# Then commit _site/ and push
git add _site/ && git commit -m "..." && git push origin main
```

`_site/` is committed to the repo (intentionally removed from .gitignore) so Vercel can serve the pre-built files.

## Site Structure
```
index.qmd          # Homepage with hero + project cards
about.qmd          # About page
problems.qmd       # Problems page
projects/
  project-1.qmd   # Tetris Game — https://tetris-game-egc6.vercel.app/
  project-2.qmd   # JobTrackr — https://careercrm.vercel.app
  project-3.qmd   # (unused template)
  project-4.qmd   # (unused template)
  project-5.qmd   # (unused template)
  project-6.qmd   # (unused template)
_quarto.yml        # Site config, navbar, theme
styles.css         # All custom styles
_site/             # Built output (committed, served by Vercel)
vercel.json        # Points Vercel at _site/ as output directory
```

## Adding a New Project
1. Write content in `projects/project-N.qmd` (follow pattern from project-1.qmd)
2. Uncomment/add the entry in `_quarto.yml` navbar menu
3. Add a project card to `index.qmd`
4. Run `quarto render`, then commit and push

## Project Page Pattern
Each project page includes:
- YAML front matter: `title`, `date`, `categories`
- HTML page-header section with overline, h1, and lead paragraph
- Overview section (bullet list of features)
- Live Demo section with two buttons (Open App + GitHub) and an iframe embed
- Technical Details section (stack, deployment, tools)
