# Icey Theme Configuration

A clean, minimal Hugo theme with grid background.

---

## Quick Start

```toml
# hugo.toml
theme = 'icey'
```

## hugo.toml

### Site Basic

```toml
baseURL = 'https://example.org/'
locale = 'zh-cn'
title = 'Icey Swan'
theme = 'icey'
enableRobotsTXT = true
summarylength = 70
```

| Field | Description |
|-------|-------------|
| `baseURL` | Site base URL, used for RSS/Sitemap/feed links |
| `locale` | Language code, affects HTML `lang` attribute |
| `title` | Site title, shown in footer copyright and browser tab |
| `theme` | Must be `'icey'` |
| `enableRobotsTXT` | Generate `robots.txt` for search engines |
| `summarylength` | Auto-summary character count (when no `summary` in front matter) |

### Theme Params

```toml
[params]
  description = "Writing code and words, one day at a time."
  logo = "logo.png"
  avatar = "avatar.png"
  aboutFile = "readme.md"
  homePostsCount = 5
```

| Field | Default | Description |
|-------|---------|-------------|
| `description` | — | Site description, shown in meta tags |
| `logo` | `logo.png` | Favicon in `assets/`, supports `png/jpg/svg` |
| `avatar` | `avatar.png` | Profile avatar in `assets/`, supports `png/jpg/svg` |
| `aboutFile` | `readme.md` | Homepage about section file in `assets/`, supports Markdown |
| `homePostsCount` | `5` | Number of recent posts on homepage |

### Menu

```toml
[menu]
  [[menu.main]]
    identifier = "home"
    name = "Home"
    url = "/"
    weight = 1
  [[menu.main]]
    identifier = "archive"
    name = "Archive"
    url = "/archive/"
    weight = 10
```

| Field | Description |
|-------|-------------|
| `identifier` | Unique menu identifier |
| `name` | Display text |
| `url` | Link URL |
| `weight` | Sort order (lower = further left) |

Menu items are rendered left-to-right by `weight` in the top navigation bar. Menu text uses the heading font (LXGW WenKai).

### Markup

```toml
[markup]
  [markup.tableOfContents]
    startLevel = 2
    endLevel = 3
  [markup.highlight]
    style = "github"
```

| Field | Description |
|-------|-------------|
| `startLevel` | TOC minimum heading level |
| `endLevel` | TOC maximum heading level |
| `style` | Code highlight style (see [Chroma styles](https://xyproto.github.io/splash/docs/)) |

### Output Formats

```toml
[outputs]
  home = ["HTML", "RSS", "Sitemap"]
  section = ["HTML", "RSS"]

[sitemap]
  filename = "sitemap.xml"
  changefreq = "weekly"
  priority = 0.5

[rss]
  limit = 20
```

---

## data/site.json

Homepage profile data and site uptime configuration.

```json
{
    "author": "Icey Swan",
    "bio": "Breaking free, pursuing freedom.",
    "since": "2023-12-25"
}
```

| Field | Description |
|-------|-------------|
| `author` | Profile display name (fallback: `title` in hugo.toml) |
| `bio` | One-line bio, displayed right-aligned next to author name |
| `since` | Site start date, format `YYYY-MM-DD`, used for footer uptime counter and copyright year range |

---

## Content Structure

```
content/
├── posts/           # Blog posts, displayed on homepage and archive
│   └── hello-world.md
├── archive/         # Archive page (requires _index.md)
│   └── _index.md
├── note/            # Notes page (requires _index.md)
│   └── _index.md
└── about/           # About page (requires _index.md)
    └── _index.md
```

### Post Front Matter

```yaml
---
title: "Post Title"
date: 2026-06-07
lastmod: 2026-06-10
draft: false
tags: ["tag1", "tag2"]
summary: "Brief description shown on homepage"
---
```

| Field | Description |
|-------|-------------|
| `title` | Post title |
| `date` | Publication date |
| `lastmod` | Last modified date (optional), shown as "Edited: YYYY-MM-DD" when set and differs from `date` |
| `draft` | Set `true` to hide from production builds |
| `tags` | Tags array, shown as badges on homepage and post page |
| `summary` | Brief description, shown on homepage post list |
| `toc` | Set `false` to hide TOC for specific post (default: `true`) |

### Section Pages

Archive, Note, and About pages require an `_index.md` file in their directory:

```markdown
---
title: "Archive"
---
```

---

## Assets

All asset files are placed in `assets/` directory:

```
assets/
├── logo.png      # Site favicon (browser tab icon)
├── avatar.png    # Homepage profile avatar
└── readme.md     # Homepage about section (Markdown)
```

All filenames are configurable via `[params]` in `hugo.toml`. Supports any image format (`png`, `jpg`, `svg`) for `logo` and `avatar`. The `aboutFile` supports full Markdown syntax (links, lists, code blocks, images, etc.).

---

## Search

Press `/` to open the search overlay, `Esc` to close. Search uses Google site search as a fallback.

---

## Customization

### Colors

Override CSS variables in your own stylesheet or in `layouts/partials/head.html`:

```css
:root {
    --color-accent: #your-color;
    --color-bg: #your-bg;
}
```

### Layout Width

```css
:root {
    --max-width: 60vw;      /* Navigation and footer width */
    --content-width: 60vw;  /* Main content width */
    --toc-width: 220px;     /* TOC sidebar width */
}
```

### Fonts

Fonts are loaded from Google Fonts CDN. To change, edit the `@import` URL and CSS variables:

```css
:root {
    --font-heading: 'Your Heading Font', serif;
    --font-body: 'Your Body Font', sans-serif;
    --font-mono: 'Your Mono Font', monospace;
}
```
