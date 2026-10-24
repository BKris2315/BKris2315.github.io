---
aliases: ["/blog/math-typesetting/"]
author: Hugo Authors
title: Math Typesetting
date: 2019-03-08
description: A brief guide to setup KaTeX
math: true
tags: 
  - "hugo-basic-example"
---

Mathematical notation on this site is rendered with [KaTeX](https://katex.org/), loaded only on pages that need it.
<!--more-->

- Add `math: true` to the front matter of a page to load KaTeX there.
- Display math: wrap it in `$$ … $$` or `\[ … \]`.
- Inline math: wrap it in `\( … \)`. Hugo's *passthrough* extension (see `hugo.toml`) keeps
  Markdown from touching the TeX inside these delimiters, so underscores and backslashes survive.
- The KaTeX include lives in `layouts/_partials/math.html`.

**Note:** Use the online reference of [Supported TeX Functions](https://katex.org/docs/supported.html)

### Examples

Inline math: \(\varphi = \dfrac{1+\sqrt5}{2}= 1.6180339887…\)

Block math:
$$
 \varphi = 1+\frac{1} {1+\frac{1} {1+\frac{1} {1+\cdots} } }
$$
