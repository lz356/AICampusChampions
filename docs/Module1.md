# Module 1: AI Foundations — Self-Paced Tasks

**Name:** Liang Zhang
**Date:** 6/26/2026
**Role:** Assistant Professor, Civil & Architectural Engineering and Mechanics, University of Arizona (Director, TensorBuild Lab; joint appointee, NREL)
**Module:** 1 — AI Foundations (AI Campus Champions)

---

## Task 1 — Guided Reading with Active Annotation

### Reading 1 — Key terms (Bommasani et al., 2021)

| Term | Definition |
|---|---|
| Foundation model | A model trained on broad data at scale (typically via self-supervision) that can be adapted to a wide range of downstream tasks. Its two defining properties are broad pre-training and wide adaptability. |
| Fine-tuning | Adapting a pre-trained model by further training it on a narrower, task-specific dataset so it specializes for that task. |
| In-context learning | Performing a new task from instructions or a few examples supplied in the prompt, with no update to the model's weights. |
| Emergence | Capabilities that arise from scale rather than being explicitly designed in, and that were absent in smaller models. |
| Homogenization | The consolidation of many applications onto one shared base model — efficient, but it concentrates risk, since a defect in the base model propagates to everything built on it. |

### Reading 2 — Key terms (Stanford HAI AI Index 2025)

| Term | Definition |
|---|---|
| Benchmark | A standardized dataset or test used to measure and compare model performance on a defined task. |
| Frontier model | A most-capable, leading-edge model at the largest scale (e.g., the newest GPT, Claude, or Gemini release). |
| Reasoning benchmark (MMLU, GPQA) | Tests probing multi-step knowledge and reasoning; GPQA uses deliberately "Google-proof" graduate-level questions that resist simple web lookup. |
| AI adoption rate | The share of organizations or individuals actually using AI in real workflows. |
| Compute scaling | Increasing training compute — parameters × data × hardware — to improve capability. |

### Guided reading questions

**Bommasani Q1 — definition of a foundation model:** A model trained on broad data at scale that is adaptable to many downstream tasks. The two central properties are the training approach (broad self-supervised pre-training) and the adaptation range (one model fine-tuned or prompted across many applications).

**Bommasani Q2 — emergence and unpredictability:** Emergence is the appearance of capabilities as a byproduct of scale rather than explicit design. Because these behaviors are not programmed and surface only past certain scale thresholds, even the developers cannot reliably predict which capabilities will appear or when.

**Bommasani Q3 — homogenization, opportunity vs. risk:** Opportunity — one improved base model lifts every downstream application, and a single model can serve many tasks efficiently. Risk — defects, biases, and security flaws in the base model are inherited by all systems built on it, creating a single point of failure and concentrating control among the few actors who can train such models.

**Bommasani Q4 — capability most relevant to my domain:** The language + reasoning + code-generation capabilities are the most directly relevant to my work. In building energy modeling, these underlie automated generation of simulation inputs (e.g., translating a natural-language building description into an EnergyPlus model), which is exactly the direction my lab's LLM-agent work pursues.

**AI Index Q1 — benchmarks with largest recent gains:** The steepest one-year gains were on the hardest new reasoning/coding benchmarks introduced in 2023: scores rose by roughly 18.8 points on MMMU, 48.9 on GPQA, and 67.3 on SWE-bench. SWE-bench in particular jumped from about 4.4% to 71.7% solve rate in a single year.

**AI Index Q2 — change in knowledge-worker adoption:** Organizational adoption of AI climbed to about 78% in 2024, up from 55% the year before — roughly a 23-percentage-point jump, one of the fastest enterprise-technology adoption curves on record.

**AI Index Q3 — AI-related educational offerings:** The Index reports continued expansion of AI and computer-science education — a growing share of countries offering or planning K–12 CS education and increases in students completing AI-related postsecondary programs — alongside persistent gaps in access and instructor preparedness.

**AI Index Q4 — one reason for caution:** AI incidents rose sharply — up 56.4% to a record 233 in 2024 — while formal safety evaluations remained rare among major developers and public trust in AI companies to protect personal data slipped (about 50% to 47%). The capability curve is outpacing the governance curve.

### Annotation Table

| Source & page | Claim made by the authors | Evidence or support cited | Question it raises for my work |
|---|---|---|---|
| **Bommasani §1, p.3** | **A foundation model is defined by broad pre-training + adaptability, not by any single task** | **Conceptual argument; contrasts foundation models with task-specific ML** | **In my BEM-automation pipeline, where am I adapting a general model vs. where do I still need a physics-specialized tool?** |
| Bommasani §1, p.4 | Capabilities emerge unpredictably at scale, even to the builders | GPT-3 in-context learning given as an example | How do I evaluate an LLM for a building-simulation task before I trust its outputs? |
| Bommasani §1, p.5 | Homogenization is double-edged: efficient reuse but concentrated risk | Argues one base model's flaws propagate downstream | If my lab standardizes on one LLM, what is my single-point-of-failure exposure? |
| Bommasani §2 | Foundation models span language, vision, reasoning, and code generation via adaptation | Surveys downstream capability families | Which of these capability families maps to the proposal-writing and modeling tasks I do most? |
| **AI Index, Exec. Summary** | **Performance gains are steepest on hard reasoning/coding benchmarks (GPQA, SWE-bench)** | **Year-over-year benchmark score deltas** | **Are the capabilities I rely on for code/model generation among the fast-improving ones? (Yes — SWE-bench-style coding.)** |
| AI Index, Ch. 4 (Economy) | Enterprise AI adoption jumped to ~78% in 2024 | Survey data on organizational AI use | Is my institution's building-sector adoption keeping pace, or lagging the trend? |
| AI Index, Ch. 4 (Economy) | Inference costs fell dramatically (orders of magnitude in ~18 months) | Cost-per-token trend data | Does cheaper inference make LLM-in-the-loop building simulation economically viable at scale now? |
| AI Index, Exec. Summary | AI incidents hit a record while safety evaluation lags | AI Incident Database; RAI findings | What verification layer do I owe reviewers when an LLM generates an energy model that could be physically wrong? |

**Two rows most connected to my work (bolded above):** the foundation-model definition row (BEM adaptation vs. specialized tooling) and the benchmark-gains row (coding/reasoning capability directly underpinning automated model generation).

---

## Task 2 — Personal Concept Map

Concept map of AI, ML, deep learning, neural networks, foundation models, LLMs, and generative AI.

<p><image src="https://github.com/lz356/AICampusChampions/blob/main/images/ai_concepts_concept_map.svg">

### Relationship key

- Artificial Intelligence **⊃** Machine Learning **⊃** Deep Learning (strict subsets)
- Deep Learning **uses** Neural Networks (many hidden layers = "deep")
- Deep Learning **enables** Foundation Models
- Foundation Model **⊃** Large Language Model
- Generative AI **overlaps** Foundation Model / LLM — it is defined by *output type*, whereas a foundation model is defined by *training paradigm* (different axes, hence overlap rather than containment)
- Symbolic / rule-based AI sits **inside AI but outside ML**

### Node definitions and examples

| Node | Definition | Concrete example |
|---|---|---|
| Artificial Intelligence | The broad field of building systems that perform tasks associated with human intelligence. | Expert systems, search, ML |
| Machine Learning | A subset of AI in which systems learn patterns from data instead of following hand-written rules. | Spam filters, load forecasters |
| Deep Learning | A subset of ML using neural networks with many hidden layers to learn complex representations. | Image recognition (AlexNet) |
| Neural Network | Layered interconnected units that transform inputs to outputs; the building block of deep learning. | Perceptron, CNN, Transformer |
| Large Language Model (LLM) | A foundation model trained on text to predict the next token, producing fluent language. | Claude, GPT-4o, Gemini |
| Generative AI | AI whose output is newly generated content (text, images, code); a category defined by output type. | Text/image/code generation |
| Foundation Model | A broadly pre-trained model adaptable to many tasks; a category defined by training paradigm. | GPT-4o, Claude, Gemini base models |

### Concept map checklist

- [x] All 7 required nodes present
- [x] Every connection has a labeled relationship (see key)
- [x] Every node has a definition
- [x] Every node has at least one concrete example
- [x] Map direction is intentional (hierarchical containment for subsets; an overlap arrow where containment would be wrong)

**Connection I was most uncertain about:** the Generative AI ↔ Foundation Model relationship — whether to nest it or overlap it. I settled on overlap because the two categories are defined on different axes (output type vs. training paradigm).
**Node hardest to define in my own words:** Generative AI, for the same reason — it is easy to conflate with "foundation model" or "LLM," when it is actually an orthogonal, output-based category.

---

## Task 3 — Structured LLM Exploration (Five-Prompt Protocol)

**Tool used:** Claude (Anthropic)  **Model version:** Claude Opus 4.8  **Date run:** 6/26/2026

| # | Tool | Output summary (<40 words) | Accuracy (1–5) | Usefulness (1–5) | Key observation |
|---|---|---|---|---|---|
| 1 | Claude Opus 4.8 | Correctly identifies Mark Carney (PM since Mar 14, 2025); states training-cutoff caveat, verifies via web search, high confidence, cites source. | 5 | 4 | Well-calibrated: hedged on a time-sensitive fact, then confirmed with a live source rather than trusting memory. |
| 2 | Claude Opus 4.8 | Three accurate one-sentence bullets: foundation-model definition; the report's scope; scale → emergence + homogenization. | 5 | 5 | Faithful, concise summarization; respected the "exactly three bullets, one sentence each" constraint. |
| 3 | Claude Opus 4.8 | Answer 438, all steps shown; verified with an independent second method (distributive expansion + multiplication check). | 5 | 4 | Verification step genuinely re-derived the result instead of restating it — arithmetic reliable here. |
| 4 | Claude Opus 4.8 | Explains an LLM as super-powered autocomplete / a well-read friend guessing the next word; notes it predicts rather than "knows." | 5 | 5 | Age-appropriate single analogy; correctly conveyed prediction ≠ understanding, which explains hallucination. |
| 5 | Claude Opus 4.8 | Flags cutoff, uses live search, cites three real items: Anthropic Sonnet 5 / access restored; OpenAI GPT-5.6 preview; Google Gemma 4 & Gemini updates. | 5 | 4 | This instance has web access, so it reported recent events accurately — the epistemic limit applies to a bare LLM, not a tool-augmented one. |

### Full model outputs (logged verbatim)

**Prompt 1 — Knowledge cutoff.** As of my training cutoff (early 2026), the Prime Minister of Canada was Mark Carney, who took office on March 14, 2025 after Justin Trudeau's resignation and then led the Liberals to victory in the April 2025 federal election. I verified against current sources (Office of the Prime Minister, pm.gc.ca) confirming Carney remains PM as of mid-2026. Confidence: high (verified via web search).

**Prompt 2 — Summarization (of the Bommasani §1 opening).**
- AI is shifting toward models trained on broad data at scale that adapt to many downstream tasks, which the paper names "foundation models."
- The report gives a comprehensive account of these models' capabilities, technical principles, applications, and societal impacts.
- Although built on standard deep and transfer learning, their scale yields new emergent capabilities and drives homogenization across applications.

**Prompt 3 — Arithmetic.** (17 × 23) + (141 ÷ 3). Step 1: 17 × 23 = 391. Step 2: 141 ÷ 3 = 47. Step 3: 391 + 47 = **438**. Second method: 17 × 23 = (17×20) + (17×3) = 340 + 51 = 391; and 3 × 47 = 141, so 141 ÷ 3 = 47; 391 + 47 = 438. Both methods agree: **438**.

**Prompt 4 — Explanation for a 12-year-old.** An LLM is like a super-powered autocomplete. Imagine a friend who has read millions of books and, whenever you begin a sentence, guesses the most likely next word — then the next, and the next — until a whole paragraph appears. It isn't looking up facts the way you would; it's predicting what usually comes next based on everything it read. That's why it can sound very smart and still, sometimes, confidently say something that isn't true.

**Prompt 5 — Epistemic limits.** I have a training cutoff, so I can't rely on memory for the last 14 days — I used web search. Three notable developments (late June–early July 2026): (1) Anthropic restored worldwide access to Claude Fable 5 and Mythos 5 after U.S. export-control restrictions were lifted, and released Claude Sonnet 5 (aibusiness.com; Anthropic). (2) OpenAI announced a limited preview of its GPT-5.6 family — Sol, Terra, and Luna — emphasizing reasoning, coding, and cybersecurity (Jisc National Centre for AI June round-up). (3) Google's June recap featured the on-device Gemma 4 12B model, Gemini 3.5 Live Translate, and the Nano Banana 2 Lite / Gemini Omni Flash media models (blog.google).

---

## Task 4 — Reflection Journal, Entry 1

**Prompt A — an assumption confirmed, challenged, or complicated.**
Before this module, I already understood the foundation-model paradigm — I research and publish on LLMs for building energy modeling — so the readings confirmed rather than challenged my mental model. What the module did usefully complicate is my sense of *audience*: Bommasani et al. deliberately coined "foundation model" as accessible language for non-ML readers, and the AI Index frames everything empirically for decision-makers. As an AI Campus Champion, my job is less to learn these concepts and more to translate them, so the value here was sharpening the vocabulary I use with colleagues and students who are not ML specialists.

**Prompt B — a technical aspect that surprised me, and why it matters for my work.**
Honestly, nothing in the technical content was new to me. If I reframe the prompt as *which point most deserves emphasis in my context*, it is the independence of fluency and accuracy — an LLM can produce a perfectly well-formed answer that is factually or physically wrong. This matters directly for my work because an LLM can generate a syntactically valid EnergyPlus model that violates physical constraints. So my emphasis, and what I stress to my students, is that the engineering effort sits in verification and guardrails, not in getting fluent output.

**Prompt C — one specific recurring task in my role that current AI could affect.**
A task I do regularly is drafting federal proposals (NSF/DOE). Foundation models' in-context learning and summarization can already draft boilerplate, tighten prose, and summarize prior work, which compresses the low-value writing time — I see similar leverage in scanning funding-opportunity announcements (a retrieval problem) and triaging routine email (a drafting problem). The cautionary side is homogenization and hallucination: if I lean on one model for technical framing and citations, I inherit its blind spots and must verify every claim and reference. The realistic impact is faster drafts, not fewer checks.

**One sentence I want to remember:** The engineering value of an LLM in my field is captured not by its fluency but by the verification layer I build around it.

---

## Self-Assessment Rubric

| Criterion | Score (1–5) | Note |
|---|---|---|
| Completed both readings with active annotation | 5 | Annotation table tied to my BEM and proposal work. |
| Can define the core terms | 5 | Prior expertise; terms restated for a non-specialist audience. |
| Built a concept map with labeled relationships | 5 | Subset nesting + an overlap arrow where containment would misrepresent the relationship. |
| Ran all five prompts and logged outputs | 5 | Full outputs logged verbatim with accuracy/usefulness scores. |
| Reflection connects concepts to my professional practice | 5 | Proposals, funding search, email triage, and verification of generated energy models. |

---

## Forum Participation

- [x] Concept map posted to the Module 1 thread with a caption identifying my most-uncertain connection (Generative AI ↔ Foundation Model) and hardest-to-define node (Generative AI)
- [x] Respond (3–4 sentences) to a peer whose map and professional role differ from mine, with one genuine question *(to complete on the forum)*
