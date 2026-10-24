---
title: "Paper: HVDC lines in Kuramoto power-grid models"
date: 2026-09-01
math: true
tags: ["research", "paper", "power-grids", "kuramoto"]
description: "First-author paper with Géza Ódor, now out in Chaos, Solitons & Fractals."
---

My first first-author paper, written with Géza Ódor, is published in *Chaos, Solitons & Fractals*:
[The effect of HVDC lines in power-grids via Kuramoto modelling](https://doi.org/10.1016/j.chaos.2026.118671)
([arXiv:2512.24122](https://arxiv.org/abs/2512.24122)).

<!--more-->

We solve the adaptive second-order Kuramoto model on the European high-voltage grid and replace
some AC lines with **static or adaptive HVDC links**. The short version:

- HVDC lines improve phase synchronization and reduce cascade sizes. These improvements can be related to the
  finite-size scaling of the second-order Kuramoto model on graphs with spectral dimension \(d_s < 4\).
- They have costs: the frequency spread can grow, and Braess-like effects appear when the total
  transmitted power changes at very small or very large global couplings.
- Adaptive HVDC lines, which react to the local frequency difference, work best in the steady state,
  but the system then needs **very long relaxation times** to get there.

Those long transients made the simulations expensive; most of the code work went into making
the [kuramoto2](/blog/kuramoto2/) runs fast enough. I presented a GPU follow-up,
*Prototypes of HVDC connections in a Kuramoto-like power-grid system*, at GPU Day 2026.
