# legal

Static legal documentation site hosted on GitHub Pages.

## Pages

### Studio-wide

| URL | Content |
|-----|---------|
| `/` | Legal document index |
| `/terms.html` | Terms of Service |
| `/privacy.html` | Privacy Policy |
| `/cookie.html` | Cookie Policy |

### App-specific

| URL | Content |
|-----|---------|
| `/lite-translate/privacy.html` | Lite Translate — Privacy Policy |
| `/lite-translate/terms.html` | Lite Translate — Terms of Service |

## Setup

1. Push this directory to `github.com/tooolab/legal` (`main` branch)
2. **Repository Settings** → Pages → Source: `Deploy from branch` → `main` → `/ (root)`
3. Pages will be available at `https://tooolab.github.io/legal/`

### Custom domain (optional)

1. Add a `CNAME` file with your domain (e.g. `legal.tooolab.com`)
2. Configure DNS: CNAME record pointing to `tooolab.github.io`
3. Enable "Enforce HTTPS" in Pages settings
4. Update `sitemap.xml` and `robots.txt` URLs to match your domain

## Constants

| Key | Value |
|-----|-------|
| Studio name | Tooolab Inc. |
| Contact email | tooolab.app@gmail.com |
| Jurisdiction | the People's Republic of China |
| GitHub org | tooolab |

## Adding a new app

Copy an existing app directory (e.g. `lite-translate/`) as a starting point:

```bash
cp -r lite-translate/ your-app-slug
```

Then:
1. Edit `your-app-slug/privacy.html` and `terms.html` — replace content, update canonical URLs, data collection table
2. Add a group section in root `index.html`
3. Add URLs to `sitemap.xml`

## Removing an app

```bash
rm -rf your-app-slug/
```

Then remove the group section from `index.html` and entries from `sitemap.xml`.

## Document versioning

Before updating any legal document:

1. Create a git tag: `git tag terms-v1.0 -m "Terms effective 2025-01-01"`
2. Update the document content
3. Update the "Effective" date in the page
4. Update `sitemap.xml` lastmod dates
5. Commit and push

Users can view previous versions via git history or tagged releases.

## Stack

- Pure HTML + CSS + vanilla JS (~3KB)
- Inter font via Google Fonts
- Lucide icons (inline SVG)
- Dark/light theme toggle (localStorage)
- No build tools, no frameworks
