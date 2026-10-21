# Projects site

A minimal Jekyll site modeled on al-folio's projects page: a grid of project
cards grouped by category, each opening its own page.

```
_config.yml          site title, author, and the list of categories
index.html           the projects page (grid of cards)
_projects/*.md       one file per project = one card + one page
_layouts/            page templates (rarely need editing)
assets/css/style.css all styling (change --accent to recolor)
assets/img/          your images
```

## Add a project

Create a file in `_projects/`, e.g. `_projects/my-project.md`:

```markdown
---
title: My Project
description: One line shown on the card and under the page title.
img: assets/img/my-project.png    # card thumbnail (optional)
category: Jet Reconstruction      # must match a name in _config.yml
importance: 1                     # order within the category (1 = first)
math: true                        # only if the page uses $$ math $$
# redirect: https://example.com   # optional: card links elsewhere instead
---

Write the project page in Markdown here.
```

It appears at `/projects/my-project/`.

## Add or rename a category

Edit `project_categories` in `_config.yml`. Sections show in that order, and a
category with no projects is hidden.

## Images on a project page

```html
<div class="row">
  <img src="{{ '/assets/img/a.png' | relative_url }}" alt="">
  <img src="{{ '/assets/img/b.png' | relative_url }}" alt="">
</div>
<div class="caption">Caption text.</div>
```

Add `class="wide"` to one image to make it span two thirds.

## Math

Use `$$ ... $$` inline or on its own lines, and set `math: true` in the
project's front matter.

## Publish on GitHub Pages (free)

1. Create a GitHub repo and upload these files to it.
2. Repo **Settings → Pages → Source: Deploy from a branch**, pick `main` / `root`.
3. If the repo is named `USERNAME.github.io`, keep `baseurl: ""`.
   Otherwise set `baseurl: "/REPO-NAME"` in `_config.yml`.
4. The site goes live at `https://USERNAME.github.io/` (or `/REPO-NAME/`) in a minute or two.

## Preview locally (optional)

```bash
bundle install
bundle exec jekyll serve
# open http://localhost:4000
```
