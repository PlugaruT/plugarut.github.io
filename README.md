# Personal Profile Site

A minimalist Jekyll-based personal profile website with About and Resume sections.

## Prerequisites

- Ruby 3.3 or higher (matches GitHub Pages; the macOS system Ruby is too old)
- Bundler gem (`gem install bundler`)

Alternatively, use Docker (no local Ruby needed):

```bash
docker run --rm -p 4000:4000 -v "$PWD":/srv -w /srv ruby:3.3 \
  bash -c 'bundle install && bundle exec jekyll serve --host 0.0.0.0'
```

## Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd about-me
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
bundle exec jekyll build
```

The static site will be generated in the `_site` directory.

## Configuration

Edit `_config.yml` to customize:
- Personal information (name, bio, location)
- Social media links
- Work experience
- Education details
- Theme colors

## Project Structure

```
├── _config.yml          # Site configuration
├── _layouts/            # Page layouts
│   └── default.html     # Default HTML template
├── _site/              # Generated site (git ignored)
├── assets/             
│   ├── css/            
│   │   └── main.scss   # Main stylesheet
│   └── images/         
│       └── profile.jpg # Profile photo
├── index.html          # Homepage with About/Resume views
├── Gemfile             # Ruby dependencies
└── README.md          # This file
```

## License

MIT