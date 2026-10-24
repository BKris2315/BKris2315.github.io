# bkris2315.github.io

Personal site of Kristóf Benedek, built with [Hugo](https://gohugo.io/). There's no theme dependency
and no npm: the layout is a few small templates in `layouts/` with gruvbox colours in `assets/css/`.

Pushing to `master` builds and deploys the site through GitHub Actions (`.github/workflows/hugo.yml`).

## Common edits

| To change…                     | Edit                                                       |
| ------------------------------ | ---------------------------------------------------------- |
| a publication                  | `data/publications.yaml` (newest first)                    |
| a talk or poster               | `data/talks.yaml` (newest first)                           |
| bio and news on the home page  | `content/_index.md`                                        |
| name, role, emails, links      | `[params]` in `hugo.toml`                                  |
| the CV                         | `content/cv.md`                                            |
| the menu                       | `[menus]` in `hugo.toml`                                   |
| the profile photo              | replace `assets/images/profile.jpg`                        |

### New blog post

Create `content/blog/my-post.md`:

```markdown
---
title: "My post"
date: 2026-11-01
tags: ["research"]
description: "One line shown in the post list."
---

Intro paragraph (shown as the summary).

<!--more-->

The rest of the post.
```

Add `math: true` for KaTeX (`$$…$$` display, `\(…\)` inline). For images, make a folder
`content/blog/my-post/` with `index.md` plus the image files, and use `![alt](photo.jpg "caption")`.
The images are resized to WebP automatically.

## Preview locally

```bash
hugo server        # http://localhost:1313, reloads on save
```

Hugo ≥ 0.146 (extended) is needed; CI uses the version pinned in the workflow.

## Layout

```
hugo.toml              site config: params, links, menu
content/               pages (Markdown); blog/ and tutorials/ are sections
data/                  publications.yaml, talks.yaml
layouts/               baseof, home, page, section templates
  _partials/           header, footer, publication entry, KaTeX include
  _shortcodes/         {{< publications >}}, {{< talks >}}, {{< entry >}}, {{< video >}}
  _markup/             image render hook
assets/                css (gruvbox palette, syntax colours) and profile photo
static/                favicons and fonts, copied as-is
```
