---
title: "Chaos in reasoning language models"
date: 2026-07-30
tags: ["research", "paper", "machine-learning", "chaos", "teaching"]
description: "A preprint that grew out of a student project: LLMs analysed with the tools of nonlinear dynamics."
---

New preprint with Gregorio Jaca and János Török:
[Chaos in reason: How chain-of-thought LLMs can look for an answer](https://arxiv.org/abs/2607.27805).

It started as Gregorio's BSc student research project (TDK), which János Török and I supervised.
The project, *Chaos in Large Language Models*, won 1st prize at the 2025 BME TDK conference.

<!--more-->

The idea is to treat a language model as a dynamical system and use the usual chaos toolbox on it:

- **Sensitivity to initial conditions.** Nearby trajectories, in text and in hidden states,
  diverge intermittently, in jumps, while staying bounded. This holds across different distance metrics.
- **Exact Jacobians of the Transformer blocks.** Self-attention and the feed-forward network
  expand perturbations, while normalization and residual connections counteract them.
- **Recurrence plots and dimension analysis.** They look structurally similar to canonical chaotic
  systems such as the Lorenz attractor, with fractal structure in the hidden-state space,
  strongest in the last layers.

Our working hypothesis is that the nonlinear coupling introduced by attention drives the chaotic behaviour.
