# Backplane

A static notebook-style site for documenting work in embedded systems, electronics, mechanics, and vehicle dynamics.

This repository is built using Jekyll and hosted via GitHub Pages.  
Entries are organized chronologically and by thematic clusters.

The goal is to keep publishing lightweight:
- Minimal structure
- Simple Markdown files
- No backend
- No complex tooling

---

## Structure Overview

```
.
├── _posts/           # Notebook entries
├── _data/            # Cluster definitions and site data
├── about.md          # Preface / About page
├── _config.yml       # Site configuration
├── assets/           # CSS and static assets
```

---

## Creating a New Entry

All entries live inside the `_posts/` directory.

### Step 1: Create a new file

File name format:

```
YYYY-MM-DD-title.md
```

Example:

```
2026-02-06-stm32-timer-notes.md
```

The date is required for Jekyll to process the post correctly.

---

### Step 2: Add front matter

At the top of the file, include:

```yaml
---
layout: post
title: "STM32 Timer Notes"
date: 2026-02-06
clusters: [silicon, circuits]
status: draft
---
```

Fields explained:

- `layout`: leave as `post`
- `title`: entry title
- `date`: must match filename date
- `clusters`: must match slugs defined in `_data/clusters.yml`
- `status`: optional (e.g. draft, fragment, complete)

---

### Step 3: Write content in Markdown

Markdown basics:

```
# Heading 1
## Heading 2

Regular paragraph text.

- Bullet point
- Another point

`inline code`
```

Code blocks:

```c
uint32_t timer = 0;
```

Save → Commit → Push.  
GitHub Pages will rebuild automatically.

---

## Editing the About Page

Open:

```
about.md
```

Modify the Markdown content below the front matter.

Example structure:

```yaml
---
layout: page
title: Preface
permalink: /about/
---
```

Edit the text beneath it.

Commit and push changes.

---

## Managing Clusters

Clusters are defined in:

```
_data/clusters.yml
```

Example:

```yaml
- slug: silicon
  name: Silicon & State Machines
  description: "STM32, CH32V, deterministic control"
```

To add a new cluster:

1. Add a new block with:
   - unique `slug`
   - display `name`
   - short `description`
2. Save and commit.

No template edits required.

---

## Adding Images to an Entry

1. Place images inside:

```
assets/images/
```

2. Reference in Markdown:

```markdown
![Alt text](/assets/images/example.png)
```

Commit and push.

---

## Changing the Color Theme

Theme colors are defined in:

```
assets/css/style.scss
```

Look for variables such as:

```scss
$background-color: #f5e9d4;
$text-color: #3b2f2f;
$accent-color: #6b4f3f;
```

Modify the hex values as desired.

Common edits:
- Background color
- Text color
- Accent color

Commit and push to apply changes.

---

## Local Development (Optional)

If running locally:

```
bundle install
bundle exec jekyll serve
```

Site will be available at:

```
http://localhost:4000
```

---

## Notes

- No analytics.
- No comment system.
- Minimal dependencies.
- Content-first workflow.
- Designed for incremental entries, not polished articles.

This repository is intentionally simple.
