---
layout: default
title: "Efficient Transformer Quantization Notes"
excerpt: "Quick references for activation-aware quantization experiments."
permalink: /research/quantization-notes/
---

This collection documents the most useful heuristics from my quantization experiments:

- Calibrate per-channel scales with 8–16 representative batches to reduce cold-start error.
- Use smooth clipping with a learned threshold when activations follow a heavy-tailed distribution.
- Run a few minutes of knowledge distillation to recover perplexity after int8 conversion.

Each notebook in `_research/` is a standalone page, which makes it easy to link quick references without crowding the main blog feed.
