# DaVinci's Notebook

A Jekyll-based static site designed like Leonardo da Vinci's notebooks: non-linear, thematic, and focused on the process of thinking rather than polished articles.

## Philosophy

This isn't a blog. It's a public notebook that reflects how a polymath actually works:

- **Non-linear:** Thoughts connect across disciplines
- **Thematic:** Ideas cluster naturally by subject
- **Fragmentary:** Not everything needs to be finished
- **Dated but not constrained:** Time stamps exist, but themes matter more

## Structure

- **Two reading modes:**
  - Chronological (default at `/`)
  - Clustered by theme (at `/themes.html`)
  
- **Minimal metadata:**
  - Date
  - Cluster(s)
  - Optional status (fragment, sketch, question, complete)

## Getting Started

### Prerequisites

- Ruby (2.7 or higher)
- Bundler

### Local Development

1. Clone this repository
2. Install dependencies:
   ```bash
   bundle install
   ```

3. Run the local server:
   ```bash
   bundle exec jekyll serve
   ```

4. Visit `http://localhost:4000`

### Adding a New Entry

Create a new file in `_entries/` with this format:

```markdown
---
layout: entry
title: "Your Entry Title" # Optional
date: YYYY-MM-DD
clusters:
  - cluster-slug
  - another-cluster-slug
excerpt: |
  Brief summary (optional)
status: fragment # or: sketch, question, complete
---

Your entry content here...
```

### Adding a New Cluster

Edit `_data/clusters.yml`:

```yaml
clusters:
  - slug: your-new-cluster
    name: Display Name
    description: "Brief description"
```

No template changes needed.

## Deployment

This site is designed for GitHub Pages:

1. Push to your repository
2. Enable GitHub Pages in repository settings
3. Set source to `main` branch, `/` (root)

## Customization

- **Colors:** Edit CSS variables in `assets/css/notebook.css`
- **Quotes:** Edit `_data/marginalia.yml`
- **Site metadata:** Edit `_config.yml`
- **About page:** Edit `about.md`

## Design Principles

- Structure over visual polish
- Fragments are features, not bugs
- Multiple reading paths (chronological vs. thematic)
- Cross-disciplinary by default
- Minimal, parchment-toned aesthetic

## License

MIT License - Use this however you like.

---

*"Learning never exhausts the mind."* — Leonardo da Vinci
