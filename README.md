# How to run Hugo server (WSL)
```bash
hugo server --disableFastRender
```

## How to add files to Hugo

### 1. Static files (PDF, images, downloads) - `static/` directory

**How to do it:**
- Place files in `static/` (e.g., `static/cv.pdf`, `static/images/photo.jpg`)
- Hugo automatically serves them at root URL: `/cv.pdf`, `/images/photo.jpg`

**How to display:**
```yaml
# In hugo.yaml - add to menu
menu:
  main:
    - name: CV
      url: /cv.pdf
```

```markdown
# In .md files - link or display
[Download CV](/cv.pdf)
![My Photo](/images/photo.jpg)
```

### 2. Content pages (About, Blog posts) - `content/` directory

**How to do it:**
- Create markdown files in `content/` 
  - `content/about.md` → URL: `/about/`
  - `content/posts/my-post.md` → URL: `/posts/my-post/`

**Example creating a new page:**
```markdown
---
title: "My Page"
date: 2025-12-20
draft: false
---

Your page content goes here.
```

**How to display:**
```yaml
# Add to menu in hugo.yaml
menu:
  main:
    - name: My Page
      url: /my-page/
```

**Summary:**
- `static/` = downloadable files, images (not processed)
- `content/` = HTML pages rendered by Hugo from Markdown