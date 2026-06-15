---
title: "Markdown Syntax"
date: "2025-01-02"
lastmod: "2025-01-02"
author: Your Name
categories:
- Misc
tags:
- markdown
- demo
summary: "A showcase of markdown syntax supported by the Icey theme."
draft: false
Toc: true
hidemeta: false
---

This post demonstrates all markdown features supported by the Icey theme.

## Text Formatting

This is **bold text** and this is *italic text*. You can also use ~~strikethrough~~.

## Blockquote

> A blockquote is useful for highlighting important information or quoting sources.

## Code

Inline code: `print("hello")`

Code block with syntax highlighting:

```python
def greet(name: str) -> str:
    """Return a greeting string."""
    return f"Hello, {name}!"

print(greet("World"))
```

## Lists

### Unordered List

- First item
- Second item
  - Nested item A
  - Nested item B
- Third item

### Ordered List

1. Step one
2. Step two
3. Step three

## Table

| Feature | Supported |
| ------- | --------- |
| Headings | Yes |
| Code blocks | Yes |
| Tables | Yes |
| Images | Yes |

## Images

Place images in the `assets/` or `static/` directory and reference them:

```markdown
![alt text](/image.png)
```

## Links

- Internal: [About](/about)
- External: [Hugo](https://gohugo.io/)

## Math

Inline math: $E = mc^2$

## Horizontal Rule

---

That's it! You now have a reference for all the markdown features available in this theme.
