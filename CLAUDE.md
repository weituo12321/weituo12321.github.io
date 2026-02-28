# CLAUDE.md - AI Assistant Guide for weituo12321.github.io

## Project Overview

This is **HardCoreAI**, an academic portfolio and machine learning blog authored by Weituo Hao. The site uses an **academicpages-inspired** layout (based on the Minimal Mistakes Jekyll theme aesthetic) and is deployed to GitHub Pages as static HTML. There is no build system — all HTML files are edited and committed directly.

- **Site URL**: https://weituo12321.github.io/
- **Design**: Academicpages / Minimal Mistakes inspired (two-column layout with sidebar)
- **Hosting**: GitHub Pages (served from `master` branch)
- **Author**: Weituo Hao (@VicWeituo on Twitter, weituo12321 on GitHub)

## Repository Structure

```
/
├── index.html                      # Homepage / About page
├── blog.html                       # Blog posts archive (year-grouped listing)
├── publications.html               # Publications (placeholder)
├── talks.html                      # Talks (placeholder)
├── teaching.html                   # Teaching (placeholder)
├── portfolio.html                  # Portfolio (placeholder)
├── cv.html                         # CV (placeholder)
├── classification_*.html           # Classification tutorial blog posts
├── regression_*.html               # Regression tutorial blog posts
├── introduction.html               # Introduction blog post
├── images/                         # Content images (ML diagrams, charts)
├── feeds/                          # Atom/RSS feed
├── author/                         # Legacy author archive pages
├── category/                       # Legacy category archive pages
├── tag/                            # Legacy tag archive pages
├── pages/                          # Legacy static pages
└── theme/                          # Frontend assets
    ├── css/
    │   ├── academicpages.css       # PRIMARY stylesheet (academicpages layout)
    │   ├── code_blocks/darkly.css  # Code syntax highlighting (active)
    │   ├── main.css                # Legacy Pelican theme CSS
    │   ├── bootstrap*.css          # Legacy Bootstrap CSS
    │   └── clean-blog*.css         # Legacy Clean Blog CSS
    ├── js/                         # JavaScript (legacy jQuery, Bootstrap)
    ├── fonts/                      # Web fonts
    └── images/                     # Theme images and icons
```

## Technology Stack

| Layer           | Technology                                              |
|-----------------|---------------------------------------------------------|
| Layout          | Custom academicpages-style (Minimal Mistakes inspired)  |
| CSS             | Custom `academicpages.css` + code_blocks/darkly.css     |
| Icons           | Font Awesome 6.x (CDN) + Academicons (CDN)             |
| Math Rendering  | MathJax 2.7 (CDN)                                      |
| Code Highlight  | Pygments CSS (darkly theme)                             |
| Hosting         | GitHub Pages                                            |

## Site Navigation

The top navigation bar links to:
1. **Home** (`/`) — About page with author bio and ML series overview
2. **Publications** (`/publications.html`) — Placeholder
3. **Talks** (`/talks.html`) — Placeholder
4. **Teaching** (`/teaching.html`) — Placeholder
5. **Portfolio** (`/portfolio.html`) — Placeholder
6. **Blog Posts** (`/blog.html`) — Archive of all ML tutorial posts
7. **CV** (`/cv.html`) — Placeholder

## Page Layout

Every page follows a consistent two-column layout:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Meta, academicpages.css, Font Awesome 6, Academicons, MathJax -->
</head>
<body>
    <div class="masthead">         <!-- Top navigation bar -->
    <div id="main">
        <div class="sidebar">     <!-- Left: avatar, name, bio, social links -->
        <article class="page">    <!-- Right: page content -->
    </div>
    <footer class="page__footer"> <!-- Bottom footer -->
</body>
</html>
```

### Sidebar (appears on every page)
- Author avatar (GitHub avatar)
- Name: Weituo Hao
- Bio tagline
- Social links: Email, GitHub, Twitter

## Content Organization

### Blog Posts (canonical, listed on blog.html)

**Regression Series:**
1. `regression_1_simple_regression.html` — Simple Regression (March 21, 2016)
2. `regression_2_multiple_regression.html` — Multiple Regression (April 02, 2016)
3. `regression_3_simple_regression.html` — Assessing Performance (April 05, 2016)
4. `regression_4_ridge_regression.html` — Ridge Regression (April 08, 2016)
5. `regression_5_lasso.html` — LASSO (April 15, 2016)
6. `regression_6_nearest-neighbor-and-kernel-regression.html` — Nearest Neighbor & Kernel (April 17, 2016)

**Classification Series:**
1. `classification_1_linear_classifiers.html` — Linear Classifiers (April 23, 2016)
2. `classification_2_linear_classifiers_2.html` — Linear Classifiers / MLE (April 23, 2016)
3. `classification_3_decision_trees.html` — Decision Trees (April 27, 2016)
4. `classification_4_boosting.html` — Boosting (April 28, 2016)
5. `classification_5_large_datasets_and_evaluation.html` — Large Datasets & Evaluation (April 30, 2016)
6. `classification_6_data_preprocessing.html` — Data Preprocessing (May 05, 2016)

**Other:**
- `introduction.html` — Blog introduction (March 20, 2016)

### Legacy / Duplicate Files (not linked from blog.html)
These files exist but are duplicates or variants from the original Pelican build:
- `classification_2_decision_trees.html` (duplicate of #3)
- `classification_4_decision_boosting.html` (duplicate of #4)
- `classification_4_large_datasets_and_messurments.html` (empty)
- `classification_5_large_datasets_and_messurments.html` (duplicate of #5)
- `Announcement.html`, `nothingnew.html`, `re.html` (test posts)
- `index2.html`, `archives.html`, `authors.html`, `categories.html`, `tags.html` (legacy archive pages)

## Development Workflow

### No Build Pipeline
This repository contains **only static HTML output**. There is no build system, no Jekyll, no Pelican config. All changes are direct HTML edits.

### Deployment
Push to `master` triggers GitHub Pages deployment automatically.

### To Add or Modify Content
Edit HTML files directly. Every page must include:
1. The `<head>` section with `academicpages.css`, Font Awesome, and MathJax references
2. The masthead navigation bar
3. The sidebar with author info
4. The main content area
5. The footer

## Key Conventions

1. **HTML-only edits** — All content changes are direct HTML modifications; no build step.
2. **Consistent layout** — Every page uses the same masthead, sidebar, and footer.
3. **academicpages.css** — The primary stylesheet at `theme/css/academicpages.css`.
4. **MathJax for equations** — Mathematical notation uses MathJax loaded from CDN.
5. **Pygments for code** — Code blocks use Pygments CSS classes with `darkly` theme.
6. **Image assets** — Content images go in `/images/`; theme images go in `/theme/images/`.
7. **Navigation is hardcoded** — Nav links exist in every HTML file; changes require editing all pages.

## Common Tasks for AI Assistants

### Adding a new blog post
1. Copy an existing blog post HTML file (e.g., `regression_1_simple_regression.html`) as a template.
2. Update `<title>`, `<h1 class="page__title">`, date in `page__meta`, and the content in `page__content`.
3. Add an entry to `blog.html` in the correct chronological position.
4. Place any new images in `/images/`.

### Adding content to placeholder pages
Edit the corresponding HTML file (`publications.html`, `talks.html`, `teaching.html`, `portfolio.html`, `cv.html`) and replace the `placeholder-notice` div with actual content.

### Fixing styling issues
- Primary stylesheet: `theme/css/academicpages.css`
- Code block theme: `theme/css/code_blocks/darkly.css`

### Updating navigation or sidebar
Navigation and sidebar HTML are duplicated in every page file. Global changes require editing all HTML files.

## Caveats

- **Duplicate files exist** — Several legacy article variants remain in the repo. The canonical versions are listed above and linked from `blog.html`.
- **No templating** — Global changes (nav, sidebar, footer) require editing every HTML file individually.
- **Legacy assets** — Old Pelican theme files (Bootstrap 3, jQuery, Clean Blog CSS/JS) remain in `/theme/` but are no longer referenced by the active pages.
- **macOS artifacts** — `.DS_Store` files are present in the repository.
