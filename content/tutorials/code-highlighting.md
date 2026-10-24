---
aliases: ["/blog/prism-code-highlighting-showcase/"]
title: "Code Highlighting"
date: "2021-07-28T04:25:37+02:00"
description: "Syntax highlighting with Hugo's built-in Chroma highlighter and the gruvbox palette."
tags: ["code", "hugo"]
---

Code blocks are highlighted at build time by [Chroma](https://github.com/alecthomas/chroma),
Hugo's built-in highlighter, so the page needs no JavaScript for it. The colours are the
`gruvbox` and `gruvbox-light` Chroma styles. They live in `assets/css/syntax.css` and follow the theme toggle.

<!--more-->

To regenerate the stylesheet with a different style:

```bash
hugo gen chromastyles --style=gruvbox
```

## Fenced code blocks

````markdown
```python
print("hello")
```
````

```python
import numpy as np

def kuramoto_order(theta: np.ndarray) -> float:
    """Kuramoto order parameter r = |<exp(i θ)>|."""
    return float(np.abs(np.exp(1j * theta).mean()))
```

```c
#include <math.h>

double order_parameter(const double *theta, int n) {
    double re = 0.0, im = 0.0;
    for (int i = 0; i < n; i++) { re += cos(theta[i]); im += sin(theta[i]); }
    return sqrt(re * re + im * im) / n;
}
```

```julia
order(θ) = abs(sum(cis, θ)) / length(θ)
```

## Line numbers and highlighted lines

Options go after the language name, for example `{linenos=table,hl_lines=[2]}`:

```bash {linenos=table,hl_lines=[2]}
git pull
hugo server
git push
```

## Inline code

Use backticks for `inline code`.
