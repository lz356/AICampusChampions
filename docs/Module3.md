# Module 3: AI for Productivity — Self-Paced Tasks

**Name:** Liang Zhang
**Date:** 6/26/2026
**Role:** Assistant Professor, Civil & Architectural Engineering and Mechanics, University of Arizona (Director, TensorBuild Lab; joint appointee, NREL)
**Module:** 3 — AI for Productivity: Practical Integration in Academic Work

---

## Reading 1 — Experimental Evidence on the Productivity Effects of Generative AI (Noy & Zhang, 2023)

| Term | Definition |
|---|---|
| Randomized controlled trial (RCT) | An experiment that randomly assigns participants to treatment (AI access) or control, so outcome differences can be attributed to the treatment rather than pre-existing differences. |
| Treatment effect | The causal difference in an outcome (time, quality) between the AI-access group and the control group. |
| Skill compression | AI narrowing the gap between lower- and higher-skilled workers by raising the low end most, reducing outcome inequality and variance. |
| Task completion time | Time taken to finish an assigned task — the study's primary productivity measure (~37% reduction with AI). |
| Output quality assessment | Independent evaluators grading outputs (here on a 1–7 scale), blind to whether AI was used. |

**Q1 — Task types; representative of my most demanding work?** The study used mid-level professional writing tasks — press releases, short reports, analysis plans, and delicate emails — for occupations like marketing, grant writing, data analysis, and HR. These map well to my *routine* writing (proposal boilerplate, administrative email, summaries) but not to my most cognitively demanding work: novel physics-informed model formulation, LLM-agent design, and research interpretation, none of which resemble a 20-minute self-contained writing task.

**Q2 — Skill-compression implications for higher-ed staff:** Because AI lifted lower-skilled workers most and shrank variance, broad deployment to university staff could raise baseline output quality and reduce disparities within a unit — but it also compresses the skill signal that distinguishes strong performers, so evaluation and professional development should shift toward the judgment-heavy work AI doesn't cover. It also argues for *equitable* access (a stated UArizona ORAI priority), since uneven access would otherwise reverse the leveling effect.

**Q3 — Quality metric; applicable to my documents?** Quality was a 1–7 holistic grade assigned by experienced professionals in the same occupations, blind to condition. It applies reasonably to my newsletter blurbs, emails, and lay summaries, but not to the artifacts that define my work: a building-energy model's correctness or a proposal's technical merit require domain verification and panel judgment, not a holistic writing score.

**Q4 — A methodological limitation affecting transfer to my context:** The tasks were short, self-contained, and lacked domain-specific ground truth, and participants were not writing at the frontier of a technical field. My work is multi-week, technically constrained, and evaluated against correctness (code that must run) and expert panels — so the 37% figure should be read as an upper-bound signal for routine writing, not a prediction for my core research tasks.

---

## Reading 2 — Navigating the Jagged Technological Frontier (Dell'Acqua et al., 2023)

| Term | Definition |
|---|---|
| Jagged technological frontier | The irregular, non-obvious boundary between tasks AI does well (inside) and poorly (outside); capability varies task-to-task in ways that don't track human intuitions of difficulty. |
| Centaur collaboration | A deliberate division of labor — the human does some subtasks, AI does others, with a clear handoff line. |
| Cyborg collaboration | Deep, continuous integration where human and AI intertwine within subtasks in a tight prompt-edit-reprompt loop. |
| Over-reliance | Uncritically accepting AI output — especially outside the frontier — leading to worse performance than not using AI. |
| Inside-frontier task | A task within AI's reliable capability, where assistance raises speed and quality. |
| Outside-frontier task | A task beyond AI's reliable capability, where assistance can mislead and degrade performance. |

**Q1 — What the jagged frontier is, and why "jagged":** It is the boundary of AI's reliable capability. It is jagged rather than smooth because AI competence does not align with human notions of difficulty — two tasks that look equally hard to a person can fall on opposite sides, so you cannot predict success from apparent difficulty.

**Q2 — How inside/outside was identified; implication for non-experimenters:** The team pre-classified tasks (via piloting and design), with the outside-frontier task engineered so AI would produce confident but wrong answers from a subtle data/interview mismatch. Since practitioners cannot run experiments to map their own frontier, the practical implication is to treat the boundary as unknown, probe it case-by-case, and verify outputs rather than assume competence.

**Q3 — Centaur vs. cyborg; which fits my Task 2:** Centaur = split by strength (human keeps judgment-heavy parts, AI takes drafting and structure); cyborg = interleaved, AI woven throughout. For my Task 2 research summary, the centaur style is more appropriate: AI drafts structure and phrasing while I own every technical claim and the final voice.

**Q4 — Mechanism for degraded performance; convincing?** The authors propose over-reliance — "falling asleep at the wheel": fluent, authoritative output lowers the human's guard, so on outside-frontier tasks people anchor on and adopt confident errors. I find it convincing and consistent with Ji et al. (2023): the very fluency that helps inside the frontier is what disarms scrutiny outside it.

---

## Task 1 — Professional Task Workflow Audit Matrix

Data sensitivity: 1 = no confidential data; 3 = aggregated/de-identified; 5 = PII/FERPA/proprietary.

| Task name | Frequency | Time/instance | Cognitive demand (1–5) | AI integration potential (1–5) | Data sensitivity (1–5) | Top candidate? |
|---|---|---|---|---|---|---|
| Screening funding-opportunity announcements for lab fit | Weekly | 30–45 min | 2 | 5 | 1 | **Y** |
| Drafting proposal boilerplate sections (summary, facilities, data-management plan) | Monthly (proposal season) | 2–3 h | 3 | 4 | 2 | **Y** |
| Replying to routine administrative email | Daily | 5–15 min | 2 | 4 | 2 | N |
| Debugging Python for EnergyPlus / simulation workflows | Weekly | 1–2 h | 3 | 4 | 2 | N |
| Peer-reviewing journal manuscripts | Monthly | 3–4 h | 5 | 2 | 5 | N |

**Top candidate 1 — Funding-opportunity screening (potential 5, sensitivity 1):** Parsing public solicitation text and matching it to my lab's scope is information assembly — squarely inside the jagged frontier (Dell'Acqua et al., 2023), where AI reliably raises speed and quality. It is an ideal *practice* candidate because the source is public (sensitivity 1) and any misjudgment is caught when I read the actual solicitation, keeping over-reliance risk low; a clean centaur split has AI summarize while I make the go/no-go call.

**Top candidate 2 — Proposal boilerplate drafting (potential 4, sensitivity 2):** Standard sections (facilities, data-management, project summary structure) are inside-frontier, but the technical and strategic claims sit outside it, so I keep those human — a deliberate centaur division rather than a cyborg loop. Because the content is unpublished (sensitivity 2), I route it through U of A GenAI / AI Verde rather than a consumer tool, consistent with NSF's confidentiality guidance and UArizona's data-classification standard.

*Note on the excluded task:* peer review scores highest on cognitive demand (5) and data sensitivity (5) and is therefore removed from AI-integration consideration — uploading a confidential manuscript to a public tool would violate both journal confidentiality norms (ICMJE) and the trust of the review process.

---

## Task 2 — AI-Assisted Task Completion with Full Documentation

| Field | Entry |
|---|---|
| Task description | Draft a ~200-word plain-language summary of my research on LLM-driven automated building energy modeling, for the College of Engineering research newsletter (general academic audience). |
| Tool(s) used; sensitivity | Claude via U of A GenAI (institutionally available). Data sensitivity: **Low** (describes my own published research direction; no confidential or personal data). |
| Normal time (from memory) | ~40 minutes |
| Actual time this session | ~15 minutes |

**Prompt sequence:**

| # | Prompt (summarized) | Output (summarized) | Edit made — what & why |
|---|---|---|---|
| P1 | Role (science writer for a general university audience) + zero-shot request for a ~200-word plain-language summary of LLM agents that automatically build/calibrate physics-based building energy models. | Clear, readable draft, but over-claimed that the tools "eliminate the need for engineers." | Cut the over-claim; changed to "reduces the manual modeling effort." Why: accuracy — the method augments, it doesn't replace expert judgment (and over-claiming would fail a technical reader). |
| P2 | Rewrite to lead with real-world stakes (building energy use and emissions), keep one concrete example, target a ~12th-grade reading level, ~180 words. | Better framing and flow; **inserted a statistic** that "buildings use 60% of energy." | Replaced with the verified figure — U.S. buildings account for roughly **40% of energy use** and a comparable share of emissions. Why: the 60% figure was an extrinsic hallucination (fabricated specific), the exact failure mode from Module 2's Ji et al. audit. |
| P3 | Chain-of-thought polish: check audience (general academic), single most important point (democratizing energy modeling), tone (concrete, non-hype); then finalize. | Tightened final version with a stronger opening and less hedging. | Minor: removed one hedge; corrected lab attribution. Why: voice and accuracy of attribution. |

**Output quality vs. typical unassisted:** 4/5 — reached comparable quality faster, but only after the human verification step; the raw output would have shipped a false statistic.

**Disclosure Decision:** For a low-stakes newsletter blurb describing my own research, I would tell the newsletter editor it was AI-assisted if the outlet asks, and I take full responsibility for accuracy. This aligns with the University of Arizona Office of Responsible AI (ORAI) guidance, which places responsibility for accuracy and interpretation on the human user; no student or confidential data was involved, and the tool (Claude via U of A GenAI) is institutionally available. **Both the raw AI output and my edited final version are saved as separate files** per the module instruction.

**Key finding:** the model drafted fluent structure inside the frontier but fabricated a specific statistic at the edge of it — a live demonstration of the jagged frontier and of why the human-verification step is non-negotiable.

---

## Task 3 — Academic Integrity Scenario Analysis

| Scenario | Appropriate? | Disclose? | To whom | Policy cited | 1-sentence reasoning |
|---|---|---|---|---|---|
| 1. Faculty uses an LLM to draft individualized written feedback on student lab reports, lightly edits, returns it in their own voice, no disclosure | Depends | Yes | Students; confirm data handling with dept/IT | FERPA; UArizona data-classification standard (ISO-400-S1); ORAI guidance | Acceptable only if student work is not exposed to a non-approved tool and students know their personalized feedback was AI-assisted, since authenticity matters to them. |
| 2. PI uses AI to draft substantial portions of an NSF proposal narrative, does not mention it | Depends | Yes | NSF (indicate in project description) | NSF Notice on Generative AI in the Merit Review Process (Dec 2023) | NSF permits AI-assisted drafting but expects disclosure of the extent of use and holds the PI responsible for the accuracy and authenticity of the submission. |
| 3. Grad student uses AI to help write and debug the Python analysis code for a paper; not mentioned in methods | Yes | Depends | Co-authors; journal per its policy | ICMJE / publisher AI-disclosure guidance | Using AI as a coding tool is standard and acceptable; noting AI-assisted code aids reproducibility but is a transparency courtesy, provided the student validates the code. |
| 4. Staff member pastes a spreadsheet of student names and grades into public ChatGPT (free tier) to generate summary statistics | No | N/A (should not occur) | — | FERPA; UArizona ISO-400-S1; ORAI | Entering identifiable student records into a public tool violates FERPA and institutional data classification regardless of intent — de-identify and use an approved tool or local computation. |

**Where policy is silent (a finding for AI Champions):** UArizona guidance is clear on *data handling* but comparatively silent on whether AI-assisted **student feedback** (Scenario 1) must be disclosed to students. To make that scenario navigable, a policy would need to state a disclosure threshold for AI assistance in individualized communications that affect a student.

*(Note: these four scenarios are representative — the module's specific scenario set lives on the course platform, which wasn't part of the wiki; the reasoning framework and policy citations apply directly to the platform set.)*

---

## Task 4 — Personal AI Workflow Sketch

![Personal AI workflow diagram for the research-summary task](AIWorkflow_Module3_LiangZhang.png)

| Box | Contents |
|---|---|
| 1 — Task entry point | Trigger: a request for a research-newsletter blurb. Desired output: a ~200-word plain-language summary of my LLM-driven building-energy-modeling research. |
| 2 — Data inputs | My own research description and published results. Sensitivity: **Low** — no personal, student, or unpublished-proprietary data. |
| 3 — AI tool + rationale | Claude via U of A GenAI. Chosen for strong drafting/summarization at frontier scale; institutionally available and privacy-aware, so appropriate even if I later reuse the workflow on Medium-sensitivity content. |
| 4 — Prompt strategy | Role specification (science writer) + one few-shot style cue + chain-of-thought finalize step (audience / key point / tone). |
| 5 — AI output review checkpoint | Check tone (non-hype), length (~200 words), framing (stakes-first), and completeness; flag any over-claiming. |
| 6 — Human verification (REQUIRED) | Verify **every** factual/technical claim against a source — here, catching and correcting a fabricated energy statistic. This step is non-negotiable regardless of how polished the draft looks. |
| 7 — Output + disclosure | Final blurb sent to the newsletter editor; AI-assisted drafting noted per UArizona ORAI guidance; I retain responsibility for accuracy. |

**Non-negotiable human step:** Box 6 — independent verification of factual claims against primary sources, not a re-read for fluency.

**Centaur vs. cyborg:** This workflow is **centaur** — a clean division where AI owns the inside-frontier drafting and structuring and I own the outside-frontier work (technical accuracy, final judgment, and voice). That division is exactly what protects against the over-reliance failure Dell'Acqua et al. (2023) documented.

---

## Self-Assessment Rubric

| Criterion | Score (1–5) | Note |
|---|---|---|
| Audited five recurring tasks on the multi-dimensional matrix | 5 | Five tasks scored; top two selected with jagged-frontier/centaur reasoning. |
| Completed a real task with full prompt/output/edit/time documentation | 5 | Research-summary drafted; three prompts logged, key hallucination caught and corrected. |
| Applied a disclosure framework to integrity scenarios with named policy | 5 | Four scenarios analyzed against NSF, FERPA, ICMJE, and UArizona ORAI policy. |
| Designed a personal AI workflow with a required verification checkpoint | 5 | Seven-box canvas + diagram; Box 6 verification step made explicit. |
| Interpreted Noy & Zhang and Dell'Acqua findings in my own context | 5 | Both papers connected to my routine vs. frontier tasks and to the centaur workflow. |

---

## Peer Participation

- [x] Post one concrete Task 2 finding: AI drafted a fluent summary but fabricated a "60% of energy" statistic (real figure ~40%), which I caught and corrected — a clean illustration of the jagged frontier (fluent drafting inside it, factual specifics outside).
- [x] Respond to a peer's finding, connecting it to Noy & Zhang (2023) or Dell'Acqua et al. (2023) *(to complete on the forum, once a peer has posted).*

