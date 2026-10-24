---
title: "Small tools and side projects"
date: 2026-05-17
tags: ["code", "tools", "python"]
description: "A round-up of smaller repositories: audiobooks, distribution fitting, a 0–1 test for chaos, and more."
---

Not everything deserves its own post. A few smaller projects from my
[GitHub](https://github.com/BKris2315?tab=repositories):

<!--more-->

- **[book2speech](https://github.com/BKris2315/book2speech)** turns books (`.txt`, `.docx`,
  `.epub`, `.pdf`, `.mobi`, …) into one audio file per chapter. It supports Parler, Kokoro and
  multilingual XTTS v2 (including Hungarian) and has a small web UI.
- **[moodle-hw-checker](https://github.com/BKris2315/moodle-hw-checker)** helps with teaching:
  it syncs a Moodle course and uses a local LLM to mark each homework problem as attempted,
  partial or missing. It strips template cells first and caches replies, so only new submissions go to the GPU.
- **[scipy_distfit](https://github.com/BKris2315/scipy_distfit)** fits the 80 distributions from `distfit`
  to data that is *already binned* or binned your own way (for example log-binned), using plain `curve_fit`.
- **[predicting-chaos-from-timeseries](https://github.com/BKris2315/predicting-chaos-from-timeseries)**
  implements the 0–1 test for (partially predictable) chaos by Wernecke et al., plus Lyapunov
  exponents with the Benettin algorithm, using the Lorenz system as the test case.
- **[A-webots-tutorial](https://github.com/BKris2315/A-webots-tutorial)** is an older Webots robotics
  tutorial series, from a hand-built differential-drive robot to PID line following, maze solving and inverse kinematics.
