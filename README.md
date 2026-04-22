# StyleProbe-PRM

> Diagnosing Style Sensitivity in Multimodal Process Reward Models

[![arXiv](https://img.shields.io/badge/arXiv-coming_soon-b31b1b.svg)](https://arxiv.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**Status:** 🚧 Work in progress. Core diagnostic benchmark expected by late May 2026.

---

## TL;DR

Multimodal Process Reward Models (PRMs) — like VisualPRM, MM-PRM, and others — are increasingly used to score step-by-step reasoning in vision-language models. We investigate a concerning question:

> **Do these PRMs actually score reasoning correctness, or do they score how the reasoning is *written*?**

Our preliminary results suggest the latter. When the same logically-correct reasoning trajectory is rewritten in a different stylistic form — shorter, without reflection words, or in a different template — state-of-the-art PRMs assign noticeably different scores.

This project provides:

1. **StyleProbe-PRM** — a diagnostic benchmark with both *synthetic* (prompt-paraphrased) and *natural* (cross-source) style variants of logically equivalent reasoning trajectories.
2. **A suite of metrics** (SV, RIR, SCR, Kendall's τ) to quantify PRM style sensitivity.
3. **Cross-backbone evaluation** showing the issue is universal across PRM families.
4. **StyleInv-PRM** (coming soon) — a lightweight LoRA-based proof-of-concept that mitigates the fragility while preserving step-level accuracy.

---

## Why this matters

PRMs power test-time scaling (Best-of-N reranking) and RL-based reasoning training. If a PRM rewards writing style over reasoning correctness:

- **Best-of-N reranking** may pick stylistically appealing but logically wrong answers.
- **RL training** may drift the policy toward "PRM-pleasing" surface patterns rather than genuine reasoning.
- **Cross-policy evaluation** becomes unreliable when the evaluated model has a different style distribution than the PRM's training data.

---

## Roadmap

- [x] Project kickoff
- [ ] Week 1-4: Diagnostic framework and MVP benchmark
- [ ] Week 5-8: StyleInv-PRM training
- [ ] Week 9-10: Best-of-N reranking evaluation
- [ ] Week 11-12: Paper draft and release

---

## Planned structure