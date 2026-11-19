# Personal Profile Site

A minimalist Jekyll-based personal profile website with About and Resume sections, live at [plugaru.me](https://plugaru.me).

## Prerequisites

- Ruby 3.3 or higher (the macOS system Ruby is too old)
- Bundler gem (`gem install bundler`)

Alternatively, use Docker (no local Ruby needed):

```bash
docker run --rm -p 4000:4000 -v "$PWD":/srv -w /srv ruby:3.3 \
  bash -c 'bundle install && bundle exec jekyll serve --host 0.0.0.0'
```

## Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/PlugaruT/plugarut.github.io.git
   cd plugarut.github.io
   ```

2. **Install dependencies:**
   ```bash
   bundle install
   ```

## Running the Site

### Development Server

```bash
bundle exec jekyll serve
```

The site will be available at `http://localhost:4000`

### Build for Production

```bash
JEKYLL_ENV=production bundle exec jekyll build
```

The static site will be generated in the `_site` directory.

## Deployment

Every push to `main` runs the GitHub Actions workflow in `.github/workflows/pages.yml`,
which builds the site with Jekyll 4 and deploys it to GitHub Pages. The repository's
Pages source must be set to **GitHub Actions** (Settings → Pages → Build and deployment).

## Configuration

Edit `_config.yml` to customize:
- Site title, tagline and description (used for SEO and social cards)
- Personal information (name, location, avatar)
- Social media links
- Work experience and education

The About text lives in `_includes/author-bio.md`. Optional per-job details can be
written in `_experiences/*.md` and enabled with `details_file` in `_config.yml`.

## Project Structure

```
├── .github/workflows/
│   └── pages.yml        # Build & deploy to GitHub Pages
├── _config.yml          # Site configuration
├── _experiences/        # Optional per-job details for the Resume view
├── _includes/
│   └── author-bio.md    # About text
├── _layouts/
│   └── default.html     # Default HTML template
├── assets/
│   ├── css/
│   │   └── main.scss    # Main stylesheet
│   └── images/          # Profile photo, favicon, touch icon
├── 404.html             # Not-found page
├── index.html           # Homepage with About/Resume views
├── CNAME                # Custom domain
└── Gemfile              # Ruby dependencies
```

## License

MIT
