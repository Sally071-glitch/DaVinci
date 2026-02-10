# DaVinci's Marginallia

A static notebook-style site built with Jekyll and hosted via GitHub Pages.

Entries are organized by time and by thematic clusters.

---

# PART 1 — HOW TO USE (Adding Content)

This section is for writing and editing content.

---

## 1. Creating a New Errata

All entries live inside:

```
_entries/
```

### Step 1 — Create a new file

Filename format:

```
YYYY-MM-DD-title.md
```

Example:

```
2026-02-06-stm32-timer-notes.md
```

The date must match the date in the front matter.

---

### Step 2 — Add front matter

At the top of the file:

```yaml
---
layout: entry
date: 2026-02-06
clusters:
  - silicon
  - powertrain
excerpt: |
  Short summary of what this entry contains.
---
```

Fields explained:

- `layout`: always `entry`
- `date`: must match filename date
- `clusters`: must match slugs defined in `_data/clusters.yml`
- `excerpt`: short summary shown in listings

---

### Step 3 — Write content in Markdown

Basic Markdown:

```
# Heading
## Subheading

Regular text.

- Bullet point
- Another point

`inline code`
```

Code block:

```c
uint32_t timer = 0;
```


## 2. Editing the About Page

Open:

```
about.md
```

Edit the content below the front matter.

Commit and push changes.

---

## 3. Managing Clusters

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

# PART 2 — DEVELOPER GUIDE

This section explains the repository structure and customization.

---

## Repository Structure

```
.
├── _entries/            # All notebook entries
├── _data/               # YAML data (clusters, quotes, etc.)
├── _layouts/            # Page and entry templates
├── _includes/           # Reusable template components
├── assets/
│   ├── css/             # Styling (SCSS)          
├── about.md             # Preface page
├── _config.yml          # Site configuration
└── README.md
```

---

## Layout System

Entries use:

```
layout: entry
```

Defined in:

```
_layouts/entry.html
```

To modify entry structure:
- Edit `_layouts/entry.html`
- Adjust metadata rendering (clusters, excerpt, date)
- Modify cluster links or grouping logic

---

## Cluster System

Clusters are defined in:

```
_data/clusters.yml
```

Each cluster must contain:

- `slug`
- `name`
- `description`

Entries reference clusters via:

```yaml
clusters:
  - silicon
  - powertrain
```

If a slug does not exist in `_data/clusters.yml`, it will not render properly.

---

## Changing the Color Theme

Primary styles are located in:

```
assets/css/style.scss
```

Look for variables such as:

```scss
$background-color: #f5e9d4;
$text-color: #3b2f2f;
$accent-color: #6b4f3f;
```

Modify these values.

Commit and push to apply changes.

---

## Adding New Data Files

Custom site data can be added inside:

```
_data/
```

Example:

```
_data/marginalia.yml
```

---

## Local Development

To run locally:

1. Install dependencies:

```
bundle install
```

2. Start local server:

```
bundle exec jekyll serve
```

3. Open:

```
http://localhost:4000
```

---

## Modifying Structure

To modify:

- Navigation → `_includes/`
- Layouts → `_layouts/`
- Home logic → `index.html`
- Cluster grouping logic → templates referencing `site.data.clusters`

Changes require commit + push to deploy.

---

## Deployment

Deployment is handled automatically via GitHub Pages.

Every push to the default branch triggers rebuild.

---

## Design Principles

- Content-first
- Minimal abstraction
- No analytics
- No comments
- No dynamic backend
- Static, transparent structure

Intended for incremental, technical entries.
