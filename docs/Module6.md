# Module 6: Becoming an AI Campus Champion — Self-Paced Tasks

**Name:** Liang Zhang
**Date:** 6/26/2026
**Role:** Assistant Professor, Civil & Architectural Engineering and Mechanics (CAEM), University of Arizona (Director, TensorBuild Lab; joint appointee, NREL)
**Module:** 6 — Becoming an AI Campus Champion: Design, Leadership, and Action

---

## Reading 1 — Cultivating Communities of Practice (Wenger, McDermott & Snyder, 2002)

| Term | Definition |
|---|---|
| Community of practice | A group bound by a shared domain who build knowledge together through sustained relationships and a shared practice — more than a team (task) or a network (relationships). |
| Domain (CoP) | The shared area of concern or inquiry that gives the community its identity and focus. |
| Community (CoP) | The web of relationships and mutual engagement that lets members learn from and with each other. |
| Practice (CoP) | The shared repertoire of tools, methods, cases, and stories the community develops and reuses. |
| Knowledge stewardship | The active curation, documentation, and sharing of the community's accumulated knowledge so it persists and circulates. |
| Legitimate peripheral participation | The way newcomers learn by starting at the edge with low-stakes contributions and moving inward as they gain competence and confidence. |

**Q1 — Three elements; does the Champions cohort qualify?** The three elements are domain (a shared concern — responsible AI in higher ed), community (relationships that support learning), and practice (a shared repertoire of tools/cases). The cohort clearly has the **domain** and, through six weeks of forum exchange, a real **community**. It is thinnest on **practice**: we have shared readings and templates but not yet a durable, jointly maintained repertoire that outlives the workshop. So it is a strong emergent CoP that falls short precisely on the practice element — which is exactly what a post-workshop network must cultivate.

**Q2 — Accommodating core/active/peripheral members:** An initiative should make **peripheral** participation legitimate and easy — observing, reading a shared resource, attending one session — rather than treating anything short of leadership as non-participation. Concretely: a low-barrier shared channel and resource library for peripheral members, a regular meeting rhythm for active members, and a small stewardship role for core members. The design goal is a wide, welcoming edge that lets people contribute at the intensity they can sustain, with a clear path inward.

**Q3 — Cultivation, not mandate; language for leadership:** Because CoPs cannot be commanded into existence, I would propose to leadership in the language of *enabling conditions*, not compliance: "create time, recognition, and a shared space for interested faculty and staff to build AI practice," rather than "require all units to adopt AI training." Words like *pilot, invite, cultivate, support, and community* create room for organic participation; words like *mandate, rollout, and compliance* trigger the resistance that kills voluntary communities.

**Q4 — Knowledge-management structures a Champions CoP needs:** A shared, searchable resource library (templates, worked cases, tool/data guidance); a predictable meeting rhythm (e.g., a monthly "what worked / what broke" exchange); documentation practices that capture reusable artifacts (workflow canvases, unit guidelines, prompt patterns) rather than one-off chat; and a named steward or two who keep the library current. Without stewardship, the knowledge stays tacit and leaves when individuals do.

---

## Reading 2 — A Revision of Bloom's Taxonomy (Krathwohl, 2002)

| Term | Definition |
|---|---|
| Cognitive process dimension | The six-level scale of what learners *do* with knowledge: Remember, Understand, Apply, Analyze, Evaluate, Create. |
| Knowledge dimension | The four *types* of knowledge — Factual, Conceptual, Procedural, Metacognitive. |
| Learning objective verb | The action verb that names the targeted cognitive process and makes an objective observable/measurable. |
| Metacognitive knowledge | Knowledge of one's own thinking and learning — awareness of strategies, strengths, and gaps in relation to a subject. |
| Bloom's Revised Taxonomy | Anderson & Krathwohl's 2001 update recasting Bloom's noun categories as verbs and adding the metacognitive knowledge type, arranged as a two-dimensional table. |
| Measurable learning objective | An objective stated with an observable verb and clear conditions, so attainment can actually be assessed. |

**Q1 — Mapping the six modules to Bloom's levels:** Module 1 = **Remember/Understand** ("define" AI/ML/LLM); Module 2 = **Apply** ("apply" zero-/few-shot/CoT to a task); Module 3 = **Apply/Analyze** ("audit" my workflow); Module 4 = **Analyze** ("classify" bias types, "detect" hallucinations); Module 5 = **Evaluate** ("evaluate" policies, "argue" a position); Module 6 = **Create** ("design" an original initiative). The verbs in each module's objectives track the taxonomy's recommended verbs at each level.

**Q2 — Why verbs beat nouns for objectives:** A noun ("Comprehension") names a mental state you cannot directly observe; a verb ("summarize," "classify," "design") names an action you can see and assess. Verb objectives specify what the learner will *do* to demonstrate learning, which makes the objective measurable and the assessment obvious — you can check whether they summarized, not whether they "comprehend."

**Q3 — Metacognitive knowledge + an example in my domain:** Metacognitive knowledge is awareness of one's own cognition — knowing one's strategies, limits, and when to switch approaches. In my domain: a graduate researcher recognizing *when* an LLM is inside vs. outside its reliable frontier for a building-energy modeling task, and adjusting how much to trust and verify accordingly. That self-regulatory judgment — not the modeling skill itself — is metacognitive.

**Q4 — Where I'd start an AI-literacy experience for colleagues, and why:** I would start at **Understand/Apply**, not Remember — a short accurate mental model of what an LLM is, immediately followed by hands-on application to a real task. The workshop's own design is my evidence: Module 1 spent minimal time on rote definitions and quickly moved to applied exploration, because adults engage when abstract concepts attach to a concrete task they care about. For busy faculty, leading with a relevant "Apply" activity earns the attention that pure "Remember" content loses.

---

## Task 1 — AI Adoption Initiative Design Canvas

**Initiative title:** *Verify-First — an AI research-productivity clinic for graduate researchers in CAEM*

**SECTION 1 — Problem Statement (49 words):** Graduate researchers in CAEM already use general-purpose AI for literature, code, and writing, but with no shared norms they risk unverified hallucinated claims in manuscripts, put unpublished or sponsor data into consumer tools, and overlook privacy-safe institutional options — and no unit guidance addresses *research* (not coursework) use.

**SECTION 2 — Target Audience:** MS/PhD researchers in CAEM (and, secondarily, their advisors). **AI fluency: 2–3** — most use ChatGPT ad hoc without verification discipline or data-sensitivity awareness. **What they need:** a concrete, safe workflow for literature, coding, and drafting that saves real time without risking integrity or data. **Key concern:** "Will using AI look like cheating or hurt my scholarly credibility — and is my data safe?"

**SECTION 3 — AI Tools and Approach:**

| Tool | Modality | Rationale | Data sensitivity | Approved? |
|---|---|---|---|---|
| Claude via U of A GenAI / AI Verde | Text/multimodal | Reasoning, drafting, summarizing; privacy-aware institutional hosting | Cleared for internal/research (non-public) | Y |
| Google NotebookLM (NetID) | Text (research) | Grounded literature synthesis from uploaded papers | Low (public papers) | Y |
| GitHub Copilot | Code | Python/EnergyPlus workflows and refactoring | Non-proprietary code only | Pending (verify dept license) |
| Whisper (local) | Audio | Private transcription of meetings/interviews | Local, on-device | Y |

**SECTION 4 — Ethical Safeguards:**

| Risk | Safeguard mechanism | Responsible party |
|---|---|---|
| Hallucinated facts/citations in manuscripts | Mandatory human-verification step (Module 3 Box 6): every claim/citation checked against a primary source | Each researcher + advisor sign-off |
| Sensitive-data leakage (unpublished proposals, sponsor/occupant, student data) | Data-classification rule: non-public data only through U of A GenAI/AI Verde; never consumer tools | PI / lab director (guideline owner) |
| Representation bias in AI-generated "field leaders"/exemplars/citations | Cross-check AI lists against diverse sources (Module 4 finding) | Clinic facilitator (me) |
| Over-reliance / deskilling of junior researchers | Centaur framing — AI drafts, human owns judgment; teach *when not* to use AI | Advisors |

**SECTION 5 — Equity Considerations:**
- **Population 1 — International/ESL graduate students:** may over-rely on AI for English and be judged by it, or fear disclosure stigma. **Adjustment:** frame AI as legitimate language support, adopt disclosure norms that don't penalize ESL writers, and teach verification so their reliance is safe rather than risky.
- **Population 2 — Students without paid-tool access or personal devices:** the clinic must not assume a paid ChatGPT subscription or a personal laptop. **Adjustment:** route everything through free institutional tools (U of A GenAI, NetID NotebookLM) and hold sessions in a department computer lab, so no purchase or device is required. *(Also: extend equal invitation to part-time/contingent researchers.)*

**SECTION 6 — Success Metrics:**

| Metric | How measured | Timeline | Minimum threshold |
|---|---|---|---|
| Verification behavior | Pre/post self-report + a worked exercise (spot the hallucinated claim) | Pre (S1) / post (S3) / 30-day follow-up | ≥70% demonstrate verification on the post exercise |
| Data-safe tool use | Pre/post survey of which tools they use for sensitive data | Pre / post | ≥80% report routing sensitive data only through approved tools |
| Real-world adoption | 30-day follow-up: did they apply the workflow to actual work? | Day 30 after S3 | ≥60% report using it on a real task |

**SECTION 7 — Rollout: First Three Steps:**

| Step | What | Who | Resource needed | By when |
|---|---|---|---|---|
| 1 | Draft the 3-session clinic outline; adapt my Module 3 workflow canvas + Module 5 lab guideline into participant handouts | Me (independent) | Existing artifacts only | Within 7 days |
| 2 | Recruit 5–8 pilot participants from my lab + one collaborating lab; confirm room and time | Me + named collaborator (co-advising CAEM faculty / grad coordinator) | Email + a lab-meeting slot | Day 21 |
| 3 | Run Session 1 (safe workflow + data classification); collect pre-survey | Me | U of A GenAI access; department computer lab | Day 45 |

**30-second elevator pitch (48 words):** Our grad students already use AI for research — but without shared rules they risk hallucinated citations and leaked unpublished data. I'm piloting a three-session, verify-first clinic that teaches CAEM researchers a safe, privacy-aware AI workflow using our own institutional tools. Small, measurable, and built to scale.

---

## Task 2 — Stakeholder Communication (Email to a Skeptical Colleague)

**Format:** Email · **Recipient:** A senior CAEM faculty colleague who advises graduate students and is skeptical that AI belongs in research training.

**Hook (problem, no AI):** You've likely seen a draft from a student lately with a confident claim or citation that turned out to be wrong — and had to wonder how carefully it was checked.

**Initiative description:** A short, three-session clinic that teaches our graduate researchers a disciplined workflow for using AI on literature, code, and writing — with verification and data protection built in — using the University's own privacy-safe tools.

**Anticipated objection + response:** *Objection:* "This will make students lean on AI and stop thinking." *Response:* That's exactly the failure mode the clinic targets; the whole method keeps the student as the accountable author and treats AI as a drafting tool that must be verified, so it builds judgment rather than replacing it.

**Call to action:** Could you spare 15 minutes to look at my one-page outline and tell me where you'd push back?

**Full draft (222 words):**

Subject: A 15-minute ask — keeping AI use in our students' research honest

Dear [Colleague],

You've probably seen a student draft recently with a confident claim or a citation that didn't hold up on a closer look — and found yourself wondering how carefully it had been checked. I've been running into the same thing, and I don't think the answer is to pretend our students aren't already using AI. They are; they're just doing it without any shared rules.

I'm piloting a short, three-session clinic for our graduate researchers that teaches a disciplined way to use AI for literature, code, and writing — with fact-verification and data protection built into the workflow, using the University's own privacy-safe tools rather than consumer apps.

I expect your first reaction may be that this will make students lean on AI and stop thinking. That's precisely the failure mode I'm designing against: the method keeps the student as the accountable author, treats AI only as a draft to be checked against sources, and explicitly teaches when *not* to use it. The goal is stronger judgment, not outsourced thinking.

I'm not asking you to endorse anything yet. Could you spare 15 minutes to read a one-page outline and tell me where you'd push back? Your skepticism is exactly the pressure-test it needs.

Thanks,
Liang

---

## Task 3 — Initiative Review (Four-Dimension Rubric)

*Peer exchange is pending a partner's canvas on the forum; below is my self-review using the same rubric, as the module's Best Practices recommend doing first.*

**Initiative reviewed:** Verify-First AI research-productivity clinic (my own)

| Dimension | Score (1–5) | Evidence from the canvas | Concrete suggestion |
|---|---|---|---|
| 1 Problem clarity | 4 | Section 1 names a specific population (CAEM grad researchers), a specific gap (no research-use norms; unverified claims; data leakage), and scale (unit). | Add one concrete incident (e.g., a real hallucinated-citation near-miss) so the problem is recognizable, not abstract. |
| 2 Evidence–design alignment | 5 | Safeguards cite Module 3 (verification step), Module 4 (representation-bias cross-check), and Module 5 (data classification); tools carry sensitivity + approval status. | Make the Bloom's progression explicit in the session design so the *pedagogy* is as evidence-grounded as the safeguards. |
| 3 Equity treatment | 4 | Section 5 names two populations (ESL students; students without paid tools/devices) with a concrete adjustment each, plus contingent researchers. | Add a measure that tracks whether ESL and no-device participants benefit *equally* (disaggregate the success metrics), not just that they can attend. |
| 4 Feasibility | 4 | Step 1 is executable this week with existing artifacts and no permission; Steps 2–3 have owners, resources, and dates. | Copilot approval is "pending" — add a fallback (skip paid Copilot; use free U of A GenAI for the code session) so Step 3 isn't blocked by a dependency. |

**Open question (genuine):** The clinic depends on advisors reinforcing the verification norm afterward — but advisors aren't the direct participants. What is the mechanism that keeps a busy advisor bought in once the three sessions are over, so the practice doesn't decay the moment the clinic ends?

---

## Task 4 — 90-Day Action Plan + Concept Map Revision

### Part A — 90-Day AI Campus Champion Action Plan

**Days 1–30 (independent, this week, existing resources):**
- Action 1: Draft the three-session clinic outline and convert my Module 3 workflow canvas + Module 5 lab guideline into two participant handouts.
- Action 2: Identify and list 6–8 candidate participants from my lab and one collaborating CAEM lab.
- Collaborator: *the CAEM Graduate Program Coordinator* (Megan Letchworth) — the person who knows which students to reach.
- Resource needed: my existing Module 3–5 artifacts; U of A GenAI access.
- Barrier + response: *Barrier:* I over-scope it into an all-department program. *Response:* cap the pilot at ≤8 participants and one collaborating lab.

**Days 31–60 (collaborative):**
- Action 1: Meet the named co-advising faculty colleague to co-sponsor the pilot and pressure-test the outline (this is my Task 2 email in action).
- Action 2: Confirm a room/time, send invitations, and run Session 1 with a pre-survey.
- Collaborator: *a senior CAEM faculty colleague* (Dominic Boccelli) as co-sponsor.
- Resource needed: a department computer lab slot; the pre/post survey.
- Barrier + response: *Barrier:* low sign-up from busy students. *Response:* frame it around a concrete pain (proposal/lit-review time), offer it during an existing lab-meeting slot rather than adding a new obligation.

**Days 61–90 (building on 1–60):**
- Action 1: Run Sessions 2–3 (bias/verification; data-safe tools + code), collect the post-survey.
- Action 2: Write a 2-page "what worked / what broke" brief and share it with the AI Champions network as a reusable template.
- Collaborator: the AI Champions cohort (as a community of practice for stewarding the materials).
- Resource needed: 30-day follow-up survey; a shared repository slot.
- Barrier + response: *Barrier:* the practice decays after the clinic. *Response:* give each advisor a one-page verification checklist so the norm lives in the lab, not just the clinic.

**By Day 90 I will have:** piloted and documented a three-session, verify-first AI research clinic for a cohort of ≤8 CAEM graduate researchers, with pre/post evidence of improved verification behavior and data-safe tool use, and a reusable brief shared with the Champions network.

### Part B — Concept Map Revision (Week 1 → Week 6)

**New nodes added (7, from Modules 2–6):** Hallucination (M2/M4), Jagged frontier (M3), Bias encoding (M4), "Stochastic parrot" (M4), NIST AI RMF (M5), Human verification (M3), Community of practice (M6).

**Existing connections annotated with evidence (3):**
- AI ⊃ ML ⊃ Deep learning — "strict subsets."
- Foundation model → LLM — "all frontier LLMs are foundation models [Bommasani et al., 2021, p.3]."
- Foundation model ↔ Generative AI — "overlap: output type vs. training paradigm."

**New technical → ethical/governance connections (drawn as dashed red links — the integrative moves):**
- Foundation model → Bias encoding — "web-scale training data encodes societal bias [Bender et al., 2021; Caliskan et al., 2017]."
- LLM → Hallucination → Human verification — "next-token prediction has no truth-check [Ji et al., 2023], so a human-verification control is required [Module 3]."
- LLM → Jagged frontier — "capability boundary is jagged and unintuitive [Dell'Acqua et al., 2023]."
- LLM → "Stochastic parrot" — "form-without-meaning critique [Bender et al., 2021]," complicated by emergent abilities [Wei et al., 2022].
- Bias encoding → NIST AI RMF → Community of practice — "governance response [NIST, 2023] stewarded through an AI-Champions community of practice [Wenger et al., 2002]."

![Concept Map - Week 6](https://github.com/lz356/AICampusChampions/blob/main/images/ConceptMap_Week6_LiangZhang_1.png)

---

## Self-Assessment Rubric

| Criterion (Learning Objective) | Score (1–5) | Note |
|---|---|---|
| Designed an original, evidence-grounded initiative on the seven-section canvas | 5 | Verify-First clinic reuses Module 3 & 5 artifacts; safeguards cite Modules 3–5. |
| Produced a professional stakeholder communication for a skeptical colleague | 5 | 222-word email leads with the problem, answers the main objection, asks a 15-minute step. |
| Provided structured, evidence-grounded review on the four-dimension rubric | 4 | Completed as a rigorous self-review; peer exchange pending on the forum. |
| Formulated a specific 90-day plan with collaborators, milestones, barriers | 5 | Three horizons, named collaborator roles, one barrier/response each, a concrete Day-90 outcome. |
| Revised the Week 1 concept map to document learning trajectory | 5 | Seven new nodes, three annotated connections, five technical→ethical links. |

---

## Peer Participation

- [x] Post both concept maps (Week 1 and Week 6) with a 3-sentence caption — (1) *most significant new connection:* LLM → Hallucination → Human verification, because it reframed a technical property (next-token prediction) as the reason a governance control is non-negotiable; (2) *connection that best represents my learning:* Bias encoding → NIST AI RMF → Community of practice, linking a technical failure to a governance response stewarded by people; (3) *node I could not yet add confidently:* a rigorous "emergent abilities" node — I can gesture at it, but I don't yet understand the scale-threshold evidence well enough to connect it precisely without overclaiming.
- [ ] Respond to a peer's Week 1↔Week 6 maps (most striking growth / one connection I'd draw differently / one question about where they go next) *(to complete on the forum once a peer has posted).*
