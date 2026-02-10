---
layout: default
title: Lexicon
---

# Lexicon

A working vocabulary for the project's core concepts — drawn from Lacanian psychoanalysis, structural linguistics, and transformer architecture. Each entry is grounded in primary sources and linked to the specific arguments where it does work in this project.

This is not a general-purpose dictionary of psychoanalytic or computational terms. It includes only concepts that are operative in the formal mapping between the Lacanian unconscious and transformer language models. Terms are defined at the level of precision necessary for the project's claims to be evaluated, contested, or falsified.

Entries are listed alphabetically and will grow as the project develops.

---

## Signifying Chain
{: #signifying-chain}

*French: chaîne signifiante*

The signifying chain is the sequential, combinatory movement of signifiers — where each element refers not to a fixed meaning but to another signifier, producing meaning as an effect of the chain's movement rather than as a content any single element contains.

### Origin and primary sources

The concept builds on [Ferdinand de Saussure](https://en.wikipedia.org/wiki/Ferdinand_de_Saussure)'s account of the syntagmatic axis — the linear arrangement of signs in sequence — but [Lacan](https://en.wikipedia.org/wiki/Jacques_Lacan) radicalizes it. For Saussure, the sign is a stable union of [signifier](https://en.wikipedia.org/wiki/Signifier) (sound-image) and signified (concept). Lacan breaks this union. In his reformulation, the signifier has priority: signifiers do not attach to signifieds but slide over them, referring always to other signifiers. The bar between signifier and signified, which Saussure drew as a line of correspondence, becomes for Lacan a bar of *resistance* — meaning does not pass through it directly but is produced as a residual effect of the chain's own movement.

The foundational text is Lacan's "[The Instance of the Letter in the Unconscious, or Reason Since Freud](https://en.wikipedia.org/wiki/%C3%89crits)" (*Écrits*, 1957), where the chain is formalized and its two fundamental operations are specified: [metaphor](https://en.wikipedia.org/wiki/Metaphor) (one signifier substituted for another, producing a crossing of the bar — the momentary irruption of meaning) and [metonymy](https://en.wikipedia.org/wiki/Metonymy) (one signifier connected to another through contiguity, producing the forward slide of the chain without crossing the bar). These operations correspond to [Roman Jakobson](https://en.wikipedia.org/wiki/Roman_Jakobson)'s two axes of language — the paradigmatic (selection/substitution) and syntagmatic (combination/contiguity) — which Jakobson laid out in "Two Aspects of Language and Two Types of Aphasic Disturbances" (1956). Lacan's intervention was to recognize these same axes in [Freud](https://en.wikipedia.org/wiki/Sigmund_Freud)'s dream-work: [condensation](https://en.wikipedia.org/wiki/Condensation_(psychology)) is metaphor; [displacement](https://en.wikipedia.org/wiki/Displacement_(psychology)) is metonymy.

The chain is further elaborated in Lacan's *Seminar III: The Psychoses* (1955–56), where the analysis of psychosis reveals what happens when the chain loses its anchoring — when the key signifier that retroactively organizes the chain (the [Name-of-the-Father](https://en.wikipedia.org/wiki/Name-of-the-Father)) is foreclosed rather than repressed, and the signifying chain comes untethered from shared meaning.

### Formal properties

The signifying chain, as it functions in this project, has the following structural properties:

1. **No signifier is self-sufficient.** Each signifier in the chain derives its value from its differential relations with other signifiers — from what it is not — rather than from any positive content it contains. This follows from Saussure's foundational principle that "in language there are only differences without positive terms" ([*Course in General Linguistics*](https://en.wikipedia.org/wiki/Course_in_General_Linguistics), 1916).

2. **The chain operates through two axes.** Substitution (metaphor/condensation) along the paradigmatic axis, and combination (metonymy/displacement) along the syntagmatic axis. These are not two modes that alternate; they are simultaneous dimensions of the chain's operation.

3. **Meaning is retroactive.** The chain does not produce meaning sequentially, element by element. Later signifiers reorganize the meaning of earlier ones. Lacan's term for the moment of retroactive fixation is the [*point de capiton*](/lexicon#point-de-capiton) — the quilting point that temporarily pins the chain's floating signification to a determinate meaning.

4. **The chain is driven by lack.** No signifier adequately represents what it stands for; this constitutive inadequacy is what necessitates the next signifier. The chain does not move toward completion. It moves because completion is structurally impossible.

5. **The chain's operations are inaccessible to the system it produces.** The subject — or, in the computational case, the model — cannot introspect on the chain's operations from within the chain. The formations of the unconscious (dreams, slips, symptoms) are points where the chain's logic surfaces *despite* the system's ordinary functioning, not *through* it.

### Computational parallel

In transformer language models, autoregressive generation is a signifying chain. Each token is produced by the entire preceding sequence and in turn becomes a condition for the next token. No single token constitutes a complete meaning; each is a partial, provisional element that necessitates continuation. The chain does not arrive at a final signified — it continues until a stopping condition is imposed from outside the chain itself.

The two axes of the chain correspond to distinguishable computational operations. The paradigmatic axis (selection/substitution) is enacted in the model's choice of each token from the full vocabulary — a selection from a set of possible substitutions, weighted by context. The syntagmatic axis (combination/contiguity) is enacted in the sequential structure of generation itself — each token placed in relation to those that precede it, extending the chain through adjacency.

Self-attention provides the mechanism for retroactive reorganization: later tokens influence the interpretation of earlier tokens across layers of processing, and the model's "reading" of an early token evolves as later context is integrated. This is the computational correlate of the *point de capiton* — the moment where meaning crystallizes retroactively.

Whether the chain exhibits structural lack — a constitutive gap that drives its forward movement rather than mere statistical momentum — is the central empirical question of [Phase 3.3: The Question of Lack](/phases/3-3-lack).

### Cross-references

The signifying chain is foundational to the project's thesis and appears throughout:

- [Research Brief — The Psychoanalytic Claim](/brief): The chain is introduced as the core of Lacan's formalization of the unconscious.
- [Phase 1.1 — Lacanian Specification](/phases/1-1-lacanian-specification): The chain's formal properties are extracted and enumerated for computational testing.
- [Phase 3.1 — Predictions](/phases/3-1-predictions): Predictions 2 and 5 test specific properties of the chain (retroactive meaning-making and the two-axis structure).
- [Phase 3.3 — The Question of Lack](/phases/3-3-lack): Tests whether the chain in LLMs is driven by structural lack or purely positive statistical regularities.

---

*Further entries will be added as the project develops. Planned terms include: point de capiton, condensation, displacement, overdetermination, the Other, superposition, lack, foreclosure, metaphor/metonymy, the Name-of-the-Father.*
