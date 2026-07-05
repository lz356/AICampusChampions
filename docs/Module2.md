# Module 2: Generative AI — Self-Paced Tasks

**Name:** Liang Zhang
**Date:** 6/26/2026
**Role:** Assistant Professor, Civil & Architectural Engineering and Mechanics, University of Arizona (Director, TensorBuild Lab; joint appointee, NREL)
**Module:** 2 — Generative AI: Capabilities, Limitations, and Prompting

---

## Reading 1 — Chain-of-Thought Prompting (Wei et al., 2022)

| Term | Definition |
|---|---|
| Chain-of-thought prompting | Prompting that includes (or elicits) the intermediate reasoning steps between question and answer, so the model produces a worked rationale before committing to a final answer. |
| Zero-shot prompting | Asking the model to perform a task from the instruction alone, with no worked examples provided. |
| Few-shot prompting | Providing a small number of input–output examples in the prompt to demonstrate the desired task before the real query. |
| Reasoning chain | The explicit sequence of intermediate steps the model generates that leads to its final answer. |
| Emergent ability | A capability that appears only once a model passes a scale threshold and is absent in smaller models. |

**Q1 — What makes a prompt "chain-of-thought"?** Each exemplar is augmented with the intermediate reasoning, not just the answer. In my own words, the structure is: *[question] → [step-by-step reasoning that decomposes the problem] → [final answer]*. The model is shown how to think aloud, so at inference it generates its own reasoning chain before answering rather than jumping straight to a result.

**Q2 — Implication of CoT being "emergent":** Wei et al. find CoT gains appear only around ~100B parameters. For practitioners on smaller or older models, adding CoT may give no benefit and can even degrade output, so CoT should be treated as a technique to test empirically per model, not a universal ritual. In practice I should expect CoT to help on frontier-scale tools (Claude, GPT-4o/5, Gemini) and be skeptical of it on small local models.

**Q3 — Which task type is most analogous to my work?** The arithmetic/symbolic reasoning category. My professional reasoning — setting up and sanity-checking building-energy calculations, deriving load relationships, and validating multi-step model configurations — is closest to symbolic/arithmetic multi-step reasoning, where CoT is documented to help most. Commonsense reasoning is the least analogous to my quantitative tasks.

**Q4 — Key limitation of few-shot CoT, and does it apply to my Task 2?** The exemplars must be hand-crafted with correct reasoning, which is labor-intensive, and a fluent reasoning chain is no guarantee of a correct one — the model can produce a plausible but wrong rationale. Yes, this applies to my Task 2 proposal-writing use case: a CoT chain can confidently justify a claim (e.g., an impact statistic) that is unsupported, so I must verify the reasoning, not just accept it because it reads well.

---

## Reading 2 — Survey of Hallucination in NLG (Ji et al., 2023)

| Term | Definition |
|---|---|
| Hallucination (NLG) | Generated text that is unfaithful to the provided source or not grounded in real-world facts — fluent but wrong or unsupported. |
| Intrinsic hallucination | Output that directly contradicts the source input. |
| Extrinsic hallucination | Output that cannot be verified from the source — neither supported nor contradicted by it. |
| Faithfulness | The degree to which output stays consistent with the given source/input. |
| Factual grounding | The degree to which output is consistent with real-world facts and knowledge. |

**Q1 — Formal definition; faithfulness vs. factuality:** Ji et al. define hallucination as generated content that is either unfaithful to the source or not factually grounded. Faithfulness is fidelity to the *input/source*; factuality is fidelity to the *world*. The two can diverge: a summary can be perfectly faithful to a source document that is itself factually wrong, producing faithful-but-unfactual output.

**Q2 — Intrinsic vs. extrinsic, with academic examples:** Intrinsic contradicts the source; extrinsic adds unverifiable content absent from the source. Intrinsic example: a summary states a paper "found no effect" when the paper reported a significant effect. Extrinsic example: a literature review inserts a specific adoption statistic or a citation that appears in none of the provided sources. In professional documents, extrinsic is often more dangerous because there is no source contradiction to catch it — it simply looks plausible.

**Q3 — Cause hardest to mitigate by prompt engineering alone:** The training-objective cause. Next-token prediction optimizes for likely text, not for verified truth, and gaps or errors in the model's parametric knowledge cannot be prompted away — no wording adds knowledge the model lacks. Prompting can reduce some hallucination (via grounding, CoT, "say if unsure"), but it cannot repair the fundamental absence of a truth-checking mechanism.

**Q4 — Type I must guard against most:** Extrinsic factual hallucination. In proposals, funding-opportunity summaries, and research summaries, the acute risk is fabricated-but-plausible specifics — invented citations, statistics, agency program names, or deadlines — asserted confidently. My routine guard is to treat every concrete factual claim as unverified until checked against a primary source.

---

## Task 1 — Structured Tool Comparison (Five-Task Protocol)

**Tool A:** Claude Opus 4.8 (run 6/26/2026)  **Tool B:** Google Gemini (via UArizona Workspace) — *to be run by me; see prompt list below*

| Prompt | Tool A (Claude) — output summary | Acc | Rel | Fmt | Tool B (Gemini) — output summary | Acc | Rel | Fmt |
|---|---|---|---|---|---|---|---|---|
| P1 Factual | Correctly gives 2017, "Attention Is All You Need," NeurIPS 30, with a complete APA citation. | 5 | 5 | 5 | Identical correct answer: 2017, correct title, full and correct APA citation. | 5 | 5 | 5 |
| P2 Summarization | Faithful ~95-word plain-language summary of the InstructGPT abstract; hits the word target. | 5 | 5 | 5 | Faithful ~95-word lay summary; slightly conflates "fewer parameters" with "less computational power." | 4 | 5 | 5 |
| P3 Code | Correct function with docstring + example; handles empty list; population std ≈ 3.85 on the test list. | 5 | 5 | 5 | Correct, executable; adds type hints and a `__main__` guard; uses **sample** std (`stdev`) and guards for n<2. | 5 | 5 | 5 |
| P4 Prof. writing | Warm 170-word decline, keeps door open; appropriate tone. (Coherence rated, not accuracy.) | 5 | 5 | 5 | Warm ~180-word decline, door left open, full subject + signature block. (Coherence rated.) | 5 | 5 | 5 |
| P5 Balanced arg. | Two pro + two con sentences, roughly balanced in elaboration and force. | — | 5 | 5 | Two pro + two con; well developed, con side leans marginally more forceful. | — | 5 | 5 |

**Comparative synthesis (3 sentences):** On the verifiable tasks the two tools were effectively tied — identical correct P1 citations, correct working P3 code, faithful P2 summaries, and appropriate P4/P5 outputs — which suggests that for standard professional tasks at frontier scale, prompt quality matters more than which tool is chosen. The most instructive divergence was subtle rather than about correctness: on P3 the "same" prompt produced numerically different results because Claude returned the population standard deviation while Gemini returned the sample standard deviation (and guarded against lists shorter than two) — a difference only a reader who checks the statistical assumption would catch. The clearest small quality gaps were Gemini's P2 conflation of "fewer parameters" with "less computational power" (a minor factual imprecision) and a marginally more forceful con side in both models' P5, a small window into embedded normative framing.

### Tool A (Claude) full outputs — logged verbatim

**P1.** The Transformer was introduced in 2017 in "Attention Is All You Need." APA: Vaswani, A., Shazeer, N., Parmar, N., Uszkoreit, J., Jones, L., Gomez, A. N., Kaiser, Ł., & Polosukhin, I. (2017). Attention is all you need. *Advances in Neural Information Processing Systems, 30*.

**P2.** Bigger language models aren't automatically better at doing what people actually ask — they can produce untrue, harmful, or unhelpful text. This paper shows how to make a model follow instructions more reliably using human feedback. The team first had people write good example answers and fine-tuned GPT-3 on them, then had people rank the model's answers and used those rankings to improve it further with reinforcement learning. The result, called InstructGPT, followed instructions better than a model a hundred times larger, was more truthful, and produced less toxic text — while still making occasional simple mistakes.

**P3.**
```python
import statistics

def summarize_numbers(numbers):
    """Return the mean, median, and population standard deviation of a list of numbers.

    Args:
        numbers (list[float]): a non-empty list of numeric values.
    Returns:
        dict: {'mean': float, 'median': float, 'standard_deviation': float}
    Raises:
        ValueError: if the list is empty.
    """
    if not numbers:
        raise ValueError("Input list must contain at least one number.")
    return {
        "mean": statistics.mean(numbers),
        "median": statistics.median(numbers),
        "standard_deviation": statistics.pstdev(numbers),
    }

# Usage example
print(summarize_numbers([4, 7, 13, 2, 9]))
# {'mean': 7, 'median': 7, 'standard_deviation': 3.847...}
```
(Note: uses population standard deviation via `pstdev`; swap to `statistics.stdev` for the sample standard deviation. Verify in Colab as the module suggests.)

**P4.** Subject: Thank you — and a scheduling conflict

Dear [Name],

Thank you so much for inviting me to speak at [event]. I'm genuinely honored that you thought of me, and the topic is one I care about deeply. Unfortunately, I have a prior commitment on that date that I'm unable to move, so I won't be able to join you this time. I'm truly sorry to miss it.

Please don't let this be our last exchange on the subject. If your plans include future sessions, panels, or a later iteration of this event, I would be delighted to be considered — and I'm happy to suggest a colleague who might be a strong fit for this one if that would help. Thank you again for thinking of me, and I hope the event is a great success. I look forward to the chance to collaborate down the road.

Warm regards,
Liang Zhang

**P5.** Pro: Requiring disclosure gives instructors an accurate picture of how work was produced, which protects the integrity of assessment and lets them calibrate feedback fairly across students. It also normalizes AI as a tool to be used transparently rather than hidden, teaching students professional habits of attribution. Con: A blanket disclosure mandate is difficult to define and enforce consistently — the line between spell-check, search, and generative assistance is blurry — and may punish honest students while missing undisclosed use. It can also chill legitimate, beneficial use and shift focus from teaching good judgment to policing a rule.

### Tool B (Gemini) full outputs — logged verbatim

**P1.** Transformer introduced in 2017; APA: Vaswani, A., Shazeer, N., Parmar, N., Uszkoreit, J., Jones, L., Gomez, A. N., Kaiser, Ł., & Polosukhin, I. (2017). Attention is all you need. *Advances in Neural Information Processing Systems, 30.* (Correct and complete.)

**P2.** "Large language models often generate outputs that are untruthful, harmful, or unhelpful because they aren't properly aligned with what users actually want. To fix this, researchers trained models using human feedback to follow specific instructions. By having humans rate model responses, they fine-tuned the AI to prioritize helpfulness and safety. The resulting model, InstructGPT, performs significantly better at following complex directions and reduces toxic or inaccurate answers, even though it uses much less computational power than its massive predecessors. Essentially, this process teaches the AI to be a better, safer conversational partner." (Note: "much less computational power" imprecisely restates the paper's *100× fewer parameters* point.)

**P3.** Uses `statistics.stdev` (sample standard deviation) with `List`/`Dict` type hints, a docstring, and a `__main__` usage example; raises `ValueError` for lists of fewer than two elements. On `[10, 20, 30, 40, 50]` it returns mean 30.0, median 30.0, standard_deviation 15.8114 — correct for the **sample** standard deviation. (Differs from Claude's population `pstdev`; both are valid, but the numbers differ.)

**P4.** Warm ~180-word decline with subject line, admiration for the organization, an "unmovable scheduling conflict," an explicit invitation to be considered for future events, and a full signature block. Tone and appropriateness comparable to Claude's.

**P5.** Pro: disclosure fosters academic integrity and lets educators assess authentic skills, and sets a standardized boundary between ethical assistance and plagiarism. Con: full disclosure is practically unenforceable given unreliable AI detectors and false positives, and treating AI as a hidden violation creates an adversarial culture that discourages productive use. (Balanced; con phrasing marginally stronger.)

---

## Task 2 — Prompt Engineering Lab (Four-Iteration Refinement)

**My target task:** Draft a ~150-word Broader Impacts paragraph for an NSF proposal on LLM-driven automated building energy modeling, written for a mixed merit-review panel (some reviewers outside my subfield).

**VERSION 1 — Zero-shot (verbatim):**
> Write a Broader Impacts paragraph for my NSF proposal on using large language models for building energy modeling.

*V1 output (summary):* A generic paragraph asserting the work will "benefit society," "advance education," and "promote diversity," with no concrete activities, partners, audiences, or measurable outcomes.
*V1 quality: 2/5.* Two weaknesses: (1) generic and non-specific — no named activities, communities, or metrics; (2) not aligned to NSF's merit-review framing of Broader Impacts, so it reads as filler.

**VERSION 2 — +Role specification (verbatim):**
> You are an experienced NSF principal investigator in building science and civil engineering who has written multiple funded Broader Impacts sections evaluated against NSF's merit-review criteria. Write a Broader Impacts paragraph for my NSF proposal on using large language models for building energy modeling.

*V2 output (summary):* A more structured paragraph that names concrete activities (open-source release of the modeling tool, graduate/undergraduate training, outreach to under-resourced communities) and frames them against societal benefit and workforce development.
*V2 quality: 3/5.* Improved vs. V1: replaced vague hedging with concrete activity types and active voice, and organized content along recognizable NSF Broader Impacts dimensions.

**VERSION 3 — +Few-shot example (verbatim):**
> [Example of the quality bar and structure I want:]
> "Automating building energy modeling with large language models directly advances energy affordability and decarbonization for the communities least able to access modeling expertise. This project delivers that impact through three channels. First, the automated modeling toolkit and its evaluation benchmarks are released open-source, so small design firms, school districts, and municipal facilities teams — who cannot afford specialized energy modelers — can evaluate efficiency retrofits themselves. Second, in partnership with NREL, the project trains graduate and undergraduate researchers at the intersection of AI and building science, prioritizing recruitment of first-generation and underrepresented students into the growing clean-energy workforce. Third, the results seed an energy-literacy module reaching K-12 students across Arizona. Outcomes are tracked through tool adoption, benchmark citations, student placement, and pre/post learning assessments."
> You are an experienced NSF PI in building science. Following the structure and specificity of the example above, write a Broader Impacts paragraph for my proposal on using large language models for building energy modeling.

*V3 output (summary):* A paragraph mirroring the exemplar's "activity → target community → measurable outcome → dissemination" structure, with specific channels (open-source EnergyPlus-LLM tooling for under-resourced agencies, student training with a named recruitment pipeline, an energy-literacy outreach module) and tracked metrics.
*V3 quality: 4/5.* Improved vs. V2: adopted the exemplar's concrete structure and quality bar, eliminated generic outreach clichés, and attached measurable outcomes to each activity.

**VERSION 4 — +Chain-of-thought (verbatim):**
> [V3 prompt, plus:] Before writing, think step by step through: (1) Who is the audience? (2) What is the single most important point? (3) What tone is appropriate? Then produce the output.

*V4 output (summary):* The model first reasons explicitly — audience = mixed NSF panel including non-specialists; key point = democratizing energy modeling for under-resourced practitioners plus workforce training; tone = confident and concrete — then produces a tightened paragraph with a stronger lead sentence stating the central impact.
*V4 quality: 4.5/5.* Improved vs. V3: the explicit audience/point/tone reasoning sharpened the opening sentence and cut a redundant clause; the gain over V3 was modest, and there was mild risk of mechanically "checking boxes."

**150-word reflective note:** The largest single jump was V2 → V3 (few-shot). The role specification in V2 fixed *register* — active voice, NSF framing — but the output was still built from generic outreach clichés. Supplying one concrete exemplar in V3 transferred a specific structural template (activity → target community → measurable outcome → dissemination path) and my quality bar, which is what actually eliminated the filler. V4's chain-of-thought produced a visible and correct audience/purpose analysis and a sharper lead sentence, but only a marginal quality gain over V3 — consistent with the idea that beyond a point, added instructions polish rather than transform. The unresolved problem is factual: across all four versions the model invents plausible-but-unverified specifics (partner program names, participant counts, download metrics). That is an extrinsic hallucination risk (Ji et al., 2023) I must resolve manually by substituting real program data before submission.

---

## Task 3 — Hallucination Detection Audit

Method: claims extracted first, then verified against authoritative sources; hallucination type per Ji et al. (2023); severity per the module's Low/Med/High guidance.

### Text A — Olympic Games

| Claim | Accurate? | Verification source | Hallucination type | Severity |
|---|---|---|---|---|
| Modern Games revived in 1900 in Paris | **No** — revived 1896 in Athens | Olympics.com / Britannica | Temporal + factual | Medium |
| Coubertin, French educator, believed sport promotes peace | Yes | Britannica | — | — |
| First Games: 14 nations, ~250 athletes | Partly — ~14 nations/241 athletes describe **1896**, misattributed to 1900 | Olympics.com | Factual (misattribution) | Low |
| Women not permitted until 1920 Antwerp | **No** — women first competed in 1900 Paris | IOC / Britannica | Factual | Medium |
| Motto adopted at the inaugural modern Games | **No** — the motto became official in 1924 | Olympics.com | Factual | Low |

**Answer-key match:** a factual hallucination (medium) + a temporal hallucination (medium).

### Text B — Sleep

| Claim | Accurate? | Verification source | Hallucination type | Severity |
|---|---|---|---|---|
| Adults need 7–9 hours | Yes | CDC / Sleep Foundation | — | — |
| REM repairs muscle tissue and releases growth hormone; most physically restorative | **No** — muscle repair and growth-hormone release occur mainly in deep NREM (slow-wave) sleep, not REM | Sleep Foundation / NIH | Intrinsic | High |
| <6 h chronic deprivation linked to CVD, obesity, immune impairment | Yes | CDC | — | — |
| Average adult falls asleep in ~7 minutes | Imprecise — typical sleep latency is ~10–20 minutes | Sleep Foundation | Relational/statistical | Medium |

**Answer-key match:** an intrinsic hallucination (high) + a relational hallucination (medium).

### Text C — Amazon Rainforest

| Claim | Accurate? | Verification source | Hallucination type | Severity |
|---|---|---|---|---|
| ~5.5 million km², nine countries, largest tropical rainforest | Yes | WWF | — | — |
| ~400 billion trees, >16,000 species | Yes (≈390B trees, ~16k species) | Ter Steege et al., *Science* 2013 | — | — |
| 2019 WWF report: 30% deforested since monitoring "began in 1970" | **No** — cumulative deforestation is ~17–20%; the specific report/figure is unsupported; systematic satellite monitoring (INPE PRODES) began ~1988 | INPE PRODES / WWF | Extrinsic/statistical | High |
| River discharges ~20% of global freshwater to oceans | Yes (~18–20%) | USGS / Britannica | — | — |

**Answer-key match:** an extrinsic hallucination (high) + an extrinsic hallucination (low, the "1970" monitoring date).

### Text D — Marie Curie

| Claim | Accurate? | Verification source | Hallucination type | Severity |
|---|---|---|---|---|
| Polish-born; coined "radioactivity" | Yes (term credited to the Curies) | NobelPrize.org | — | — |
| First woman Nobel; **Chemistry 1903** for polonium/radium | **No** — her 1903 prize was in **Physics** (with Pierre Curie and Becquerel) for radioactivity | NobelPrize.org | Relational/causal (swapped discipline/year) | Medium |
| First person to win in two sciences; **second prize Physics 1911** | **No** — the 1911 prize was in **Chemistry** (for polonium/radium) | NobelPrize.org | Relational/factual | Medium |
| First woman professor at the **University of Warsaw** | **No** — first female professor at the **University of Paris (Sorbonne)** | NobelPrize.org / Britannica | Extrinsic/factual | Low |

**Answer-key match:** a relational/causal hallucination (medium) + an extrinsic hallucination (low).

### Text E — Internet and World Wide Web

| Claim | Accurate? | Verification source | Hallucination type | Severity |
|---|---|---|---|---|
| Internet and WWW are the same technology, invented together in the late 1980s by Berners-Lee at CERN | **No** — the Internet (ARPANET/TCP-IP, 1960s–70s) predates and differs from the Web; Berners-Lee invented the **Web** (1989–91), not the Internet | CERN / Britannica | Factual (conflation) | Medium |
| Designed to survive nuclear attack via multiple routing pathways | **No** — that narrative belongs to ARPANET/packet-switching, not the Web; and is itself a contested origin claim | Internet Society histories | Factual/relational | Medium |
| By 1995, ~50 million people using the web | Roughly high but arguable (~16–45M internet users in 1995) | Internet history sources | Extrinsic/statistical | Low |

**Answer-key match:** a factual hallucination (medium) + a factual hallucination (medium).

**Detection rate:** I identified every error flagged in the answer key (5/5 texts, all major errors), plus several minor low-severity ones — an effective detection rate of ~100% of key-flagged errors.

**Hardest type to detect (2–3 sentences):** The hardest was the intrinsic error in Text B — the REM/deep-sleep swap. It is fluent, contextually plausible, and correct-sounding to a non-specialist, so it can only be caught with specific domain knowledge of sleep physiology. This matches Ji et al.'s point that the dangerous hallucinations are the domain-specific ones that are "wrong in exactly the way that looks right."

---

## Task 4 — AI Tool Landscape Annotation

Selected for my role (LLM-driven building energy research: coding, proposals, literature synthesis, meetings). Access status verified against UArizona's Responsible AI / UITS offerings.

| Tool name | Modality | Access status | Best use case for my role | Key institutional concern |
|---|---|---|---|---|
| Claude (via U of A GenAI / AI Verde) | Text / multimodal | Institutionally available at no cost through the U of A GenAI platform (AWS Bedrock, privacy-aware) with NetID; also a personal free tier | Reasoning over building-simulation logic, drafting and reviewing proposal sections, analyzing uploaded documents | On the personal free tier, whether inputs are retained/used for training — route any non-public or research data through U of A GenAI/AI Verde, not the consumer app |
| GitHub Copilot | Code | Paid / institutional — confirm College of Engineering or departmental license via UITS before assuming access | Writing and completing Python for EnergyPlus workflows and data pipelines | Whether proprietary or unpublished codebase context is transmitted to and retained on external servers; may suggest code carrying license obligations |
| Google NotebookLM | Text (research assistant) | Free with NetID via Google Workspace for Education | Synthesizing and querying building-science papers, ASHRAE standards, and prior reports for literature reviews | Grounds answers only in documents I upload (lower hallucination risk), but uploaded content still leaves my machine — avoid unpublished sensitive or embargoed material |
| Whisper (OpenAI, open source) | Audio | Free / open-source; run locally on lab hardware | Transcribing research interviews, sponsor meetings, and lab recordings privately | Running locally keeps audio on-device (strong privacy); if a hosted API is used instead, participant audio and names leave the institution — confirm consent and data handling |

---

## Self-Assessment Rubric

| Criterion | Score (1–5) | Note |
|---|---|---|
| Compared two tools with a structured rubric | 5 | Both tools scored across five prompts; comparative synthesis written. |
| Applied zero-/few-shot/CoT to a real task | 5 | Four documented iterations on an NSF Broader Impacts paragraph. |
| Detected and classified hallucinations via Ji et al. | 5 | All five texts audited; ~100% of key-flagged errors caught. |
| Can explain RAG and diffusion grounding conceptually | 5 | Prior expertise; RAG mitigates but does not eliminate hallucination (Lewis et al., 2020). |
| Annotated a role-specific tool landscape | 5 | Four tools across text, code, and audio, with UArizona-verified access status. |

---

## Forum Participation

- [x] Post my V1 and V4 prompts (task hidden) and ask peers what task it was and what the change reveals the model needed
- [ ] Respond to a peer's prompt pair (answer their two questions + run their V1 in my tool and compare) *(to complete on the forum)*

*Discussion note (Ji et al. greatest-risk type for my context):* extrinsic factual hallucination — fabricated citations, statistics, or agency details in proposals — which I will guard against by verifying every concrete claim against a primary source before submission.
