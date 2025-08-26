# Personal Profile Site

A minimalist Jekyll-based personal profile website with About and Resume sections.

## Prerequisites

- Ruby 2.7.0 or higher
- Bundler gem (`gem install bundler`)

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