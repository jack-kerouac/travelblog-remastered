# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a remastered travel blog containing content scraped from travelblog.org backup HTML files, with photos matched to high-resolution originals. The content covers travel trips from 2006-2013 across Southeast Asia, South America, and the USA.

The scraping and photo-matching scripts are in a separate repository: `travelblog-resampling`.

## Content Structure

### Directory Organization

- `content/posts/` - Blog entries organized by trip slug (e.g., `south-america-2012/`, `southeast-asia-2006/`)
  - Each trip directory contains numbered markdown files: `000-post-slug.md`, `001-another-post.md`, etc.
  - Posts are numbered sequentially, starting from `000`
- `content/trips/` - Trip overview pages
  - `_index.md` - Master index listing all trips with stats
  - Individual trip pages: `south-america-2012.md`, `southeast-asia-2006.md`, etc.
- `static/images/` - Photos organized by trip slug (matches post directory names)
  - Images are low-res from backup, replaceable with high-res originals

### Post Front Matter Structure

Blog posts use YAML front matter with the following fields:

```yaml
---
title: "Post Title"
date: 2012-10-03T00:00:00
draft: false
location:
  - "Continent"
  - "Country"
  - "Region"
  - "City/Location"
trip_slug: "south-america-2012"  # Must match directory name
original_url: "https://www.travelblog.org/..."
images:
  - filename: "image-name.jpg"
    title: "Image Title"
    description: "Optional description"  # Not always present
---
```

### Trip Front Matter Structure

Trip overview pages use:

```yaml
---
title: "Country1, Country2 YYYY"
type: trips
start_date: 2012-09-28T00:00:00
end_date: 2012-10-07T00:00:00
countries:
  - Country1
  - Country2
continents:
  - Continent Name
trip_slug: "slug-name"  # Must match directory name
stats:
  entries: 4
  words: 1886
  photos: 89
posts:
  - /posts/trip-slug/000-post-slug
  - /posts/trip-slug/001-another-post
---
```

## Development Notes

### Static Site Generator

This project was initially set up for Hugo but the Hugo configuration, layouts, and CSS were removed (see commit 1d2adff). The content is currently in Hugo-compatible format with:
- Markdown files with YAML front matter
- `public/` directory in `.gitignore` (Hugo's default output directory)
- Standard Hugo content structure

If working with Hugo again, you'll need to recreate the configuration file and layouts.

### Content Consistency

- **Trip slugs must be consistent**: The `trip_slug` field in front matter must exactly match the directory name in `content/posts/` and `static/images/`
- **Post numbering**: Posts within each trip are numbered sequentially starting from `000`
- **Image paths**: Images referenced in post front matter should exist in `static/images/{trip_slug}/`
- **Languages**: Content is mixed German and English
