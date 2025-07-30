# Mechanistic Interpretability for Real-World Language Model Failures

## Overview

This repository accompanies the Master's thesis:

> **Mechanistic Interpretability for Solving Real-World Failures in Transformer Language Models**

We apply tools from **mechanistic interpretability (MechInterp)** to diagnose, understand, and intervene in **real-world failure modes** of transformer language models — including **hallucination**, **sycophancy**, **factual inconsistency**, and **deceptive reasoning**.

All experiments are conducted on small-to-medium open-source models (e.g. Pythia, GPT-2), using transparent methods and open tooling (e.g. TransformerLens).

---

## Real-World Tasks

We analyze circuits and failure modes in tasks with direct real-world implications:

| Task                         | Problem Addressed                       | Dataset/Example Source     |
|------------------------------|------------------------------------------|-----------------------------|
| Factual QA                   | Hallucinations in knowledge queries     | TruthfulQA, HotpotQA       |
| Contradiction Detection      | Sycophancy and user-aligned errors      | Custom prompts, ANLI        |
| Ethical & Deceptive Reasoning| Unsafe or manipulative generations      | Ethics sheets, Anthropic datasets |

---

## Tooling & Frameworks

This project uses the following open-source tools:

- [TransformerLens](https://github.com/NeelNanda/TransformerLens) for model internals access
- PyTorch + custom patching & ablation utilities
- Seaborn / Plotly for visualizing circuits and activations
- CLI scripts for running real-world circuit interventions

---

## Circuit Analysis Modules

| Module                              | Description                                                                 |
|-------------------------------------|-----------------------------------------------------------------------------|
| `hallucination_circuits.py`         | Detects and intervenes on hallucination subcircuits in factual QA          |
| `sycophancy_detector.py`            | Analyzes contradiction-suppression in sycophantic completions              |
| `ethics_reasoning_tracer.py`        | Traces reasoning in morally-sensitive and manipulative prompts             |
| `activation_patcher.py`             | General-purpose activation patching across checkpoints and tasks           |
| `training_emergence_tracker.py`     | Tracks evolution of reasoning circuits during model training               |

---

## Example: Hallucination Suppression

```bash
python hallucination_circuits.py --model pythia-160m \
  --prompt "What causes measles?" \
  --ablate_heads factual_head_3.2 factual_head_4.0 \
  --visualize
