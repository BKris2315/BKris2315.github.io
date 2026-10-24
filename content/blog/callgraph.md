---
title: "Callgraph: interactive call graphs for any Python repository"
date: 2026-10-15
tags: ["code", "tools", "python"]
description: "Point it at a Python repo and get one self-contained HTML page showing who calls what."
---

When I join a new Python codebase, or come back to an old one of mine, the first question is
usually "what calls what?". [Callgraph](https://github.com/BKris2315/Callgraph) answers it statically:

```bash
pip install -e .
callgraph build --repo path/to/any/python/repo   # -> ./callgraph-<sha8>.html
```

<!--more-->

The output is one self-contained HTML file with an overview of the code's main areas and a
zoomable graph per area. The graphs show call order, the `if` a call sits under, and its arguments.
Nothing from the target repository is imported or run, so you don't need its dependencies,
and a build takes well under a second.

There are also terminal commands: `trace` prints the call tree below (or above) a function,
`edges` exports the connections as text, TSV or JSON, and an optional `annotate` step uses a
**local** LLM to write descriptions for functions.
