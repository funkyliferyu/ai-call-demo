# CLAUDE.md

This file provides guidance for AI assistants working on this repository.

## Project Overview

`ai-call-demo` is a static GitHub Pages landing page for **스마트 콜키퍼** (Smart Call Keeper), an SK Telecom product. The page displays a product image that links to the SKT T-world product purchase page.

- **Live URL**: https://funkyliferyu.github.io/ai-call-demo/
- **Product link target**: https://m.tworld.co.kr/product/callplan?prod_id=NA00004343

## Repository Structure

```
ai-call-demo/
├── index.html   # Single-page HTML landing page (Korean language)
├── main.png     # Main product image (1125×3407px, ~1.9MB) — the primary page content
├── 1.png        # Open Graph social sharing image (1200×630px, ~198KB)
└── README.md    # Minimal project readme
```

There is no build system, package manager, framework, or JavaScript. This is a pure static site.

## Tech Stack

- **HTML/CSS only** — no JavaScript, no dependencies, no build step
- **GitHub Pages** for hosting (deploys automatically from the `main` branch)
- **Language**: Korean (`lang="ko"`)

## Key Conventions

- The page is intentionally minimal: the entire UI is a full-width clickable image.
- `main.png` is the visual "content" of the page. Replacing it updates the page appearance.
- `1.png` is used exclusively as the Open Graph (`og:image`) preview for social sharing.
- All `og:*` meta tags reference absolute URLs pointing to the GitHub Pages domain.

## Development Workflow

This is a static site with no build or test pipeline. Typical changes involve:

1. **Updating content**: Replace `main.png` and/or `1.png` with new images (keep the same filenames).
2. **Updating metadata**: Edit `<meta>` tags in `index.html` (title, description, OG tags).
3. **Changing the link target**: Update the `href` on the `<a>` tag in `index.html`.

### Deployment

Pushing to the `main` branch on GitHub triggers GitHub Pages to redeploy automatically. There is no CI/CD configuration file in the repository.

### Branches

| Branch | Purpose |
|--------|---------|
| `master` | Local default branch |
| `main` (remote) | GitHub Pages source — changes here go live |
| `claude/*` | AI-assistant feature branches |

## Constraints & Notes

- **No JavaScript**: Keep the page dependency-free. Do not introduce JS without a clear reason.
- **Image sizes**: `main.png` is intentionally tall (scroll-through infographic format). Maintain this format when replacing images.
- **No linter/formatter**: There is no configured linter, formatter, or test suite. HTML changes can be validated manually or with an HTML validator.
- **Encoding**: The HTML file uses UTF-8. Korean characters must be preserved as-is; do not escape them.
- **No `.gitignore`**: The repo tracks all files. Avoid committing OS artifacts (`.DS_Store`, `Thumbs.db`).
