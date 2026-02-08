---
layout: default
title: "Phase 3.1 — Psychoanalytic Predictions"
---

# Phase 3.1 — Psychoanalytic Predictions About LLM Behavior

*Status: Not started — Target: Weeks 11–24*

## Objective

Derive 5 predictions from Lacanian theory that are non-obvious from a purely computational perspective. Test each one. This phase is the center of gravity of the entire project.

---

## Tools and Infrastructure Required

- Open-weight models (LLaMA, Mistral) for interpretability work
- TransformerLens or similar library for mechanistic interpretability
- Sparse autoencoder tooling (Anthropic's published SAE code or alternatives)
- Logit lens / tuned lens implementations
- Jupyter notebooks or Python scripts for each experiment

---

## Prediction 1: Hallucinations as Formations of the Unconscious

**Theoretical basis:** Freud argued that dreams, slips, and symptoms are structured formations — products of condensation, displacement, and overdetermination. If LLM errors operate through the same mechanisms, hallucinated content should be overdetermined rather than random.

### Method

- Collect hallucination corpus across multiple models and domains
- For each hallucination, trace associative sources in context and training distribution
- Code for condensation, displacement, and overdetermination vs. null hypothesis of random confabulation

### Confirming evidence:

### Disconfirming evidence:

### Results

*To be completed.*

---

## Prediction 2: Retroactive Meaning-Making (The Quilting Point)

**Theoretical basis:** Meaning is produced retroactively — later signifiers function as *points de capiton* that reorganize the meaning of prior signifiers. This should manifest as phase transitions in early-token representations.

### Method

- Use logit lens / tuned lens on garden-path sentences, punchlines, twist endings
- Measure rate of change in early-token representations across layers
- Look for nonlinear jumps corresponding to quilting-point tokens

### Confirming evidence:

### Disconfirming evidence:

### Results

*To be completed.*

---

## Prediction 3: Return of the Repressed via Superposition

**Theoretical basis:** Features compressed together in superposition may function analogously to repression. "Repressed" features should return under specific conditions — when associative pressure triggers them.

### Method

- Use sparse autoencoders / activation patching to identify compressed features
- Design prompts that create associative pressure along suppressed-feature pathways
- Monitor whether suppressed features activate and influence output

### Confirming evidence:

### Disconfirming evidence:

### Results

*To be completed.*

---

## Prediction 4: Structural Resistance at Points of Conflict

**Theoretical basis:** The signifying chain should exhibit increased uncertainty and hedging at structurally conflictual points where incompatible signifying chains converge — analogous to psychoanalytic resistance.

### Method

- Identify prompts where multiple incompatible representational pathways converge
- Measure output entropy, token probability distributions, hedging behaviors
- Compare against matched control prompts with no structural conflict

### Confirming evidence:

### Disconfirming evidence:

### Results

*To be completed.*

---

## Prediction 5: Distinct Computational Signatures of Metaphor vs. Metonymy

**Theoretical basis:** If the Jakobsonian two-axis model genuinely applies to LLM processing, metaphoric operations (substitution) and metonymic operations (combination) should leave different computational signatures.

### Method

- Design matched prompt pairs eliciting metaphoric vs. metonymic outputs
- Characterize computational pathways via mechanistic interpretability
- Test whether the two operations are mechanistically distinct

### Confirming evidence:

### Disconfirming evidence:

### Results

*To be completed.*

---

## Summary of Findings

| Prediction | Confirmed? | Strength of Evidence | Notes |
|-----------|-----------|---------------------|-------|
| 1. Hallucinations as formations | | | |
| 2. Retroactive meaning-making | | | |
| 3. Return of the repressed | | | |
| 4. Structural resistance | | | |
| 5. Metaphor vs. metonymy signatures | | | |
