---
aliases: ["/blog/image-optimization/"]
title: "Images"
date: "2021-10-16T23:51:37+02:00"
toc: true
cover:
  src: alexandre-van-thuan-mr9FouttLGY-unsplash.jpg
  alt:
    The interior of Stadsbiblioteket in Stockholm - Gunnar Asplunds library from
    1928. The architecture is a transition between neoclassicism and
    functionalism.
  caption: By [Alexandre Van Thuan](https://unsplash.com/photos/mr9FouttLGY)
---

Images placed next to a post (a [page bundle](https://gohugo.io/content-management/page-bundles/))
are processed by a Markdown render hook in `layouts/_markup/render-image.html`:

- Images wider than 960 px are scaled down, and every image is converted to [WebP](https://en.wikipedia.org/wiki/WebP).
- Images get `loading="lazy"`, so the browser only downloads them when they scroll into view.
- SVG files and remote URLs are used as they are.

<!--more-->

## Blog Post Cover Images

Use the [front matter](https://gohugo.io/content-management/front-matter/) of
your posts to add cover images:

```markdown
---
cover:
  src: alexandre-van-thuan-mr9FouttLGY-unsplash.jpg
  alt: The interior of Stadsbiblioteket in Stockholm.
  caption: By [Alexandre Van Thuan](https://unsplash.com/photos/mr9FouttLGY)
---
```

## Captions

The image title becomes a caption, with Markdown support:

```markdown
![Alt text](image.jpg "Caption with **markdown support**")
```

![The main library in Vancouver is architecturally significant.](aaron-thomas-dMqlE7lgyOU-unsplash.jpg "The main library in Vancouver. The angles and levels contour together to produce a trippy scene. By [Aaron Thomas](https://unsplash.com/photos/dMqlE7lgyOU)")

## Quality

The WebP quality is set to 80 in the render hook. Change the `q80` there to trade size for quality.
