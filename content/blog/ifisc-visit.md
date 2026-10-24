---
title: "A research week at IFISC, Mallorca"
date: 2026-02-16
tags: ["research", "collaboration", "power-grids", "code"]
description: "Stability analysis of the European grid with Pere Colet and Damià Gomila, and a Python port of their power-grid model."
---

From 9 to 15 February 2026 I worked at [IFISC](https://ifisc.uib-csic.es/) in Palma de Mallorca,
on the invitation of Pere Colet and Damià Gomila. We've been working together since 2025 on the
**linear stability and fixed points of the continental European high-voltage grid**.

<!--more-->

Our question is how a grid model reaches a bifurcation. We looked at two ways of pushing it there:

1. globally scaling the load on the transmission lines;
2. changing generation and consumption in chosen regions at the same time.

Surprisingly, the first one gives a **crossover** rather than a standard bifurcation: the leading
complex eigenvalue pair changes within a certain parameter range. We're also studying how the
bifurcation points depend on system size. Related work, *A System Divided: Stability and Size Dependence
of Segmented Power Grids*, asks what happens when a geographically coherent region is suddenly
cut off, as in the 2025 Iberian blackout, and which eigenmodes take over afterwards.

### A side product: a Python port

To get familiar with their tools I ported the IFISC group's Fortran power-grid frequency model
(Martínez-Barbeito, Gomila & Colet, *IEEE Trans. Sustainable Energy*, 2023) to Python:
[SecondaryPowerControlInElctricGrids](https://github.com/BKris2315/SecondaryPowerControlInElctricGrids).
It keeps the original semi-implicit Euler scheme and replaces Intel MKL PARDISO with SciPy's
sparse solvers. The Jacobian has fewer than 2% non-zero entries, so sparse solvers work well.
