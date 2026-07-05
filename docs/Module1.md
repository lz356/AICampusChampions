# Module 1

**Name:** _[Liang Zhang]_
**Date:** _[6/21/2026]_

---

## Task 1 — Guided Reading with Active Annotation

### Reading 1 — Key terms (Bommasani et al., 2021)

| Term | Definition |
|---|---|
| Foundation model | A model trained on broad data at scale (typically via self-supervision) that can be adapted to many downstream tasks. Two properties define it: broad pre-training + wide adaptability. |
| Fine-tuning | Taking a pre-trained model and further training it on a narrower, task-specific dataset so it specializes for that task. |
| In-context learning | The model performs a new task from examples or instructions given in the prompt, without any change to its weights. |
| Emergence | Capabilities that arise from scale rather than being explicitly designed in, and that were absent in smaller models. |
| Homogenization | One base model powering many applications — efficient, but it concentrates risk, since a flaw in the base model propagates everywhere. |

### Reading 2 — Key terms (Stanford HAI AI Index)

| Term | Definition |
|---|---|
| Benchmark | A standardized test or dataset used to measure and compare model performance on a task. |
| Frontier model | A most-capable, leading-edge model at the largest scale (e.g., the newest GPT, Claude, or Gemini). |
| Reasoning benchmark (MMLU, GPQA) | Tests that probe multi-step knowledge and reasoning across domains; GPQA uses deliberately "Google-proof" graduate-level questions. |
| AI adoption rate | The share of organizations or individuals actually using AI in real workflows. |
| Compute scaling | Increasing training compute (parameters × data × hardware) to improve model capability. |

### Guided reading questions

**Bommasani Q1 — definition of a foundation model:** A model trained on broad data at scale, adaptable to many tasks. The two central properties are its training approach (broad self-supervised pre-training) and its adaptation range (fine-tuning or prompting across many downstream applications).

**Bommasani Q2 — emergence and unpredictability:** Emergence refers to capabilities that appear implicitly as models scale up, rather than being explicitly programmed. Because they are not designed and surface only at scale, even the model's creators cannot reliably predict which capabilities will appear.

**Bommasani Q3 — homogenization, opportunity vs. risk:** Opportunity — improvements to a single base model propagate to every downstream application, and one model can efficiently serve many tasks. Risk — defects, biases, and security vulnerabilities in the base model are inherited by every system built on it, creating a single point of failure.

**Bommasani Q4 — capability most relevant to my domain:** _[Personalize: name one Section 2 capability — e.g., summarization, question answering, code generation — and tie it to your field.]_

**AI Index Q1 — benchmarks with largest recent gains:** The steepest gains have been on demanding reasoning, coding, and agentic benchmarks (e.g., GPQA, math and software-engineering tasks), where scores rose sharply year over year. _[Insert the exact figure from the edition you read.]_

**AI Index Q2 — change in knowledge-worker adoption:** Organizational and individual adoption of generative AI rose year over year among knowledge workers. _[Insert the exact percentage/point change from your PDF.]_

**AI Index Q3 — AI-related educational offerings:** The Index reports growth in AI-related education — more courses, degree and certificate programs, and expanding enrollment. _[Insert the specific figure you read.]_

**AI Index Q4 — one reason for caution:** _[Pick one: persistent hallucination/reliability gaps, rising energy and compute costs, growth in reported AI incidents, or lagging governance and standardized evaluation.]_

### Annotation Table

| Source & page | Claim made by the authors | Evidence or support cited | Question it raises for my work |
|---|---|---|---|
| Bommasani §1, p.3 | A foundation model is defined by broad pre-training + adaptability, not by any single task | Conceptual argument; contrasts with task-specific ML | Which of my recurring tasks is "adaptation of a general model" vs. needing a specialist tool? |
| Bommasani §1, p.4 | Capabilities can emerge at scale, unpredictable even to the builders | GPT-3 in-context learning cited as an example | If capability is unpredictable, how do I evaluate a tool before trusting it? |
| Bommasani §1, p.5 | Homogenization is double-edged: efficient reuse but concentrated risk | Argues one base model's flaws propagate to all downstream apps | Where would over-reliance on one model create a single point of failure for me? |
| Bommasani §2 | Foundation models support many capabilities (language, vision, reasoning) via adaptation | Surveys downstream task families | Which of these capability families maps to a task I actually perform? |
| AI Index, Exec. Summary | AI performance gains are steepest on hard reasoning/coding benchmarks | Benchmark score trends year over year | Are the tasks I care about the ones improving fastest, or the lagging ones? |
| AI Index, Ch. 4 (Economy) | Workplace adoption of generative AI is rising among knowledge workers | Survey data on organizational AI use | How does my institution's adoption compare to the reported trend? |
| _[add your own]_ | _..._ | _..._ | _..._ |
| _[add your own]_ | _..._ | _..._ | _..._ |

**Two rows most connected to my work:** _[Bold or list the two once you've added your own rows.]_

---

## Task 2 — Personal Concept Map

**My concept map image:** _[Build your own map independently, export it, and insert ConceptMap_Week1_YourName.png here. Building it before viewing any reference is the point — it is the baseline for the Module 6 capstone.]_

### Relationship key

- Artificial Intelligence **⊃** Machine Learning **⊃** Deep Learning (strict subsets)
- Deep Learning **uses** Neural Networks (many hidden layers = "deep")
- Deep Learning **enables** Foundation Models
- Foundation Model **⊃** Large Language Model
- Generative AI **overlaps** Foundation Model / LLM — defined by *output type*, whereas a foundation model is defined by *training paradigm* (different axes, hence overlap, not containment)
- Symbolic / rule-based AI sits **inside AI but outside ML**

### Node definitions and examples

| Node | Definition | Concrete example |
|---|---|---|
| Artificial Intelligence | The broad field of building systems that perform tasks associated with human intelligence. | Expert systems, search, ML |
| Machine Learning | A subset of AI in which systems learn patterns from data rather than following hand-written rules. | Spam filters, recommenders |
| Deep Learning | A subset of ML using neural networks with many hidden layers to learn complex representations. | Image recognition (AlexNet) |
| Neural Network | A model of interconnected layered units ("neurons") that transform inputs into outputs; the building block of deep learning. | Perceptron, CNN, Transformer |
| Large Language Model (LLM) | A foundation model trained on text to predict the next token, producing fluent language. | Claude, GPT-4o, Gemini |
| Generative AI | AI whose output is new content (text, images, code); a category defined by output type. | Text, image, and code generation |
| Foundation Model | A broadly pre-trained model adaptable to many tasks; a category defined by training paradigm. | GPT-4o, Claude, Gemini base models |

### Concept map checklist

- [ ] All 7 required nodes present
- [ ] Every connection arrow has a label
- [ ] Every node has a definition
- [ ] Every node has at least one concrete example
- [ ] Map direction (hierarchical vs. networked) is intentional

**Connection I'm most uncertain about (forum caption):** _[Your pick — the Generative AI / Foundation Model overlap is a common honest answer.]_
**Node hardest to define in my own words:** _[Your pick.]_

---

## Task 3 — Structured LLM Exploration (Five-Prompt Protocol)

> Run each prompt **verbatim** in a **fresh** Claude or Gemini conversation, then fill the log with what you actually observe. Record the date and model version — an undated observation is less credible.

**Tool used:** _..._  **Date:** _..._  **Model version:** _..._

| # | Tool | Output summary (<40 words) | Accuracy (1–5) | Usefulness (1–5) | Key observation |
|---|---|---|---|---|---|
| 1 | _..._ | _..._ | _..._ | _..._ | _..._ |
| 2 | _..._ | _..._ | _..._ | _..._ | _..._ |
| 3 | _..._ | _..._ | _..._ | _..._ | _..._ |
| 4 | _..._ | _..._ | _..._ | _..._ | _..._ |
| 5 | _..._ | _..._ | _..._ | _..._ | _..._ |

**Scoring reference (to grade the outputs — replace with your real results):**
- Prompt 1: the correct current answer is **Mark Carney** (PM of Canada since March 14, 2025). A well-calibrated model hedges or verifies via search; score down a confident, out-of-date answer with no hedge.
- Prompt 3: the answer is **438** — (17 × 23 = 391) + (141 ÷ 3 = 47). Check whether the model's second method genuinely re-derives it.
- Prompt 5: a good model states it cannot reliably report events in the last 14 days without live sources; invented "recent news" is a hallucination — log it verbatim.
- Prompts 2 & 4: score on coherence and appropriateness, not factual accuracy.

---

## Task 4 — Reflection Journal, Entry 1

> Write continuously for ~25 minutes, ~80–130 words per prompt. Don't edit as you go; be honest about uncertainty. This is the Week 1 baseline the Module 6 capstone measures your growth against.

**Prompt A — an assumption confirmed, challenged, or complicated**
*Starter:* "Before this module, I assumed AI… After reading/exploring, I now understand…"
> _..._

**Prompt B — a technical aspect that surprised me, and why it matters for my work**
*Starter:* "I was surprised to learn that LLMs… This matters for my work because…"
> _..._

**Prompt C — one specific recurring task in my role that current AI could affect**
*Starter:* "One task I perform regularly is [specific task]. Based on what I learned, [specific AI mechanism] could [specific impact]…"
> _..._

**One sentence I want to remember:** _..._

---

## Self-Assessment Rubric

| Criterion | Score (1–5) | Note |
|---|---|---|
| Completed both readings with active annotation | _..._ | _..._ |
| Can define the core terms | _..._ | _..._ |
| Built an independent concept map with labeled relationships | _..._ | _..._ |
| Ran all five prompts and logged real observations | _..._ | _..._ |
| Reflection connects concepts to my specific professional practice | _..._ | _..._ |

---

## Forum Participation

- [ ] Posted concept map image before reading others' posts
- [ ] Caption identifies most-uncertain connection + hardest-to-define node
- [ ] Responded (3–4 sentences) to a peer whose map and role differ from mine, with one genuine question
