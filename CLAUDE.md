# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hugo static site built with the Hugoplate theme, using Tailwind CSS v4.0 for styling. The site follows Hugo's standard directory structure and uses Hugo modules for theme management.

## Architecture

### Hugo Structure
- **Content**: Markdown files in `content/` directory drive the site structure
- **Theme**: Uses custom `hugoplate` theme located in `themes/hugoplate/`
- **Configuration**: Main config in `hugo.toml`, with additional configs in `config/_default/`
- **Assets**: Tailwind CSS, JavaScript, and static assets managed through Hugo's asset pipeline
- **Data**: Site data stored in `data/` directory for theme configuration
- **Layouts**: Theme layouts in `themes/hugoplate/layouts/`

### Key Configuration Files
- `hugo.toml`: Main Hugo configuration including baseURL, theme, modules, and build settings
- `config/_default/params.toml`: Site parameters, theme settings, plugins, and feature toggles
- `config/_default/menus.en.toml`: Navigation menu structure
- `package.json`: Node.js dependencies for Tailwind CSS and development tools

### Theme System
- Uses Hugo modules for theme management
- Theme includes pre-built layouts for blog, about, contact, and other standard pages
- Supports multiple authors, dark mode, search functionality, and responsive design
- Integrates Font Awesome icons, Swiper.js for carousels, and Glightbox for image galleries

## Development Commands

### Setup and Development
```bash
# Install Node.js dependencies
npm install

# Start development server with live reload
npm run dev

# Start development server with production environment and minification
npm run preview
```

### Build Commands
```bash
# Build for production with optimization
npm run build

# Format code with Prettier
npm run format
```

### Theme Management
```bash
# Update Hugo modules (theme and dependencies)
npm run update-modules

# Set up project structure (run after cloning)
npm run project-setup

# Update theme to latest version
npm run update-theme

# Remove dark mode functionality
npm run remove-darkmode
```

## Site Configuration

### Key Settings to Modify
- **baseURL**: Set in `hugo.toml` - currently set to "/igi/" (update for deployment)
- **Site Title**: Change "Hugoplate" in `hugo.toml`
- **Logo**: Replace `images/logo.png` and update `config/_default/params.toml`
- **Contact Form**: Update `contact_form_action` in `params.toml` (supports Airform.io or Formspree)
- **Analytics**: Set Google Analytics ID in `hugo.toml` services section

### Content Management
- Blog posts go in `content/blog/`
- Pages use front matter to control layout and features
- Author information managed in `data/authors.json`
- Theme colors and fonts configurable in `data/theme.json`

## Deployment

The site supports multiple deployment platforms:
- **GitHub Pages**: Uses `.github/workflows/hugo.yml` for automated deployment
- **Netlify**: Configured via `netlify.toml`
- **Vercel**: Uses `vercel.json` and `vercel-build.sh`
- **AWS Amplify**: Configured via `amplify.yml`
- **GitLab CI**: Uses `.gitlab-ci.yml`

### Prerequisites
- Hugo Extended v0.144+
- Node.js v22+
- Go v1.24+ (for Hugo modules)

### Important Notes
- Always update `baseURL` in `hugo.toml` before deployment
- The build process generates optimized assets in `public/` directory
- Hugo stats are tracked in `hugo_stats.json` for Tailwind CSS purging
- Theme uses Hugo's asset pipeline for CSS/JS bundling and minification