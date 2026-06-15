# Icey Theme - Quick Start

A minimal, clean Hugo theme with grid background.

## Quick Start

### 1. Create a new Hugo site

```bash
hugo new site my-blog
cd my-blog
```

### 2. Install the theme

```bash
git clone https://github.com/IceySwan/icey.git themes/icey
```

### 3. Copy the template site

Copy all files from `themes/icey/templatesite/` to your site root:

```bash
# Linux / macOS
cp -r themes/icey/templatesite/* .

# Windows (PowerShell)
Copy-Item -Path themes\icey\templatesite\* -Destination . -Recurse -Force
```

This will set up:
- `hugo.toml` — site configuration
- `data/site.json` — author name, bio, site start date
- `assets/readme.md` — homepage intro section (rendered via Markdown)
- `content/` — pages and example posts

### 4. Customize

- Edit `hugo.toml` to change `baseURL`, `title`, and menu items
- Edit `data/site.json` to set your author name and bio
- Edit `assets/readme.md` for the homepage self-introduction
- Replace `assets/logo.png` and `assets/avatar.png` with your own images
- Write new posts in `content/posts/`

### 5. Run locally

```bash
hugo server
```

Visit `http://localhost:1313` to preview.

### 6. Build for production

```bash
hugo
```

Output goes to the `public/` directory. **Always use `hugo` (not `hugo server`) when deploying.**

## Directory Structure

```
.
├── hugo.toml              # Site configuration
├── data/
│   └── site.json          # Author info (name, bio, start date)
├── assets/
│   ├── readme.md          # Homepage intro (Markdown)
│   ├── logo.png           # Site logo (favicon)
│   └── avatar.png         # Profile avatar
├── content/
│   ├── _index.md          # Homepage
│   ├── about.md           # About page
│   ├── archive/
│   │   └── _index.md      # Archive page
│   ├── notes/
│   │   └── _index.md      # Notes page
│   └── posts/
│       ├── hello-world.md # Example post
│       └── markdown-syntax.md  # Markdown demo
└── themes/
    └── icey/              # Theme files
```

## Configuration

### hugo.toml

| Key | Description |
| --- | --- |
| `baseURL` | Your site URL (e.g. `https://example.com/`) |
| `title` | Site title shown in navbar and footer |
| `theme` | Must be `icey` |
| `params.description` | Site meta description |
| `params.logo` | Logo filename in `assets/` |
| `params.avatar` | Avatar filename in `assets/` |
| `params.aboutFile` | Homepage intro file in `assets/` |
| `params.homePostsCount` | Number of posts on homepage |

### data/site.json

| Key | Description |
| --- | --- |
| `author` | Author name displayed on homepage |
| `bio` | One-line bio displayed on homepage |
| `since` | Site start date (used for uptime counter) |

## Writing Posts

Create a new post:

```bash
hugo new posts/my-post.md
```

### Frontmatter

```yaml
---
title: "Post Title"
date: "2025-01-01"
lastmod: "2025-01-01"
author: Your Name
categories:
- Misc
tags:
- example
summary: "A short description."
draft: false
Toc: true          # Show table of contents
hidemeta: false    # Hide date/author meta
---
```

## License

MIT
