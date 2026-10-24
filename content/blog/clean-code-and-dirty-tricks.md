---
title: "Clean Code & Dirty Tricks: a seminar series at BME"
date: 2025-05-09
tags: ["teaching", "python", "code"]
description: "A seminar series for students on writing maintainable, fast code, and on using AI tools well."
---

In spring 2025 I organized **Clean Code & Dirty Tricks**, a seminar series for BME students
(organized with the Wigner Jenő College for Advanced Studies and open to all BME students). All material is on GitHub:
[BKris2315/CleanCodeAndDirtyTricks](https://github.com/BKris2315/CleanCodeAndDirtyTricks).

<!--more-->

Topics:

1. **Clean code fundamentals**: function and class design, naming, comments, documentation, typing.
2. **Python optimization**: vectorization, multiprocessing, JIT compilation, GPU acceleration.
3. **AI in development**: Copilot-style tools, prompting, hallucinations and confidentiality.
4. **GitHub workflows**: project layout, branches, pull requests, task tracking, READMEs.
5. **(Optional) AI and symbolic tools**: SymPy, Transformers, object detection, distillation.

The slides are Jupyter notebooks. You can present them with

```bash
jupyter nbconvert <notebook.ipynb> --to slides --post serve --no-input --no-prompt
```

Later seminars continued with a hands-on Git session
([git_tutorial](https://github.com/BKris2315/git_tutorial)).
