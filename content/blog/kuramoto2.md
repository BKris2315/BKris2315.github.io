---
title: "kuramoto2: simulating power grids with the second-order Kuramoto model"
date: 2025-12-28
math: true
tags: ["research", "code", "power-grids", "kuramoto"]
description: "The open-source C code behind our power-grid synchronization papers."
---

Most of my research runs on one piece of software: a solver for the **second-order Kuramoto model**
on large networks. Each node is a generator or a consumer with inertia \(m_i\), damping \(d_i\) and
power injection \(P_i\), coupled through the transmission lines of the grid:

$$
m_i \ddot\theta_i + d_i \dot\theta_i = P_i + \sum_j K_{ij} \sin(\theta_j - \theta_i)
$$

The code is public at [NetworkingWithKuramoto/kuramoto2](https://github.com/NetworkingWithKuramoto/kuramoto2).
I developed the CPU implementation; a GPU version exists alongside it for the really large parameter sweeps.

<!--more-->

What it is used for:

- **Synchronization** as a function of the global coupling, measured with the Kuramoto order parameter
  and with a "universal" order parameter that also takes the network structure into account.
- **Cascade failures**: overloaded lines are removed one after another, and the size distribution
  of the resulting blackouts is recorded.
- **Grid modifications**: adding, doubling or replacing lines, including adaptive HVDC-like links.

Networks are given as plain node and edge files (ID, injected power, community, mask), so the same
binary runs on the European, North American or Hungarian high-voltage grids.

Papers that rely on it:

- [Studying power-grid synchronization with incremental refinement of model heterogeneity](https://doi.org/10.1063/5.0237050), *Chaos* (2025)
- [Quantitative comparison of power grid reinforcements](https://doi.org/10.1016/j.chaos.2025.117095), *Chaos, Solitons & Fractals* (2025)
- [The effect of HVDC lines in power-grids via Kuramoto modelling](https://doi.org/10.1016/j.chaos.2026.118671), *Chaos, Solitons & Fractals* (2026)
