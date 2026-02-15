# jack-kerouac's remastered travelblog.org travelblog

A static site built with Hugo, containing travel blog content from 2006-2013 trips across Southeast Asia, South America, and the USA. The content is scraped from travelblog.org backup HTML files, with photos matched to high-resolution originals.

**Live site**: https://jack-kerouac.github.io/travelblog-remastered/

The scraping and photo-matching scripts are in the repo: `travelblog-resampling`

## Content

- **6 trips** spanning 2006-2013
- **84 blog entries** documenting travel experiences
- **1,676 photos** from Southeast Asia, South America, and the USA
- Mixed German and English content

## Structure

- `content/trips/{trip_slug}/_index.md` - Trip overview pages with stats and entry listings
- `content/trips/{trip_slug}/{entry_slug}/index.md` - Blog entries as Hugo page bundles (images alongside)
- `layouts/` - Hugo templates for homepage, trip pages, and blog entries
- `static/css/` - Minimal styling with responsive photo grid

## Development

### Local Preview

```bash
hugo server
```

Visit http://localhost:1313/travelblog-remastered/

### Build

```bash
hugo --minify
```

Output in `public/` directory

## Deployment

Automated via GitHub Actions on push to `main` branch:
- Builds site with Hugo
- Deploys to GitHub Pages

See `.github/workflows/deploy.yml` for workflow configuration.
