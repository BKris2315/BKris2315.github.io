---
title: "agentbox: a default-deny sandbox for AI coding agents"
date: 2026-10-21
tags: ["code", "tools", "security", "ai"]
description: "One Bash script that confines coding agents to the project they work on, enforced by the kernel."
---

I use AI coding agents a lot, but I don't want them to read `~/.ssh`, my other repositories or
my browser profile. [agentbox](https://github.com/BKris2315/agentbox) is a single Bash script that
runs an agent in a **default-deny sandbox**. It needs no daemon, VM or container image, only
`python3`, which Ubuntu ships with.

<!--more-->

- **Backends.** It uses `bubblewrap` (user namespaces) when available and falls back to
  **Landlock** on kernels ≥ 5.13. If neither works, it refuses to run rather than running unsandboxed.
- **What the agent sees.** The project (read-write, except `.git/config` and `.git/hooks`),
  paths you grant explicitly with `--ro` / `--rw`, a separate per-project home directory, and read-only `/usr` and `/etc`.
- **Environment.** Variables are rebuilt from an allow-list, so `SSH_AUTH_SOCK`, `AWS_*` and `*_TOKEN` are not passed through.
- **Kernel enforcement.** Confinement doesn't depend on watching commands, so any script or binary the agent
  writes is confined exactly like the agent itself.
