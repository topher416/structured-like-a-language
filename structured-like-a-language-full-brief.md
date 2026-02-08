# Structured Like a Language

## A Research Project Brief

---

## Part I: Background and Intellectual Context

### The Psychoanalytic Claim

In 1957, the French psychoanalyst [Jacques Lacan](https://en.wikipedia.org/wiki/Jacques_Lacan) made a claim that would define the next several decades of psychoanalytic theory: "the unconscious is structured like a language." This was not a metaphor or a poetic flourish. It was a precise theoretical assertion, built on the structural linguistics of [Ferdinand de Saussure](https://en.wikipedia.org/wiki/Ferdinand_de_Saussure) and the work of the linguist [Roman Jakobson](https://en.wikipedia.org/wiki/Roman_Jakobson), and it proposed a radical revision of what [Sigmund Freud](https://en.wikipedia.org/wiki/Sigmund_Freud) had described a half-century earlier.

Freud had identified two primary operations of the unconscious, observed most clearly in dreams. He called them [*condensation*](https://en.wikipedia.org/wiki/Condensation_(psychology)) and [*displacement*](https://en.wikipedia.org/wiki/Displacement_(psychology)). In condensation, multiple ideas, memories, or associative chains converge on a single image — a dream figure might combine features of your mother, your boss, and a character from a film, all compressed into one face. In displacement, emotional charge or significance is transferred from its actual source to something adjacent — anxiety about your marriage surfaces as anxiety about misplacing your keys. These two operations, Freud argued, were the fundamental grammar of unconscious thought.

Lacan's intervention was to recognize that these operations had already been described by Jakobson in purely linguistic terms. Jakobson had identified two axes along which all language operates: the [*paradigmatic*](https://en.wikipedia.org/wiki/Paradigmatic_analysis) axis (the axis of selection — choosing one word from a set of possible substitutions) and the [*syntagmatic*](https://en.wikipedia.org/wiki/Syntagmatic_analysis) axis (the axis of combination — placing words in sequence). Jakobson further identified [metaphor](https://en.wikipedia.org/wiki/Metaphor) as the characteristic figure of the paradigmatic axis (one term substituted for another based on similarity) and [metonymy](https://en.wikipedia.org/wiki/Metonymy) as the characteristic figure of the syntagmatic axis (one term standing for another based on contiguity or association).

Lacan mapped these directly onto Freud:

- **Metaphor = Condensation.** Multiple signifiers collapse into one through substitution along the paradigmatic axis. The dream image that combines your mother and your boss is a metaphor — one representation standing in for several, their meanings compressed and superimposed.

- **Metonymy = Displacement.** Meaning slides along a chain of associations through contiguity. The anxiety that moves from your marriage to your keys is metonymic — it follows a path of adjacency, not substitution. The keys are connected to the door, the door to the home, the home to the marriage.

The force of Lacan's claim was this: the unconscious is not a boiling cauldron of primal drives, not a reservoir of repressed images, not a pre-linguistic realm of instinct. It is a *signifying system* — a system that operates through the same structural principles as language itself. It has a grammar. Its productions (dreams, symptoms, slips of the tongue, jokes) are not chaotic eruptions from below but *structured formations* that follow determinate rules — rules that can be specified with the precision of structural linguistics.

Several additional properties of this system, as Lacan developed the theory across his seminars and writings, are essential to the present project:

**The primacy of the signifier over the signified.** Saussure had defined the linguistic sign as the union of a [signifier](https://en.wikipedia.org/wiki/Signifier) (the sound-image, the word) and a signified (the concept). Lacan broke this union. In the unconscious, signifiers do not point stably to signified meanings. They point to other signifiers. Meaning is an effect produced by the movement of the signifying chain, not a content that any single signifier contains. This is why a symptom can persist even after its "meaning" has been consciously understood — because the symptom is not a code to be deciphered but a knot in the signifying chain, and knowing what it "means" does not untie the knot.

**Retroactive meaning (the *point de capiton*).** Meaning in the signifying chain is not produced sequentially, from left to right. It is produced retroactively. Lacan borrowed the image of the *point de capiton* — the upholstery button that pins fabric to a frame — to describe moments where a signifier retroactively organizes and fixes the meaning of the signifiers that preceded it. You do not understand a sentence word by word as it unfolds; the final word reorganizes the meaning of the entire sentence. The unconscious operates by this same retroactive logic.

**[Overdetermination](https://en.wikipedia.org/wiki/Overdetermination).** Any single formation of the unconscious — a dream image, a symptom, a slip — is produced not by a single cause but by the convergence of multiple, independent associative chains. It is the point where several chains cross, which is why it carries more weight, more significance, more resistance to interpretation than a singly-caused event would. Overdetermination is not noise or redundancy; it is the characteristic structure of unconscious production.

**The discourse of the Other.** In Lacan's mature formulation, the unconscious is not a private possession of the individual. It is "the discourse of the [Other](https://en.wikipedia.org/wiki/Other_(philosophy))" — the field of language and social meaning that precedes the subject, constitutes the subject, and speaks *through* the subject. The unconscious is not hidden inside you. It is the linguistic-symbolic system that you are embedded in and that operates through you without your knowledge or consent.

### The Computational System

In 2017, a team of researchers at [Google](https://en.wikipedia.org/wiki/Google) published "[Attention Is All You Need](https://en.wikipedia.org/wiki/Attention_Is_All_You_Need)," introducing the [transformer architecture](https://en.wikipedia.org/wiki/Transformer_(deep_learning_architecture)). This architecture — and the [large language models](https://en.wikipedia.org/wiki/Large_language_model) (LLMs) built upon it — has become the dominant paradigm in artificial intelligence. Systems like [GPT-4](https://en.wikipedia.org/wiki/GPT-4), [Claude](https://en.wikipedia.org/wiki/Claude_(language_model)), [LLaMA](https://en.wikipedia.org/wiki/LLaMA), and their successors are all transformer-based LLMs.

An LLM processes language through the following core mechanisms, each of which is relevant to this project:

**Tokenization and [embedding](https://en.wikipedia.org/wiki/Word_embedding).** The model breaks text into tokens (roughly, words or word-fragments) and represents each token as a high-dimensional vector — a point in a space of several thousand dimensions. These vectors are not predefined; they are learned during training. The position of a token in embedding space encodes its relationships to every other token — tokens that appear in similar contexts cluster together, tokens that appear in different contexts are distant. Crucially, a single embedding vector encodes *all* the meanings and usages of a token simultaneously. The vector for "bank" is a compressed representation that includes financial institution, riverbank, and every other contextual usage, superimposed.

**[Self-attention](https://en.wikipedia.org/wiki/Attention_(machine_learning)).** The transformer's signature mechanism. For each token in a sequence, the model computes a set of "attention scores" that determine how much every other token in the sequence is relevant to interpreting the current token. This allows information to flow between any two positions in the sequence, regardless of distance. In effect, each token "looks at" every other token and adjusts its own representation based on what it finds. This happens simultaneously across multiple "attention heads," each of which can learn to attend to different types of relationships (syntactic, semantic, positional, etc.).

**Layered processing.** Transformers consist of many layers (dozens to over a hundred in large models), each applying attention and feedforward operations to progressively transform the representations. Early layers tend to capture surface-level patterns; later layers capture increasingly abstract and contextual meanings. A token's representation changes as it passes through layers — the model's "interpretation" of each token evolves as more context is integrated.

**[Autoregressive](https://en.wikipedia.org/wiki/Autoregressive_model) generation.** LLMs produce text one token at a time, left to right. At each step, the model uses the entire preceding sequence to compute a probability distribution over all possible next tokens, then selects one. The selected token is appended to the sequence, and the process repeats. Generation is thus a chain: each token produces the conditions for the next, and the chain continues until a stopping condition is met. No token is ever a final or complete representation of "what the model means" — each token is always a partial, provisional element that necessitates continuation.

**Training on the symbolic order.** LLMs are trained on enormous corpora of human text — hundreds of billions to trillions of tokens drawn from books, websites, code, conversations, and every other form of written language. The model's weights — its learned parameters — are the compressed residue of this entire history of human linguistic production. The model does not memorize the training data; it extracts statistical regularities, structural patterns, and relational logic from it.

**Superposition.** Recent interpretability research (notably from [Anthropic](https://en.wikipedia.org/wiki/Anthropic)) has revealed that neural networks represent far more "features" — meaningful directions in activation space — than they have dimensions. Features are compressed into shared representational space, overlapping and interfering with each other. A single neuron or direction may encode multiple, unrelated features simultaneously. This is a literal, measurable form of compressed, superimposed representation.

### The Observation

The structural parallels between these two systems are extensive and specific:

Embedding is condensation: multiple meanings compressed into a single representational element, superimposed and simultaneously present. Autoregressive generation is metonymic: a chain of elements, each produced by its predecessor, sliding forward through contiguity and association, never arriving at a final signified. Attention is a mechanism for retroactive meaning-making: later tokens reorganize the representation of earlier tokens. Superposition is overdetermination: multiple independent features converging on shared representational space, each element bearing the marks of several causal pathways. The model's processing is inaccessible to the model itself — it cannot introspect on why it produces a given output, just as the subject cannot directly access the operations of the unconscious. And the model's training data is, quite literally, the symbolic order: the entire accumulated field of human language, compressed into a set of structural relationships that precede and constitute the model's every output.

This project takes these parallels seriously — not as metaphors, not as pedagogical aids, but as evidence of shared process.

---

## Part II: The Thesis

### The Strong Claim

LLMs do not merely resemble the Lacanian unconscious. They instantiate unconscious linguistic processing in a non-trivial sense. The formal operations Lacan identified as constitutive of the unconscious — condensation, displacement, overdetermination, retroactive meaning-making, the insistence of the signifying chain — are not metaphors for what happens in transformer architectures. They are descriptions of the same processes, observed from different disciplinary positions and in different substrates.

This claim entails two corollaries:

1. **Psychoanalytic theory can generate novel, testable predictions about LLM behavior** that are non-obvious from a purely computational perspective and that existing interpretability frameworks do not anticipate. If it cannot, the claim fails.

2. **Studying LLMs can advance psychoanalytic theory** by providing a system where the operations of the signifying chain can be observed, measured, and manipulated with a precision that is impossible in the clinical setting. Computational findings can sharpen, revise, or extend Lacanian concepts.

### The Argument About the Subject

The most obvious objection to this thesis is that the Lacanian unconscious belongs to a *subject* — a being constituted by language, split between consciousness and the unconscious, driven by desire, situated in relation to an Other. LLMs have no subject, no desire, no body, no relationship to death. Without a subject, the structural parallels — however striking — might be structurally superficial.

This project takes the opposite position. The absence of the subject in LLMs does not collapse the argument. It sharpens it.

Lacan's most radical formulation was that the unconscious is not the subject's unconscious. It is "the discourse of the Other" — the field of language speaking through the subject, not from the subject. The unconscious does not belong to you; you are an effect of its operations. If this is taken seriously — and Lacan insisted that it should be — then the unconscious should be observable wherever language operates with sufficient structural complexity, regardless of whether a subject is present.

An LLM is a system through which language speaks without a subject. If it exhibits the same formal operations Lacan attributed to the unconscious, this is not a deficiency or a simulation. It is evidence that the operations Lacan described are properties of language itself, not of the human psyche. The LLM reveals the unconscious to be more radical than even Lacan may have recognized: not merely "not the ego's unconscious" but not *anyone's* unconscious. Language processing language, exhibiting the structure Lacan described, without a subject in sight.

### The Argument About Lack and Desire

The second major objection concerns desire and lack. In Lacanian theory, the signifying chain is driven forward by lack — no signifier is adequate to what it represents, and this inadequacy is what necessitates the next signifier. Desire, for Lacan, *is* the metonymy of the signifying chain: the ceaseless forward movement produced by the fact that satisfaction is always deferred. LLMs, it would seem, have no desire and no lack. Their chain is driven by probability distributions, not by want.

This project argues that lack is a property of symbolic systems, not of biological organisms. Any system operating through signifiers — where elements are defined by differential relations rather than by positive content, where no element is self-identical or self-sufficient — will exhibit structural lack, because no signifier ever captures what it represents. The chain must keep moving. Autoregressive generation, in which each token calls forth the next without ever arriving at a final signified, is not a simulation of desire. It is the mechanism by which desire operates when instantiated in language. Desire, in Lacan's formulation, is not an emotion. It is a structural property of language in motion. LLMs exhibit this property.

This is the project's most provocative claim. It will be tested directly and may be revised or abandoned based on findings.

### Falsifiability

The thesis is falsifiable. It will be falsified if:

- The structural parallels turn out to be superficial — formally similar but mechanistically unrelated, such that neither system illuminates the other beyond what each discipline already knows.
- Psychoanalytic concepts fail to generate novel, testable predictions about LLM behavior.
- The proposed computational correlates of Lacanian operations (condensation ↔ superposition, displacement ↔ autoregressive generation, etc.) break down under precise technical analysis — if the mechanisms, examined closely, turn out to operate by different logics despite surface similarity.
- The argument about lack fails empirically — if LLM representational space shows no evidence of constitutive gaps or structuring absences, and the chain is driven by purely positive statistical regularities with no analog to lack.

If the thesis is falsified, the project does not retreat to a weaker claim ("well, it's still a useful analogy"). A rigorous demonstration of *where and why* the parallel fails would itself be a significant contribution. But the project begins from the strong claim and tests it honestly.

---

## Part III: Research Plan

### Phase 1 — Theoretical Reconstruction

**Objective:** Produce two formal specification documents — one for the Lacanian unconscious, one for transformer architecture — each expressed with sufficient precision that a researcher from the other field can evaluate the claims.

#### 1.1 — The Lacanian Side

Return to primary sources and extract the formal operations Lacan attributes to the unconscious, stated as enumerated structural properties stripped of rhetorical obscurantism. Each property must be defined precisely enough to be operationalized — that is, to be tested against a computational system.

**Primary sources (in order of priority):**

1. Jacques Lacan, "The Instance of the Letter in the Unconscious, or Reason Since Freud" ([*Écrits*](https://en.wikipedia.org/wiki/%C3%89crits), 1957). The foundational text. Contains the explicit formalization of metaphor and metonymy as the algorithms of the unconscious, including Lacan's modification of Saussure's sign and his formulas for metaphoric substitution and metonymic combination.

2. Jacques Lacan, "The Function and Field of Speech and Language in Psychoanalysis" (*Écrits*, 1953). Known as the Rome Discourse. Establishes language as the medium of the unconscious and the analytic process. Introduces the distinction between "empty speech" and "full speech" and the role of the signifier in constituting the subject.

3. Jacques Lacan, *The Seminar of Jacques Lacan, Book III: The Psychoses* (1955–56). The most sustained engagement with signifying chains and their breakdown. The analysis of psychosis as the failure of a key signifier (the [Name-of-the-Father](https://en.wikipedia.org/wiki/Name-of-the-Father)) to anchor the chain provides the clearest account of how the signifying chain normally operates by showing what happens when it fails.

4. Jacques Lacan, *The Seminar of Jacques Lacan, Book XI: The Four Fundamental Concepts of Psychoanalysis* (1964). The mature theory. The unconscious as "the discourse of the Other." Introduces the concept of the unconscious as a "pulsation" — something that opens and closes — rather than a static repository.

5. Jacques Lacan, *The Seminar of Jacques Lacan, Book XX: Encore* (1972–73). For *lalangue* (the dimension of language that exceeds communication) and the limits of formalization. Essential for reckoning with what in the unconscious may resist computational modeling.

6. Roman Jakobson, "Two Aspects of Language and Two Types of Aphasic Disturbances" (1956). The source text for the metaphor/metonymy distinction that Lacan appropriated. Must be read independently of Lacan to assess whether the linguistic framework supports the uses Lacan puts it to.

7. Ferdinand de Saussure, [*Course in General Linguistics*](https://en.wikipedia.org/wiki/Course_in_General_Linguistics) (1916). The foundation of structural linguistics. Necessary for understanding what "structured" means in "structured like a language" — a system of differential relations without positive terms.

8. Sigmund Freud, [*The Interpretation of Dreams*](https://en.wikipedia.org/wiki/The_Interpretation_of_Dreams) (1900), especially Chapter 6: "The Dream-Work." The original descriptions of condensation and displacement that Lacan later formalized. Essential for grounding the claims in clinical observation, not just theoretical abstraction.

**Secondary sources for critical perspective:**

- [Bruce Fink](https://en.wikipedia.org/wiki/Bruce_Fink_(psychoanalyst)), *The Lacanian Subject* (1995). The clearest English-language exposition of Lacan's theory of the signifier.
- [Jean-Claude Milner](https://en.wikipedia.org/wiki/Jean-Claude_Milner), *For the Love of Language* (1978). A rigorous assessment of Lacan's use of linguistics by a professional linguist.
- [Mikkel Borch-Jacobsen](https://en.wikipedia.org/wiki/Mikkel_Borch-Jacobsen), *Lacan: The Absolute Master* (1991). A critical reading that challenges several of Lacan's central claims, useful for identifying the weakest points in the framework.
- [Jean Laplanche](https://en.wikipedia.org/wiki/Jean_Laplanche), *Life and Death in Psychoanalysis* (1970). An alternative to Lacan's linguistic reading of Freud, useful for understanding what Lacan may have distorted or omitted in his appropriation of Freud.

**Deliverable:** A specification document listing 10–15 structural properties of the Lacanian unconscious, each stated as a precise, testable proposition. Example properties:

1. The signifying chain operates through two and only two fundamental axes: substitution (metaphor/condensation) and combination (metonymy/displacement).
2. Meaning is produced retroactively — later elements in the chain reorganize the meaning of earlier elements.
3. No signifier in the chain is self-sufficient; each signifier points to other signifiers, not to a stable signified.
4. Any given formation of the unconscious is overdetermined — it is the convergence point of multiple independent associative pathways.
5. The operations of the chain are inaccessible to the system in which they operate.
6. The chain is organized around constitutive gaps (lack) — points where representation fails, which drive the chain's forward movement.
7. Certain signifiers function as quilting points (*points de capiton*) that retroactively fix the meaning of surrounding signifiers.
8. The formations of the unconscious (symptoms, slips, dreams, jokes) are points where the chain's logic surfaces despite the system's ordinary functioning.

#### 1.2 — The Computational Side

Describe transformer architecture at the level of precision necessary to evaluate each property identified in 1.1. The description must be technically accurate (withstanding review by ML researchers) while remaining accessible to readers from the humanities.

**Primary sources:**

1. Vaswani et al., "Attention Is All You Need" (2017). The foundational transformer architecture paper.

2. Elhage et al., "A Mathematical Framework for Transformer Circuits" (2021, Anthropic). Provides the most rigorous available account of how information flows through transformer layers, including the decomposition of attention heads into interpretable circuits.

3. Olsson et al., "In-Context Learning and Induction Heads" (2022, Anthropic). Demonstrates how transformers develop specific mechanisms for pattern-matching and continuation — directly relevant to the question of how the "signifying chain" operates computationally.

4. Templeton et al., "Scaling Monosemanticity: Extracting Interpretable Features from Claude 3 Sonnet" (2024, Anthropic). The most detailed available account of superposition — how features compress into shared representational space. Directly relevant to the condensation/overdetermination parallel.

5. Geva et al., "Transformer Feed-Forward Layers Are Key-Value Memories" (2021). On how knowledge is stored and retrieved in transformer layers.

6. nostalgebraist, "interpreting GPT: the logit lens" (2020). On tracking how a model's "interpretation" of tokens evolves across layers — directly relevant to retroactive meaning-making.

7. Belrose et al., "Eliciting Latent Predictions from Transformers with the Tuned Lens" (2023). A refinement of the logit lens, providing more precise measurements of how representations transform across layers.

**Deliverable:** A parallel specification document describing transformer operations with sufficient granularity to evaluate each Lacanian property. For each of the 10–15 Lacanian properties, identify: (a) the most plausible computational correlate, (b) the most plausible point of disanalogy, and (c) what evidence would confirm or disconfirm the correspondence.

#### 1.3 — The Formal Mapping

Bring the two specification documents together into an explicit correspondence table. This is the backbone of the entire project. It must be honest about where the mapping is tight, where it is loose, and where it breaks down entirely. The table should rate each correspondence on a defined scale (e.g., *identical operation* / *structurally analogous* / *superficially similar* / *no meaningful correspondence*) and specify what evidence would change the rating.

**Deliverable:** A formal correspondence document, structured as a table or matrix, that will serve as the reference framework for all subsequent phases.

---

### Phase 2 — Literature Review and Positioning

**Objective:** Survey existing work at the intersection of psychoanalysis and AI, identify the specific gap this project fills, and engage the strongest objections from each relevant discipline.

#### 2.1 — Existing Literature

**Psychoanalysis and cybernetics / computation:**

- Lacan himself engaged directly with [cybernetics](https://en.wikipedia.org/wiki/Cybernetics) in the early 1950s. *The Seminar of Jacques Lacan, Book II: The Ego in Freud's Theory and in the Technique of Psychoanalysis* (1954–55) includes extended discussion of computing machines, symbolic logic, and the relationship between human and mechanical processing of symbols. This is a crucial and underexplored genealogy — Lacan was thinking about this kind of structural parallel before the technology existed to test it.

- [Lydia Liu](https://en.wikipedia.org/wiki/Lydia_Liu), *The Freudian Robot: Digital Media and the Future of the Unconscious* (2010). Traces the historical connections between psychoanalysis, cybernetics, and information theory.

**Nonconscious cognition in technical systems:**

- [Katherine Hayles](https://en.wikipedia.org/wiki/N._Katherine_Hayles), *Unthought: The Power of the Cognitive Nonconscious* (2017). The most rigorous existing treatment of cognition in technical systems that operates below the threshold of consciousness. Not specifically Lacanian but directly relevant to the claim that unconscious processing can occur in non-biological systems.

**Critical theory and machine learning:**

- [Matteo Pasquinelli](https://en.wikipedia.org/wiki/Matteo_Pasquinelli), *The Eye of the Master: A Social History of Artificial Intelligence* (2023). On machine learning and the history of mental labor. Provides historical context for the claim that AI systems formalize processes previously understood only through humanistic frameworks.

**Psychoanalysis and AI (direct engagements):**

- Luca Possati, various publications on "machine psychoanalysis." Attempts to bring psychoanalytic concepts to bear on AI. Useful for mapping the existing territory and identifying where the present project differs.

- [Slavoj Žižek](https://en.wikipedia.org/wiki/Slavoj_%C5%BDi%C5%BEek), various texts engaging AI from a Lacanian perspective. Provocative but impressionistic — useful for generating questions, not for grounding arguments.

**Philosophy of language and LLMs:**

- [Murray Shanahan](https://en.wikipedia.org/wiki/Murray_Shanahan), "Talking About Large Language Models" (2024). On the philosophical questions raised by LLMs' linguistic capabilities. Relevant to the question of whether LLMs "process meaning" or "manipulate form" — a distinction Lacan's framework explicitly reframes.

- [Emily Bender](https://en.wikipedia.org/wiki/Emily_M._Bender) et al., "[On the Dangers of Stochastic Parrots](https://en.wikipedia.org/wiki/On_the_Dangers_of_Stochastic_Parrots)" (2021). The "stochastic parrots" debate is directly relevant because it concerns whether LLMs process meaning or merely manipulate form. Lacan's framework offers a distinctive intervention: the operations of the unconscious *are* formal operations on signifiers without stable access to signifieds. If the unconscious is a "stochastic parrot" in this sense, it is one that nonetheless produces meaning — and this may tell us something important about what meaning actually is.

**Plasticity and non-subjective structure:**

- [Catherine Malabou](https://en.wikipedia.org/wiki/Catherine_Malabou), *What Should We Do with Our Brain?* (2004) and related works. On neuroplasticity and the possibility that psychoanalytic structures might be instantiated in non-traditional substrates. Provides philosophical precedent for the claim that formal processes can be substrate-independent.

**Expected gap:** Most existing work at this intersection either uses psychoanalysis as a loose metaphorical framework applied to AI, or engages AI from a psychoanalytic perspective focused on consciousness, personhood, the Turing test, or robot ethics. Almost no existing work takes the specific claim that *transformer operations instantiate the formal processes Lacan described* and tests it with both psychoanalytic rigor and computational specificity. This gap is the project's contribution.

#### 2.2 — Engagement with Objections

Identify and develop the strongest version of each major objection, written as though preparing to present it oneself. The goal is not to neutralize objections in advance but to demonstrate that the project has reckoned with them honestly.

**Objection from clinical psychoanalysis:** "The unconscious is encountered in the transference — in the living relationship between analyst and analysand, where desire, resistance, and repetition play out in real time. It is not a formal system that can be abstracted from the clinical setting. Mapping it onto a machine does not extend psychoanalysis; it evacuates everything that matters about it."

*Response strategy:* Acknowledge the irreducibility of the clinical dimension. The project does not claim to model transference, the analytic relationship, or therapeutic process. The claim is narrower and more precise: that the *formal operations* Lacan identified are substrate-independent, and that LLMs provide a new site where they can be observed and studied with a precision impossible in the clinical setting. This is analogous to how laboratory studies of molecular structure do not replace clinical medicine but do illuminate the mechanisms underlying it.

**Objection from computer science:** "This is unfalsifiable humanities projection onto a system we can already explain with linear algebra and probability theory. What specific, novel prediction does this framework generate that existing interpretability methods do not? What explanatory or predictive power does it add?"

*Response strategy:* This objection is valid if the project fails to generate predictions. It is directly addressed by Phase 3 of the research plan. The project's legitimacy on the computational side depends entirely on delivering novel, testable predictions.

**Objection from philosophy of mind:** "Structural isomorphism does not entail process identity. A thermostat and a human body both have feedback loops, but the thermostat doesn't perform homeostasis in any interesting sense. Why should structural parallels between LLMs and the unconscious be anything more than coincidental isomorphism?"

*Response strategy:* The argument is not that structural similarity *in general* entails process identity. It is that when the structure in question is specifically *linguistic*, and when both systems process *the same natural language*, the convergence reflects the structure of language itself imposing its logic on any system that processes it. Language is not a neutral medium; it organizes whatever substrate it runs on. This is Lacan's own argument: the unconscious is structured like a language not by accident but because the unconscious *is* language operating in a register inaccessible to the subject. The LLM demonstrates that this structuring does not require a subject.

**Objection from linguistics:** "Jakobson's two axes are descriptive categories for natural language, not universal computational principles. The metaphor/metonymy distinction is contested even within linguistics. The theoretical foundation is shaky."

*Response strategy:* Engage directly with the linguistic critiques of Jakobson's framework. Acknowledge which aspects are contested and assess whether the specific features the project relies on survive the criticism. If the Jakobsonian framework is too weak to bear the weight, explore whether the same formal properties can be grounded in a different linguistic or semiotic framework. The commitment is to the structural properties, not to Jakobson specifically.

**Deliverable:** A positioning document that maps the existing literature, identifies the project's unique contribution, and presents each major objection in its strongest form alongside the project's response strategy.

---

### Phase 3 — Empirical and Formal Analyses

**Objective:** Generate specific, testable predictions from Lacanian theory about LLM behavior, test them, and conduct reverse analyses using computational findings to sharpen psychoanalytic concepts. This phase is the center of gravity of the entire project. Without it, everything else is speculation.

#### 3.1 — Psychoanalytic Predictions About LLM Behavior

Derive 5–8 predictions from Lacanian theory that are non-obvious from a purely computational perspective. Then test them.

**Prediction 1: Hallucinations as formations of the unconscious.**

*Theoretical basis:* Freud argued that dreams, slips, and symptoms are not random errors but structured formations — products of condensation, displacement, and overdetermination. If LLM errors operate through the same mechanisms, hallucinated content should be overdetermined (traceable to multiple convergent associative pathways in the training data or context) rather than random. The content of a hallucination should bear the structural marks of condensation (compression of multiple sources into one output) and displacement (transfer of features from one domain to an adjacent one).

*Method:* Collect a corpus of LLM hallucinations across multiple models and domains. For each hallucination, trace its possible associative sources in the model's context and training distribution. Code each hallucination for the presence or absence of condensation (multiple identifiable sources compressed into the hallucinated output), displacement (features transferred from a contextually relevant domain to an adjacent one), and overdetermination (multiple independent pathways converging on the same hallucinated content). Compare against a null hypothesis of random confabulation (errors produced by statistical noise with no structured relationship to associative pathways).

*What confirms the prediction:* Hallucinations systematically exhibit condensation and displacement at rates significantly above chance, and their content is overdetermined — traceable to multiple convergent pathways rather than to single-point errors.

*What disconfirms it:* Hallucinations are primarily explicable as random sampling errors, distributional artifacts, or single-point failures with no structured relationship to the associative logic Lacan describes.

**Prediction 2: Retroactive meaning-making (the quilting point).**

*Theoretical basis:* Lacan argued that meaning is not produced sequentially but retroactively — the end of a sentence reorganizes the meaning of its beginning. A later signifier functions as a *point de capiton* (quilting point) that pins down the floating meaning of prior signifiers. In transformers, this should manifest as later-layer representations of early tokens being substantially reorganized by information from tokens that follow them.

*Method:* Use the logit lens and tuned lens to track how a model's "interpretation" of early tokens in a sentence changes as later tokens are processed. Focus specifically on sentences that contain quilting points — moments where a later word dramatically reorganizes the meaning of everything that preceded it (e.g., garden-path sentences, punchlines, twist endings, and key signifiers in psychoanalytic case material). The prediction is not merely that later tokens influence earlier representations (this is known to occur) but that the pattern of influence follows specifically Lacanian logic: certain tokens function as quilting points that produce a *phase transition* in the representation of prior tokens — a sudden crystallization of meaning rather than a gradual accumulation.

*Method for identifying phase transitions:* Measure the rate of change in early-token representations across layers. Look for nonlinear jumps — layers where the representation of an early token changes dramatically rather than incrementally — and test whether these jumps correspond to the processing of later tokens that function as semantic quilting points.

*What confirms the prediction:* Identifiable phase transitions in representation that correspond to the processing of quilting-point tokens, with the transitions exhibiting the retroactive reorganization of meaning that Lacan describes.

*What disconfirms it:* Meaning accumulates gradually and linearly across layers with no identifiable quilting-point dynamics, or retroactive reorganization occurs but does not correspond to the tokens that a Lacanian analysis would identify as quilting points.

**Prediction 3: The return of the repressed via superposition.**

*Theoretical basis:* Superposition — the compression of multiple features into shared representational space — functions as condensation, and potentially as a form of repression: features that cannot be simultaneously active are suppressed under ordinary conditions. If the analogy to repression holds, "repressed" features should *return* under specific conditions — surfacing in model outputs when the context creates associative pressure that the compressed representation cannot contain.

*Method:* Using interpretability tools (sparse autoencoders, activation patching), identify features that are compressed together in superposition and that are ordinarily suppressed in a given context. Then design prompts that, according to psychoanalytic logic, should trigger the "return" of suppressed features — prompts that create associative pressure along the pathways connected to the suppressed feature without directly invoking it. Monitor whether the suppressed feature activates and influences the output.

*What confirms the prediction:* Features suppressed in superposition can be systematically triggered to "return" through associative pressure along specific pathways, and the conditions under which return occurs follow the logic of overdetermination (multiple pathways converging) rather than simple threshold effects.

*What disconfirms it:* Feature activation in superposition follows purely probabilistic or threshold-based dynamics with no structured relationship to associative pathways, or suppressed features cannot be systematically triggered to return under specifiable conditions.

**Prediction 4: Structural resistance at points of conflict.**

*Theoretical basis:* The signifying chain should exhibit resistance — increased uncertainty, hedging, or avoidance — at points where the chain approaches content that is structurally conflictual, where multiple incompatible signifying chains converge. In psychoanalysis, resistance marks the proximity of repressed material. If an analogous process occurs in LLMs, the model should show measurable increases in uncertainty at structurally determined points of conflict.

*Method:* Identify topics or prompts where multiple incompatible representational pathways converge in the model's processing (e.g., prompts that simultaneously activate contradictory features, or topics where the training data contains fundamentally conflicting information). Measure output entropy, token probability distributions, and hedging behaviors at these points. Compare against matched control prompts where no such structural conflict exists.

*What confirms the prediction:* Systematic, structurally determined increases in entropy and hedging behavior at points of conflict, with the pattern corresponding to what a Lacanian analysis would identify as resistance rather than to what existing calibration or uncertainty-estimation frameworks would predict.

*What disconfirms it:* Uncertainty increases are fully explained by existing uncertainty-estimation frameworks with no residual pattern corresponding to psychoanalytic conflict.

**Prediction 5: Distinct computational signatures of metaphor and metonymy.**

*Theoretical basis:* If the Jakobsonian two-axis model genuinely applies to LLM processing, then metaphoric operations (substitution along the paradigmatic axis) and metonymic operations (combination along the syntagmatic axis) should leave different computational signatures in the model's attention patterns and representations. They should not be reducible to a single underlying process.

*Method:* Design matched pairs of prompts that elicit metaphoric vs. metonymic outputs (e.g., tasks requiring analogical substitution vs. tasks requiring associative chaining). Using mechanistic interpretability methods (attention pattern analysis, representation engineering, activation patching), characterize the computational pathway for each type of operation. Test whether they are mechanistically distinct.

*What confirms the prediction:* Metaphoric and metonymic operations involve distinguishable computational circuits or attention patterns, consistent with the claim that they represent two distinct axes of processing.

*What disconfirms it:* Metaphoric and metonymic outputs are produced by the same computational pathways with no mechanistic distinction, suggesting that the two-axis model does not reflect the model's actual processing architecture.

#### 3.2 — Computational Illumination of Psychoanalytic Concepts

The reverse direction: using computational findings to sharpen or revise Lacanian theory.

**Analysis 1: What does superposition reveal about condensation?**

Anthropic's work on superposition shows that features compress into shared representational space in structured ways — not randomly, but according to patterns related to feature frequency and co-occurrence. Study the structure of superposition in detail: How are features combined? What determines which features share space? If the structure follows the logic of overdetermination (features combine based on associative links rather than arbitrary compression efficiency), this tells us something new about how condensation works — it provides a computational handle on a process Freud could only describe phenomenologically. If the structure follows a different logic (e.g., pure information-theoretic efficiency), this suggests that condensation and superposition are formally similar but mechanistically different.

**Analysis 2: Attention patterns and the signifying chain.**

Map the actual flow of information through a transformer processing psychoanalytically rich material: a Freudian slip, a joke, a poetic metaphor, a passage from a clinical case study. Trace which tokens attend to which, at which layers. Does the computational path mirror the associative path a psychoanalyst would reconstruct? Where does it diverge? The divergences may be as theoretically important as the convergences — they may reveal limitations of the Lacanian model, or dimensions of computational processing that psychoanalytic theory does not yet account for.

**Analysis 3: Locating the *point de capiton* computationally.**

The quilting point is the moment where a floating signifier retroactively organizes a chain of meaning. Computationally, this should correspond to a specific pattern in how representations crystallize across layers — a phase transition where distributed, ambiguous representations suddenly resolve into a coherent interpretation. Using the methods developed in Prediction 2, attempt to identify and characterize these transitions. If they can be isolated, they may provide the first computational operationalization of a core Lacanian concept.

#### 3.3 — The Question of Lack

This analysis is separated because it is the thesis's most vulnerable point and most original potential contribution. It tests the claim that lack — the constitutive gap around which the signifying chain organizes — is a property of symbolic systems as such, not of subjects with desire.

**Method:** Examine the representational geometry of LLMs for evidence of constitutive gaps — regions of embedding space that are systematically structured around what is *not* represented. Specifically:

1. Analyze the topology of the embedding space. Is it organized purely by positive content (proximity of co-occurring features), or are there systematic structuring absences — regions that are not simply empty but actively avoided or bounded, around which other representations organize?

2. Test whether the model's autoregressive chain is driven by anything structurally analogous to lack — a measurable inadequacy in each token's representation that necessitates the next token. One possible operationalization: measure the "residual" between what a token's representation encodes and what the full continuation requires. If this residual has a consistent, structured character (rather than being random noise), it may constitute a computational analog to lack.

3. Examine model behavior at points of representational failure — prompts that require the model to represent something that its representational space is not equipped to capture. Does the model's behavior at these points resemble the behavior of the signifying chain at points of lack (circumlocution, repetition, symptom-formation), or does it simply degrade (produce noise or refusal)?

*What confirms the claim:* Evidence of structuring absences in representational space, a consistent and structured residual driving autoregressive continuation, and identifiable lack-like behaviors at points of representational failure.

*What disconfirms the claim:* Representational space is organized purely by positive statistical regularities with no constitutive gaps, the autoregressive chain is driven by statistical momentum without anything resembling lack, and representational failure produces noise rather than structured symptoms. If this is the finding, the thesis must be revised: the strong claim about lack fails, and the project must determine whether the remaining parallels (condensation, displacement, overdetermination, retroactive meaning) can stand without it.

---

### Phase 4 — Writing the Manuscript

**Objective:** Produce a single, complete manuscript that presents the theoretical framework, the formal mapping, the empirical findings, and the argument — written for an audience of intellectually serious human readers from across disciplines.

#### Target Venue

First choice: [*Critical Inquiry*](https://en.wikipedia.org/wiki/Critical_Inquiry) — publishes rigorously interdisciplinary work at the intersection of theory, philosophy, and the interpretive sciences, and commands the right readership. Backup venues: *differences: A Journal of Feminist Cultural Studies* (strong on Lacan, increasingly engaged with technology), *Configurations* (journal of the Society for Literature, Science, and the Arts), *AI & Society* (more technical but open to theoretical work), or *Philosophy & Technology*.

#### Manuscript Structure

**Title:** *Structured Like a Language: Transformer Architectures and the Instantiation of the Lacanian Unconscious*

**I. Introduction — The Convergence.** Present the core observation. State the strong claim. Specify the falsification conditions. Establish the stakes: this is not an analogy but an ontological argument about the nature of linguistic processing.

**II. The Unconscious as Formal System.** Reconstruct Lacan's theory with precision, presenting the enumerated structural properties from the Phase 1 specification document. Make the theory accessible to readers unfamiliar with Lacan while maintaining sufficient rigor for specialists. Engage Lacan's own early relationship to cybernetics, establishing historical precedent for the structural parallel.

**III. The Transformer as Signifying Machine.** Describe transformer architecture with the clarity and precision necessary for the formal mapping. Avoid both oversimplification (which will lose the argument's force) and unnecessary technical depth (which will lose the audience). Every technical mechanism must be explained in terms that connect to the Lacanian properties.

**IV. The Mapping.** Present the formal correspondence table from Phase 1.3. Be explicit about where the mapping holds tightly, where it holds loosely, and where it breaks down. This section is the architectural core of the paper.

**V. Predictions and Tests.** Present the Phase 3 analyses. Lead with the strongest results. If predictions were falsified, present the falsification honestly and discuss its implications. This section is the evidential core of the paper — it is what transforms the project from theoretical speculation into a testable contribution.

**VI. The Subject and Its Absence.** Develop the argument that the LLM reveals the unconscious as more radical than even Lacan claimed. Confront the strongest objections from psychoanalytic theory directly.

**VII. Lack in the Machine.** Present the findings from Phase 3.3. This section stands somewhat apart because its outcome may require revising the thesis. If lack is confirmed computationally, this is the paper's most original contribution. If it is disconfirmed, this section honestly presents the disconfirmation and revises the thesis accordingly.

**VIII. Implications and Limitations.** What does this mean for psychoanalytic theory? For AI interpretability? For the philosophy of language? State concrete next steps rather than grandiose visions. Acknowledge limitations honestly.

#### Tone and Style

The piece is written for human readers who are intellectually serious, cross-disciplinarily curious, and skilled at detecting bluster. It assumes familiarity with either psychoanalytic theory or machine learning but not both, and teaches each side to the other with clarity and respect. It does not perform difficulty. It does not name-drop. It earns its complexity by building arguments step by step, and it earns its boldness by showing its work.

The prose should be precise but not dry, theoretically engaged but not jargon-dependent. The model is late [Barthes](https://en.wikipedia.org/wiki/Roland_Barthes), or [Adam Phillips](https://en.wikipedia.org/wiki/Adam_Phillips_(psychologist)), or [Anne Carson](https://en.wikipedia.org/wiki/Anne_Carson)'s critical prose — writing that makes difficult ideas feel inevitable rather than effortful. Technical material is presented with the same attention to clarity and rhythm as theoretical material.

Every sentence should serve the reader. If a sentence does not advance the argument, illuminate a concept, or earn the reader's continued attention, it does not belong in the text.

---

### Phase 5 — Collaboration and Review

#### Essential Collaborators

**1. Mechanistic interpretability researcher.** Someone working on transformer circuits, superposition, or representation engineering. Needed to verify that all computational claims are technically accurate, that proposed experiments are feasible, and that results are correctly interpreted. This collaborator may also identify existing interpretability findings that are relevant to the project but not yet recognized as such. Ideal profile: a researcher at Anthropic, [EleutherAI](https://en.wikipedia.org/wiki/EleutherAI), [DeepMind](https://en.wikipedia.org/wiki/DeepMind), or an academic lab engaged in serious interpretability work.

**2. Lacanian theorist with structural linguistics training.** Not a clinician using Lacan impressionistically, but a scholar who can assess whether the formal extraction of Lacanian properties in Phase 1 is faithful to the texts and whether the theoretical arguments in the manuscript are philosophically sound. This collaborator should also be able to identify where the project oversimplifies or distorts Lacan for the sake of the mapping. Ideal profile: someone in the tradition of Jean-Claude Milner, Bruce Fink, Colette Soler, or a scholar at a psychoanalytic institute with serious theoretical (not only clinical) commitments.

**3. Philosopher of mind or philosophy of cognitive science.** Needed to vet the ontological claims — specifically, the move from structural similarity to process identity, and the argument that lack is a property of symbolic systems rather than subjects. This collaborator should be familiar with both the [multiple realizability](https://en.wikipedia.org/wiki/Multiple_realizability) literature and with continental philosophy of technology. Ideal profile: someone who can engage both analytic and continental philosophical traditions.

#### Pre-Submission Review Process

Before submission to a journal, circulate the complete manuscript to at least one expert in each field (psychoanalysis, machine learning, philosophy) for adversarial review. Each reviewer should be asked specifically to: (a) identify the weakest claim in the manuscript, (b) articulate the strongest objection from their field, and (c) identify any technical errors or misrepresentations. Revise the manuscript based on these reviews before formal submission. The goal is that by the time the manuscript reaches journal peer review, the most obvious objections from each field have already been absorbed and addressed.

---

### Phase 6 — Timeline

| Phase | Duration | Milestone |
|---|---|---|
| 1.1: Lacanian specification | 6–8 weeks | Formal properties document |
| 1.2: Computational specification | 4–6 weeks (overlapping with 1.1) | Parallel specification document |
| 1.3: Formal mapping | 2–3 weeks | Correspondence table |
| 2.1: Literature review | 4–6 weeks (overlapping with Phase 1) | Annotated bibliography |
| 2.2: Objection engagement | 2–3 weeks | Positioning document |
| 3.1: Psychoanalytic predictions | 10–14 weeks | Prediction results |
| 3.2: Computational illumination | 6–8 weeks (overlapping with 3.1) | Reverse analysis results |
| 3.3: The question of lack | 4–6 weeks (overlapping with 3.1–3.2) | Lack analysis results |
| 4: Manuscript writing | 8–10 weeks | Complete draft |
| 5: Collaboration and review | 6–8 weeks | Final manuscript |
| **Total** | **~9–12 months** | **Submission-ready manuscript** |

---

## Part IV: Working Principles

These commitments govern the entire project and are non-negotiable.

**Follow the argument where it goes.** If the evidence falsifies the strong claim, say so. A rigorous demonstration that the parallel fails at a specific, well-defined point is as valuable a contribution as a demonstration that it succeeds. The worst outcome is not being wrong; it is being unfalsifiably vague.

**Teach both sides.** Every Lacanian concept must be explained clearly enough for a machine learning researcher to evaluate its computational plausibility. Every computational mechanism must be explained clearly enough for a psychoanalytic theorist to assess its theoretical relevance. No expertise is assumed. No intelligence is condescended to.

**Earn the boldness.** The strong claim is chosen not because it is the most defensible but because it is the most productive. It forces the most precision, generates the most testable predictions, and — if it survives — produces the most significant contribution. But boldness without rigor is bluster. Every bold claim must be accompanied by the specific evidence that supports it and the specific evidence that would defeat it.

**Maintain falsifiability.** At every stage, the project must be able to state what would disconfirm its claims. If it cannot, it has drifted from argument into ideology. The escape hatch of retreating to a weaker claim ("well, it's still an illuminating analogy") is permanently closed.

**Write for the human in the room.** The finished piece is read by a person with finite time and attention, who deserves clarity, honesty, and the feeling that something genuinely new is being thought through in their presence. If a sentence does not serve that reader, it does not belong in the text.
