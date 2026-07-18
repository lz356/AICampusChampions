# Module 5: AI Governance — Self-Paced Tasks

**Name:** Liang Zhang
**Date:** 6/26/2026
**Role:** Assistant Professor, Civil & Architectural Engineering and Mechanics, University of Arizona (Director, TensorBuild Lab; joint appointee, NREL)
**Module:** 5 — AI Governance, Policy, and Responsible Use at the University

---

## Reading 1 — NIST AI Risk Management Framework (AI RMF 1.0) Core (2023)

| Term | Definition |
|---|---|
| AI RMF Core functions (GOVERN, MAP, MEASURE, MANAGE) | The four organizing functions: GOVERN sets org-wide policy, accountability, and culture; MAP establishes context and identifies/categorizes risks; MEASURE assesses and tracks risks with metrics; MANAGE prioritizes, acts on, and responds to risks. |
| AI trustworthiness properties | The characteristics that make a system trustworthy: valid and reliable, safe, secure and resilient, accountable and transparent, explainable and interpretable, privacy-enhanced, and fair with harmful bias managed. |
| AI actor | Any party playing a role across the AI lifecycle — designers, developers, deployers, operators, users, and affected parties. |
| Risk management | The coordinated process of identifying, assessing, prioritizing, and mitigating potential harms from AI across its lifecycle. |
| Principles-based governance | Governance that sets high-level goals and values and leaves the specific means to implementers, rather than prescribing detailed rules. |

**Q1 — What each function covers; the failure mode of GOVERN-only:** GOVERN is the organizational foundation (policy, accountability, roles, culture); MAP frames context and identifies/categorizes the risks of a specific system; MEASURE assesses and tracks those risks; MANAGE acts on the prioritized risks and handles response/recovery. An organization that has only implemented GOVERN — a written policy with no MAP or MEASURE — has aspiration without operation: it cannot say which deployed systems carry which risks, or whether any control actually works, so the policy is a document rather than a practice and reduces no real harm.

**Q2 — Three properties most relevant to student-facing services:** (1) *Privacy-enhanced* — student records are FERPA-protected, so data handling is the threshold concern; (2) *Fair, with harmful bias managed* — a student-facing tool that treats subgroups unequally causes direct, consequential harm (Module 4); (3) *Accountable and transparent* — students should know when AI shapes something affecting them and have a path to contest it. Validity/reliability matters too, but these three govern trust in the student relationship.

**Q3 — What makes a "voluntary" framework de facto mandatory:** Federal grant and contract terms increasingly reference NIST, so compliance becomes a condition of funding for an R1; accreditation bodies are folding AI-risk expectations into standards; and litigation/liability plus cyber-insurance underwriting make a NIST-aligned program a due-diligence defense. For a research university, grant compliance and liability exposure are the strongest levers turning "voluntary" into "expected."

**Q4 — NIST's "AI risk" vs. my institution's framing:** NIST defines AI risk as the composite likelihood × magnitude of harm to people, organizations, and ecosystems across the lifecycle, explicitly including affected third parties. UArizona currently has no single university-wide AI policy; its guidance frames AI risk mainly as *academic integrity* plus *data privacy/IP* (instructor approval required; don't submit confidential data). That covers integrity and data protection well but underplays NIST's broader categories — bias/fairness harms to affected parties, explainability, and environmental or third-party impacts.

---

## Reading 2 — UNESCO Recommendation on the Ethics of AI, Executive Summary (2021)

| Term | Definition |
|---|---|
| Multi-stakeholder governance | Including diverse actors — civil society, marginalized communities, students, staff, and youth — in AI decisions, not only leadership or vendors. |
| Human rights-based AI governance | Grounding AI rules in international human-rights norms and human dignity, rather than only in technical risk management. |
| Right to privacy (UNESCO framing) | Privacy treated as a foundational precondition for other rights and for trust, not merely one property to be traded off against utility. |
| Meaningful human oversight | Humans retaining genuine ability to understand, intervene in, and override AI decisions — not a rubber-stamp. |
| Equity in AI benefit distribution | Ensuring AI's benefits and costs are shared fairly across groups and nations, rather than concentrated among the already-advantaged. |

**Q1 — Authority of a non-binding, unanimously adopted instrument:** Unanimous adoption by 193 states gives UNESCO strong normative and moral authority and a global baseline, but no direct enforcement — weaker in bite than the EU AI Act (binding law with penalties), yet broader in legitimacy and reach than NIST (a single-nation voluntary framework). Its force is in shaping national laws, accreditation, and professional norms rather than in direct sanction.

**Q2 — How a rights-based framing changes the advising-deployment questions:** It shifts the first question from "is the risk acceptable?" to "does this respect students' rights?" Before deploying AI in advising I would have to ask: does the student know and consent; can they reach a human and contest the output; is their data protected as a right rather than a configurable setting; and does the system treat groups equitably? These rights questions come *before* — and can veto — an otherwise favorable risk-benefit calculation.

**Q3 — UNESCO vs. NIST, what each adds:** UNESCO adds environment/sustainability, equity in benefit distribution, multi-stakeholder participation, and explicit human-rights grounding — dimensions NIST treats only implicitly. NIST adds operational specifics UNESCO leaves abstract: measurable trustworthiness properties, risk metrics, lifecycle actor roles, and concrete management functions. They are complementary — UNESCO supplies the *why/what values*, NIST the *how*.

**Q4 — What makes human oversight "meaningful":** It requires a human decision-maker who is accountable for the outcome, who can actually understand the basis of the AI's output (explainability) and override it, a student-facing appeal/contest path, audit logging, and — critically — staff who have the time, information, and authority to say no. Oversight collapses into formality whenever the human lacks any one of those, which is the usual failure under time pressure.

---

## Task 1 — Comparative Policy Analysis (Three Peer R1 Public Institutions)

*Note: the course platform's policy library wasn't accessible to me, so I analyzed three real, publicly available AI policies from public R1 universities comparable to UArizona — Arizona State University, University of Michigan, and University of Florida.*

### Institution A — Arizona State University (public R1)

| Dimension | Score | Justification |
|---|---|---|
| 1 Scope | 4 | Covers faculty, staff, students, and student researchers (ChatGPT Enterprise access; teaching, brand, and integrity guidance); contractors not explicit. |
| 2 Clarity | 4 | Specific prohibitions (no confidential data in tools; no photorealistic images of real people; cite AI) but spread across integrity, brand, and Digital Trust pages. |
| 3 Enforcement | 3 | Student use runs through the academic-integrity process and IT vetting, but no single named office/consequence for staff misuse; detection tools discouraged. |
| 4 Student protections | 4 | FERPA-compliant enterprise tools (ChatGPT EDU); recommends against unreliable detection; requires citing AI use. |
| 5 Faculty/staff rights | 4 | Instructors set course AI norms (academic freedom preserved); provided vetted enterprise tools. |
| 6 Update cadence | 3 | Actively evolving (2024 OpenAI partnership, ongoing updates) but no stated review date. |

### Institution B — University of Michigan (public R1)

| Dimension | Score | Justification |
|---|---|---|
| 1 Scope | 5 | Role-specific guidance for faculty, staff, students, and researchers across all campuses and Michigan Medicine. |
| 2 Clarity | 5 | Sensitive-data guide ties data classifications to specific approved tools ("use only approved AI services with sensitive data") — a practitioner can decide. |
| 3 Enforcement | 4 | ITS-vetted services, safecomputing third-party guidance, named ITS ownership; stated consequences less explicit. |
| 4 Student protections | 5 | U-M GPT is private, data not used for training, faculty cannot see student queries, not for surveillance; recommends against detection tools; equity/accessibility emphasized. |
| 5 Faculty/staff rights | 5 | Explicitly preserves instructor discretion, advises against detection tools, respects academic freedom; free private tools provided. |
| 6 Update cadence | 4 | Continuously maintained (2024–2025; cites EDUCAUSE June 2025) but no fixed review date stated. |

### Institution C — University of Florida (public R1)

| Dimension | Score | Justification |
|---|---|---|
| 1 Scope | 4 | Best-Practices guidance addresses students, faculty, staff, researchers, and HR; contractors not explicit. |
| 2 Clarity | 3 | Principles-forward (privacy, bias, authorship, literacy) with some specifics (UF-approved platforms; grad students responsible for AI content) but fewer precise permitted/prohibited lists. |
| 3 Enforcement | 3 | Named Integrated Risk Management review + Fast Path tool vetting and honor code, but consequences underspecified. |
| 4 Student protections | 3 | Privacy via UF-approved platforms and required citation; detection/appeal stance less developed. |
| 5 Faculty/staff rights | 4 | Instructor discretion for course use; faculty resources and an AI ethics/policy working group. |
| 6 Update cadence | 3 | 2024 Best Practices, active initiative; no explicit review date. |

**200-word synthesis — strongest policy and most common gap:** Of the three, **University of Michigan** is strongest overall. Its decisive advantage is that it pairs values with operations: a sensitive-data guide maps concrete data classifications to specific approved tools, and its institution-hosted services (U-M GPT, Maizey) make the privacy promise real — data isn't used for training, and faculty cannot surveil student queries. That converts "protect student data" from a slogan into infrastructure, and it simultaneously scores high on student protections and faculty rights by explicitly rejecting unreliable AI-detection tools. ASU is close behind, strong on tooling (FERPA-compliant enterprise access) but more integrity-centric and dispersed across pages; UF is principles-rich but thinner on operational specificity and enforcement detail.

The **most common gap across all three is governance cadence and enforcement teeth**: none states a concrete review date within twelve months or a rapid-update mechanism, and all three name responsible offices but leave the *consequences* of violation vague. In a domain where capability shifts monthly, the absence of a committed review cycle is the single most consequential shared weakness — a policy that cannot update itself on a stated schedule will silently fall out of date before the community has even adopted it. That gap, more than any individual provision, marks where the sector's governance consensus is least mature.

---

## Task 2 — Regulatory Framework Principle Application

| Document | Principle/Provision | Quote (≤30 words) | Institutional scenario | Operational implication for my role |
|---|---|---|---|---|
| NIST AI RMF | GOVERN function | "A culture of risk management is cultivated and present." | My lab is considering adopting an LLM agent to auto-generate EnergyPlus models from occupant/building data. | Before adoption I write and own a lab AI Acceptable-Use guideline (Task 4) that assigns accountability and a review cycle — not an ad-hoc choice by whoever tries the tool first. |
| NIST AI RMF | MAP function | MAP establishes the "context…to frame risks related to an AI system." | Deciding whether Claude may touch sponsor data, unpublished proposals, or occupant records. | I classify each data type's sensitivity and enumerate failure modes *before* use, routing anything non-public through U of A GenAI/AI Verde rather than a consumer tool. |
| NIST AI RMF | MEASURE function | "AI systems are…evaluated for trustworthy characteristics." | Considering an LLM to summarize student lab reports or generate feedback. | I run a small bias/hallucination audit (Module 4 method) and verify outputs before any student-facing use, and re-test after model updates. |
| UNESCO | Human oversight and determination | "human oversight and determination" of AI systems. | An advising or feedback tool proposes text that affects a student. | I keep a human as the accountable decision-maker: AI drafts, never finalizes, anything that affects a student's record or standing. |
| UNESCO | Environment and sustainability | "protecting the environment and ecosystems." | Choosing model size/compute for my building-energy research pipeline. | I prefer efficient/right-sized models, account for compute and carbon in method choices, and disclose environmental cost — consistent with my own decarbonization work. |
| UNESCO | Multi-stakeholder and adaptive governance | "multi-stakeholder…governance and collaboration." | Setting AI norms for my lab and courses. | I consult my student researchers (not just draft rules top-down) when writing the lab guideline, so those most affected help shape it. |

**Which framework is more immediately actionable, and why (3 sentences):** For my role, NIST is the more immediately actionable framework because it is operational and maps directly onto concrete steps I can take this week — classifying data (MAP), verifying and bias-checking outputs (MEASURE), and writing a lab guideline (GOVERN). UNESCO is more valuable for the questions it forces — equity, environment, and whose voice is included — that NIST leaves implicit, but it operates at the level of values rather than procedures. So I would use NIST to build my lab's workflow and UNESCO to pressure-test whether that workflow is actually just.

---

## Task 3 — AI Policy Position Paper (Question B: AI Authorship)

**Question selected:** (B) Should AI-generated text be eligible for listed authorship credit in scholarly publications?

**Position paper (~295 words):**

Generative-AI systems should never receive *listed authorship* on scholarly publications; their use should instead be disclosed in the methods or acknowledgments, because authorship entails an accountability that only a human can bear.

The strongest support is definitional. The ICMJE authorship criteria require that an author be able to take public responsibility for the work, approve the final version, and be accountable for the integrity of the whole — conditions a language model cannot satisfy, which is exactly why the ICMJE explicitly bars listing AI tools as authors. This is not an arbitrary exclusion; it follows from what authorship *is*.

A second, independent line of support comes from funder and epistemic norms. NSF's 2023 guidance holds the human proposer responsible for the accuracy and authenticity of AI-assisted content, and Bender et al. (2021) stress that an LLM has no agency or intent — it cannot answer for a claim, respond to a correction request, retract, or be sanctioned for misconduct. Accountability presupposes an agent; the model is not one.

The strongest counterargument is real: a capable model often contributes more to a paper's text and analysis than a junior co-author who nonetheless earns authorship. If credit should track contribution, denying the largest contributor recognition looks inconsistent, and labeling it merely "AI-assisted" arguably understates its role.

But scientific authorship was never a pure contribution-tracking scheme — it is a mechanism of accountability. Its defining function is that a named human stands behind the work and can be held responsible for it. Contribution without the capacity for responsibility is precisely what acknowledgment sections exist to record; the remedy for understating AI's role is fuller disclosure, not authorship.

Because authorship is accountability, not merely contribution, AI belongs in a disclosure statement — never on the author line.

---

## Task 4 — Unit-Level AI Acceptable Use Guideline

**UNIT:** TensorBuild Lab (Zhang Research Group), Civil & Architectural Engineering and Mechanics · **EFFECTIVE DATE:** 6/26/2026

**Purpose:** To let lab members use AI productively for research and writing while protecting sponsor data, unpublished work, and student researchers, and keeping the human accountable for every result that leaves the lab.

**Scope:** All lab members — PI, postdocs, graduate and undergraduate researchers, and visiting collaborators — for research code, data analysis, writing, and proposal work.

**Key definitions:** *AI-generated content* — substance produced primarily by AI with minimal human direction. *AI-assisted content* — human-directed work using AI for specific steps (drafting, refactoring, summarizing). *Approved AI tool* — an institutionally provided, privacy-preserving service (Claude/Gemini via U of A GenAI or AI Verde; Copilot with enterprise protection) cleared for the relevant data class.

**Permitted uses:** (1) drafting and refactoring non-proprietary code; (2) summarizing public literature; (3) improving clarity of our own prose; (4) brainstorming.

**Restricted uses (risk-based):** (1) no student PII or personnel data in any non-approved tool (FERPA); (2) no unpublished proposals, manuscripts, or confidential sponsor/occupant data in consumer tools (confidentiality); (3) no unverified AI facts, code, or citations in any deliverable (reliability); (4) no confidential peer-review material in any external tool.

**Disclosure:** Disclose AI-assisted content to co-authors, and to sponsors/journals per their policy; every factual/technical claim is human-verified before submission.

**Review date:** 6/26/2027 (≤12 months). **Owner:** Lab Director (PI).

---

## Self-Assessment Rubric

| Criterion (Learning Objective) | Score (1–5) | Note |
|---|---|---|
| Evaluated three peer policies on the six-dimension rubric | 5 | ASU, U-M, UF scored with justifications; U-M strongest, cadence/enforcement the common gap. |
| Applied NIST + UNESCO principles to institutional scenarios | 5 | Six-row table tied to my lab's real data and tools, with operational implications. |
| Wrote an evidence-grounded 300-word position with steelmanned counterargument | 5 | AI-authorship position built on ICMJE, NSF, and Bender et al., rebutting the contribution argument. |
| Drafted a practical unit AI Acceptable-Use Guideline | 5 | TensorBuild Lab guideline with risk-based restrictions and a 12-month review date. |
| Distinguished principles-based vs. rules-based governance and trade-offs | 5 | NIST (principles/operational) vs. UNESCO (rights) contrasted; risk-based over brand-based restrictions in Task 4. |

---

## Peer Participation

- [x] Post my **Unit AI Acceptable-Use Guideline** with a 2-sentence caption — *least-confident provision:* the disclosure requirement, because I'm unsure how granular to make it for AI-assisted code versus prose; *question for the cohort:* "For a research lab, what disclosure threshold for AI-assisted code strikes the right balance between reproducibility and unworkable overhead?"
- [ ] Respond to a peer's guideline draft whose unit type differs from mine (well-specified provision / gap / answer their question) *(to complete on the forum once a peer has posted).*
