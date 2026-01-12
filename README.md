# jack-kerouac's remastered travelblog.org travelblog

The content is scraped from traveblog.org backup HTML files. The photos have been matched to high-res original photos.
The scripts for both of that can be found in the repo travelblog-resampling.

## Structure

- `content/posts/` - Blog entries organized by trip ID
- `content/trips/` - Trip overview pages
- `static/images/` - Photos (low-res from backup, replaceable with high-res)

## Running the Site

1. Install Hugo: https://gohugo.io/installation/

2. Run the development server:
   ```bash
   cd hugo_site
   hugo server -D
   ```

3. Visit http://localhost:1313

## Building for Production

```bash
cd hugo_site
hugo
```

The site will be built to `public/` directory.

## Customization

- Edit `hugo.yaml` to change site settings
- Modify templates in `layouts/`
- Add custom CSS to `static/css/style.css`
- Choose a Hugo theme or create your own
