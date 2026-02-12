# CLAUDE.md - AI Assistant Guide for weituo12321.github.io

## Project Overview

This is **HardCoreAI**, a static blog focused on machine learning education, authored by Weituo Hao. It is built with Pelican (a Python static site generator) and deployed to GitHub Pages. The repository contains only pre-generated HTML output — no source markdown/RST files or Pelican configuration files are present.

- **Site URL**: https://weituo12321.github.io/
- **Generator**: Pelican (Python)
- **Theme**: blueidea (customized version of Clean Blog)
- **Hosting**: GitHub Pages (served from `master` branch)
- **Author**: Weituo Hao (@VicWeituo on Twitter, weituo12321 on GitHub)

## Repository Structure

```
/
├── *.html                  # Pre-generated blog post pages (root level)
├── author/                 # Author archive pages
├── category/               # Category archive pages
├── tag/                    # Tag archive pages
├── pages/                  # Static pages (Announcement, Introduction, etc.)
├── feeds/                  # Atom/RSS feed (all.atom.xml)
├── images/                 # Content images (ML diagrams, charts)
└── theme/                  # Frontend assets
    ├── css/                # Stylesheets (Bootstrap, Clean Blog, Pygments)
    │   └── code_blocks/    # Code syntax highlighting themes
    ├── js/                 # JavaScript (jQuery, Bootstrap, Clean Blog)
    ├── fonts/              # Web fonts (Glyphicons, Ubuntu, Holtwood)
    └── images/             # Theme images and social media icons
        └── icons/          # Social media icon PNGs
```

## Technology Stack

| Layer           | Technology                                      |
|-----------------|------------------------------------------------|
| Site Generator  | Pelican (Python)                                |
| Templates       | Jinja2                                          |
| CSS Framework   | Bootstrap 3.x                                   |
| JS Libraries    | jQuery, Bootstrap JS, Clean Blog JS             |
| Math Rendering  | MathJax (loaded from CDN)                       |
| Icons           | Font Awesome 4.1.0 (CDN), Glyphicons (local)   |
| Fonts           | Google Fonts (Lora, Open Sans)                  |
| Code Highlight  | Pygments (darkly theme active)                  |
| Hosting         | GitHub Pages                                    |

## Content Organization

### Categories
- **Machine_Learning** — primary category with classification and regression articles
- **Announcement** — site announcements
- **About** — about page
- **trial** — test/miscellaneous content

### Tags
- `classification` (5 articles) — linear classifiers, decision trees, boosting, evaluation, preprocessing
- `regression` (6 articles) — simple, multiple, ridge, lasso, nearest-neighbor/kernel regression
- `data-science`, `pelican`, `publishing`

### Article Naming Convention
Blog post HTML files follow the pattern:
- `classification_N_topic_name.html`
- `regression_N_topic_name.html`

where `N` is a sequence number within the series.

## Development Workflow

### Important: No Build Pipeline
This repository contains **only compiled HTML output**. There is:
- No `pelicanconf.py` or `publishconf.py`
- No `Makefile` or `fabfile.py`
- No CI/CD configuration (no GitHub Actions, Travis CI, etc.)
- No source markdown or reStructuredText files

Content was generated locally with Pelican, then the output was committed directly.

### Deployment
Push to `master` triggers GitHub Pages deployment automatically. No build step is needed — the HTML files are served as-is.

### To Add or Modify Content
Since source files are not in this repository, edits must be made directly to the HTML files. Each HTML page follows this structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Meta tags, CSS links (main.css, Bootstrap, Clean Blog, darkly.css) -->
    <!-- Google Fonts, Font Awesome CDN, MathJax CDN -->
</head>
<body>
    <!-- GitHub fork ribbon -->
    <!-- Navigation: site title "HardCoreAI", category links -->
    <!-- Page header with background image -->
    <!-- Main content area -->
    <!-- Sidebar: blogroll, social links -->
    <!-- Footer: Pelican & theme attribution -->
    <!-- JS: jQuery, Bootstrap, Clean Blog -->
</body>
</html>
```

## Key Conventions

1. **HTML-only edits** — All content changes are direct HTML modifications; there is no build step.
2. **Consistent layout** — Every page shares the same nav, header, sidebar, and footer structure.
3. **Bootstrap grid** — Content uses Bootstrap 3.x grid system (`container`, `row`, `col-*` classes).
4. **MathJax for equations** — Mathematical notation uses MathJax loaded from CDN.
5. **Pygments for code** — Code blocks use Pygments CSS classes with the `darkly` theme (`theme/css/code_blocks/darkly.css`).
6. **Image assets** — Content images go in `/images/`; theme images go in `/theme/images/`.
7. **No minification pipeline** — Both minified and unminified versions of Bootstrap/jQuery are present; pages reference specific versions directly.

## Common Tasks for AI Assistants

### Adding a new blog post
1. Copy an existing article HTML file as a template.
2. Update the `<title>`, meta tags, header, and article content.
3. Update `index.html` to include the new post in the listing.
4. Update relevant `category/`, `tag/`, and `author/` archive pages.
5. Place any new images in `/images/`.

### Fixing styling issues
- Primary stylesheet: `theme/css/main.css`
- Bootstrap overrides: `theme/css/clean-blog.css`
- Code block themes: `theme/css/code_blocks/darkly.css` (active)

### Updating navigation
Navigation links are hardcoded in each HTML file's `<nav>` section. Changes must be applied across all pages.

## Caveats

- **Duplicate/variant files exist** — Some articles have multiple versions (e.g., `classification_2_decision_trees.html` and `classification_3_decision_trees.html`). Take care not to modify the wrong variant.
- **No templating at build time** — Since there's no build system, global changes (nav, footer, etc.) require editing every HTML file.
- **Legacy codebase** — Content dates from 2016; libraries (Bootstrap 3, jQuery 1.x, Font Awesome 4.1) are outdated but functional.
- **macOS artifacts** — `.DS_Store` files are present in the repository.
