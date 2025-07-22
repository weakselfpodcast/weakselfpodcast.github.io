# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based static website for the **weak self podcast** - a Chinese-language podcast about iOS/Apple development hosted by Taiwanese engineers. The site serves as the official website and episode archive, deployed via GitHub Pages.

## Architecture & Structure

### Jekyll Site Structure
- **_config.yml**: Main Jekyll configuration with "texture" theme settings
- **_layouts/**: HTML templates for different page types
  - `episode.html`: Template for individual episode pages with embedded Apple Podcasts player
  - `home.html`: Homepage layout showing recent episodes
  - `list.html`, `page.html`, `post.html`: Other page templates
- **_includes/**: Reusable HTML components (headers, navigation, footer)
- **_posts/**: Episode markdown files following Jekyll naming convention (YYYY-MM-DD-{episode-number}.md)
- **_sass/**: Sass/SCSS stylesheets with texture theme customizations
- **assets/**: Static assets (CSS, JavaScript, images, fonts)

### Content Management
- Episodes are stored as markdown files in `_posts/` with YAML front matter
- Episode files follow pattern: `YYYY-MM-DD-{episode-number}.md` 
- Each episode includes embedded Apple Podcasts player iframe and structured show notes
- Main index page (`index.md`) manually lists recent episodes by season

### Theme & Styling
- Uses "texture" Jekyll theme with black color scheme
- Custom SCSS files in `_sass/` directory
- Font icons via Fontello
- Responsive design with texture backgrounds

## Common Commands

### Development
```bash
# Install dependencies
bundle install

# Serve site locally with auto-rebuild
bundle exec jekyll serve

# Build site for production
bundle exec jekyll build

# Serve with drafts included
bundle exec jekyll serve --drafts

# Serve with incremental builds (faster)
bundle exec jekyll serve --incremental
```

### Content Management
- Episodes are manually created as markdown files in `_posts/`
- Update `index.md` manually to add new episodes to season listings
- Episode URLs follow pattern: `/episodes/{episode-number}`

## Key Files for Editing

### Adding New Episodes
1. Create new file in `_posts/` following naming pattern
2. Use existing episodes as templates for front matter structure
3. Include Apple Podcasts embed iframe
4. Add chapter markers and show notes in markdown
5. Update `index.md` to include new episode in appropriate season

### Site Configuration
- `_config.yml`: Site metadata, theme settings, social links
- `index.md`: Homepage content and episode listings
- `_layouts/episode.html`: Episode page template and player embed

## Deployment

Site is automatically deployed via GitHub Pages when changes are pushed to the master branch. No additional build or deployment steps required.

## RSS & Distribution

Episodes are distributed via Substack RSS feed (https://api.substack.com/feed/podcast/5083012.rss) rather than Jekyll's built-in feed generation.