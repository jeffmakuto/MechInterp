# Master's Thesis Outline

## Title

**Mechanistic Interpretability of Reasoning Circuits in Transformer Language Models**

---

## Abstract

Transformer language models have demonstrated remarkable ability to perform abstract reasoning, such as contradiction detection, causal inference, and factual consistency. However, little is known about the internal mechanisms that support these capabilities. This thesis presents an in-depth mechanistic interpretability study of reasoning circuits in transformer models. We identify specialized attention heads and neurons, verify their causal role through ablations and activation patching, and trace their emergence during training. We focus on small to medium models (e.g., SoLU-1L, Pythia series) using open-source tools like TransformerLens. Our findings show evidence of modular reasoning circuits, causal dependence of predictions on these circuits, and sudden emergence phenomena during grokking. These insights inform both the development of interpretable AI systems and future research into model behavior and alignment.

---

## Table of Contents

1. Introduction
2. Background & Related Work
3. Methodology

   * Models Used (SoLU, Pythia, GPT-2)
   * Tasks and Datasets (Contradiction, Causal Inference, Factual Verification)
   * Tools (TransformerLens, Activation Patching, Ablations)
4. **Circuit Discovery for Reasoning Tasks** *(A)*

   * Identification of Specialized Heads and Neurons
   * Activation Pattern Analysis
   * Modular Roles (e.g., negation, temporal reasoning)
5. **Causal Verification of Reasoning Circuits** *(B)*

   * Intervention Experiments (Ablations, Activation Patching)
   * Redundancy and Robustness of Circuits
   * Suppressing and Overwriting Predictions
6. **Emergence of Reasoning Circuits During Training** *(C)*

   * Longitudinal Checkpoint Analysis (e.g. Pythia at 10%, 50%, 100%)
   * Sudden Sharpness in Circuits (Grokking)
   * Early vs Late Representation Comparisons
7. Discussion & Limitations

   * Generalization across prompts, phrasing, and tokenization
   * How minimal tasks shaped circuit clarity
   * Relation to existing theories of model abstraction
8. Future Work

   * Beyond reasoning: Could circuits form for ethics, planning?
   * Improving interpretability through training-time interventions
9. Conclusion

---

## Publication Plan

### Paper 1: Circuit Discovery for Reasoning Tasks

* Focus: Identifying and characterizing heads and neurons responsible for abstract reasoning
* Status: Core of Chapter 4

### Paper 2: Causal Verification of Reasoning Mechanisms

* Focus: Causal tracing, patching, redundancy, and robustness of discovered circuits
* Status: Core of Chapter 5

### Paper 3: Emergence of Reasoning During Training

* Focus: Temporal evolution of circuits, checkpoint analysis, grokking phenomena
* Status: Core of Chapter 6

Each paper will be positioned for submission to workshops and conferences in interpretability, such as **NeurIPS IML**, **ICLR Transparency**, or **Anthropic Interpretability Research Circles**.

---

## Notes

* All experiments will use models where interpretability is practical (e.g. Pythia 70M–410M)
* Tooling: TransformerLens, Seaborn/Plotly for visualizations, PyTorch for ablations
* Code, prompts, and data to be open-sourced for reproducibility
