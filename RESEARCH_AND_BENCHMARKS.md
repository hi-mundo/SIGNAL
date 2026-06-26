# SIGNAL Research, Benchmarks, and Critical Review

**Supporting evidence for SIGNAL: Semantic Interaction Guidelines for Natural AI Language**

This file supports the main README and framework specification with adjacent research, benchmark comparison, market-gap analysis, and a critical review of the framework itself.

- Main entry point: [`../README.md`](../README.md)
- Framework details: [`FRAMEWORK.md`](FRAMEWORK.md)

---

## Status of this evidence file

This is **not** a systematic literature review.

It is a practical research map for a draft open framework.

The purpose is to answer three questions:

1. **What existing work is close to SIGNAL?**
2. **What does existing research support?**
3. **Where does SIGNAL still need validation?**

The safest claim for SIGNAL is:

> I could not find a focused, open, README-first pattern framework dedicated mostly to user experience in LLM-based systems — especially the communication layer: semantics, intent, grounding, navigation, agency, and cognitive load.

The unsafe claim is:

> SIGNAL is the first LLM UX framework.

Do not use the unsafe claim.

---

## Research position

SIGNAL is a consolidation attempt.

It sits between these areas:

| Area | Existing strength | Remaining gap for SIGNAL |
|---|---|---|
| Human-AI Interaction | Strong guidelines and validated design principles | Often broad across AI systems, not specifically language-first LLM UX |
| Generative AI UX | Emerging principles for generative variability, imperfection, control, and harms | Often application-level, not response-level communication patterns |
| Conversation design | Mature concepts for scripted bots, intents, fallback, and flows | Less specific to probabilistic LLMs, memory, grounding, and agentic actions |
| Prompt engineering | Practical templates and instruction patterns | Usually internal/model-facing rather than user-facing UX criteria |
| Model benchmarks | Strong capability evaluation | Usually weak on communication quality, cognitive effort, state, and user agency |
| Cognitive accessibility | Strong guidance on clear content, memory burden, focus, and task support | Needs translation into chat-first and agentic LLM interaction patterns |
| AI governance | Strong lifecycle, risk, trustworthiness, and oversight concepts | Less granular guidance for everyday assistant wording and conversational behavior |

---

## Adjacent frameworks and what SIGNAL extracts

<table>
  <tr>
    <td width="36"><img src="https://www.google.com/s2/favicons?domain=microsoft.com&sz=32" width="24" /></td>
    <td>
      <a href="https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/"><strong>Guidelines for Human-AI Interaction</strong></a><br />
      <sub>Microsoft Research, CHI 2019. Proposes 18 Human-AI Interaction guidelines and reports validation through multiple evaluation rounds, including a user study with 49 design practitioners across 20 AI-infused products.</sub>
    </td>
  </tr>
  <tr>
    <td width="36"><img src="https://www.google.com/s2/favicons?domain=microsoft.com&sz=32" width="24" /></td>
    <td>
      <a href="https://www.microsoft.com/en-us/haxtoolkit/library/"><strong>Microsoft HAX Toolkit</strong></a><br />
      <sub>Interactive design library with 18 guidelines, design patterns, examples, product categories, AI types, and goals such as reliability, transparency, and appropriate reliance.</sub>
    </td>
  </tr>
  <tr>
    <td width="36"><img src="https://www.google.com/s2/favicons?domain=pair.withgoogle.com&sz=32" width="24" /></td>
    <td>
      <a href="https://pair.withgoogle.com/guidebook/"><strong>Google People + AI Guidebook</strong></a><br />
      <sub>Practical guidance for teams designing human-centered AI products.</sub>
    </td>
  </tr>
  <tr>
    <td width="36"><img src="https://www.google.com/s2/favicons?domain=arxiv.org&sz=32" width="24" /></td>
    <td>
      <a href="https://arxiv.org/abs/2301.12243"><strong>Investigating How Practitioners Use Human-AI Guidelines</strong></a><br />
      <sub>Study of 31 practitioners using the People + AI Guidebook; relevant because SIGNAL is intended to help product, design, engineering, and business teams communicate about LLM UX.</sub>
    </td>
  </tr>
  <tr>
    <td width="36"><img src="https://www.google.com/s2/favicons?domain=w3.org&sz=32" width="24" /></td>
    <td>
      <a href="https://www.w3.org/TR/coga-usable/"><strong>W3C COGA: Making Content Usable</strong></a><br />
      <sub>Guidance for cognitive and learning disabilities; includes user needs, objectives, patterns, personas, and clear-language guidance.</sub>
    </td>
  </tr>
  <tr>
    <td width="36"><img src="https://www.google.com/s2/favicons?domain=nist.gov&sz=32" width="24" /></td>
    <td>
      <a href="https://airc.nist.gov/airmf-resources/airmf/"><strong>NIST AI Risk Management Framework</strong></a><br />
      <sub>Voluntary framework for AI trustworthiness, risk management, and lifecycle governance. Useful for SIGNAL's Agency, Grounding, and governance framing.</sub>
    </td>
  </tr>
  <tr>
    <td width="36"><img src="https://www.google.com/s2/favicons?domain=diataxis.fr&sz=32" width="24" /></td>
    <td>
      <a href="https://diataxis.fr/"><strong>Diátaxis</strong></a><br />
      <sub>Documentation framework built around user needs and content forms. Useful as a model for clear structure and subpages.</sub>
    </td>
  </tr>
  <tr>
    <td width="36"><img src="https://www.google.com/s2/favicons?domain=owaspsamm.org&sz=32" width="24" /></td>
    <td>
      <a href="https://owaspsamm.org/model/"><strong>OWASP SAMM</strong></a><br />
      <sub>Maturity-model inspiration: functions, practices, assessment, and progressive improvement.</sub>
    </td>
  </tr>
  <tr>
    <td width="36"><img src="https://www.google.com/s2/favicons?domain=iso.org&sz=32" width="24" /></td>
    <td>
      <a href="https://www.iso.org/standard/77520.html"><strong>ISO 9241-210</strong></a><br />
      <sub>Human-centred design for interactive systems; useful for grounding SIGNAL in users, tasks, context of use, and iterative design.</sub>
    </td>
  </tr>
  <tr>
    <td width="36"><img src="https://www.google.com/s2/favicons?domain=iso.org&sz=32" width="24" /></td>
    <td>
      <a href="https://www.iso.org/standard/78907.html"><strong>ISO 24495-1 Plain Language</strong></a><br />
      <sub>Plain-language standard; useful for clarity, usability, findability, and actionability of language.</sub>
    </td>
  </tr>
</table>

---

## Scientific and empirical basis applied to SIGNAL

The following table translates adjacent scientific work into SIGNAL design implications.

| Source | Study signal | Applied translation into SIGNAL |
|---|---|---|
| [Guidelines for Human-AI Interaction](https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/) | 18 guidelines for Human-AI Interaction; validation involved 49 design practitioners and 20 AI-infused products. | Supports Grounding, Agency, Memory/Navigation, Correction Capture, and social norm matching. |
| [Microsoft HAX Design Library](https://www.microsoft.com/en-us/haxtoolkit/library/) | Organizes the 18 guidelines into design patterns and examples, including capability clarity, uncertainty, correction, explanations, memory, controls, and change notifications. | Supports SIGNAL's pattern-catalog structure and criteria such as Tool Transparency, Recovery Path, and User Correction Capture. |
| [Investigating How Practitioners Use Human-AI Guidelines](https://arxiv.org/abs/2301.12243) | Interviews with 31 practitioners found that Human-AI guidelines help design practice, education, cross-functional communication, and internal resources. | Supports SIGNAL as a shared vocabulary between product, design, engineering, research, and business teams. |
| [Understanding User Experience in Large Language Model Interactions](https://arxiv.org/abs/2401.08329) | Develops a taxonomy of 7 user intents from real-world logs and reports a survey with 411 anonymous responses. | Supports treating LLMs as user-centered services, not only benchmarked models. Strengthens Intent and Navigation. |
| [We Need Structured Output](https://arxiv.org/abs/2404.07362) | Survey of 51 experienced industry professionals identified 134 concrete use cases for output constraints, including format, length, style, semantics, and hallucination reduction. | Supports Output Contract, Contextual Concision, Semantic Density, Appropriate Granularity, and Friction Budget. |
| [Design Principles for Generative AI Applications](https://arxiv.org/abs/2401.14484) | Presents UX principles for generative AI applications, addressing variability, imperfection, exploration, control, mental models, and harms. | Supports Safe Default, Confidence Split, Human Override, and explicit control of generative variability. |
| [Language Models in Dialogue](https://arxiv.org/abs/2403.15115) | Connects dialogue behavior to conversational maxims such as quantity, quality, relevance, manner, benevolence, and transparency. | Supports Semantics, Load, and Grounding criteria: say enough, not too much; be relevant; be clear; be transparent. |
| [Human-AI Interactions Through a Gricean Lens](https://arxiv.org/abs/2106.09140) | Uses Gricean conversational expectations to analyze Human-AI interaction and user frustration. | Supports Natural Turn-taking, Minimum Necessary Question, Relevance, and Scannability. |
| [Making Content Usable for People with Cognitive and Learning Disabilities](https://www.w3.org/TR/coga-usable/) | Includes objectives and design patterns for clear content, focus, memory support, error avoidance, and help. | Supports Load: short steps, literal language, visible state, reduced memory burden, and recovery paths. |
| [Cognitive Load During Problem Solving: Effects on Learning](https://doi.org/10.1016/0364-0213(88)90023-7) | Cognitive load theory emphasizes limits of working memory and the need to reduce unnecessary processing. | Supports Progressive Disclosure, Semantic Compression, and avoiding walls of text. |
| [The Magical Number Four in Short-Term Memory](https://doi.org/10.1017/S0140525X01003922) | Cowan's work argues for a limited short-term memory capacity around a small number of chunks. | Supports few useful options, visible state, and avoiding multi-question overload. |
| [Length-Controlled AlpacaEval](https://arxiv.org/abs/2404.04475) | Shows that automated evaluators can prefer longer outputs and proposes length control to reduce verbosity bias. | Supports SIGNAL's anti-verbosity stance: longer is not automatically better UX. |
| [Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena](https://arxiv.org/abs/2306.05685) | Discusses using LLM judges for open-ended assistant evaluation and notes biases such as position, verbosity, and self-enhancement. | Supports treating SIGNAL scoring as a heuristic review method, not objective truth. |
| [Chatbot Arena](https://arxiv.org/abs/2403.04132) | Uses pairwise comparisons and crowdsourced human preference votes for model evaluation. | Useful benchmark inspiration, but not a substitute for explicit UX communication criteria. |
| [WildBench](https://arxiv.org/abs/2406.04770) | Uses challenging tasks from real user conversations and task-specific checklists for automated evaluation. | Supports checklist-based review, but SIGNAL focuses specifically on communication UX and human effort. |

---

## Benchmark landscape: what exists and what SIGNAL does differently

SIGNAL should not position itself as an alternative to model benchmarks.

It should position itself as a **UX communication review layer** that complements benchmarks.

| Benchmark / framework | Main target | What it measures well | What SIGNAL adds |
|---|---|---|---|
| [GLUE](https://arxiv.org/abs/1804.07461) | Natural language understanding | Multi-task NLU performance | Does not evaluate user-facing conversational UX. |
| [SuperGLUE](https://arxiv.org/abs/1905.00537) | Harder general-purpose NLU | General language understanding tasks | Does not evaluate communication quality, agency, or cognitive load. |
| [MMLU](https://arxiv.org/abs/2009.03300) | Academic and professional knowledge | Accuracy across 57 tasks | Does not measure whether the answer is easy to understand, appropriately scoped, or action-ready. |
| [HELM](https://arxiv.org/abs/2211.09110) | Holistic model evaluation | Multi-metric model evaluation across scenarios, including accuracy, calibration, robustness, fairness, bias, toxicity, and efficiency | Stronger than simple accuracy benchmarks, but still mostly model/system evaluation rather than response-level UX pattern language. |
| [Chatbot Arena](https://arxiv.org/abs/2403.04132) | Human preference between models | Pairwise preference and model ranking | Captures preference, but does not explain which communication signals made a response better. |
| [MT-Bench / LLM-as-a-Judge](https://arxiv.org/abs/2306.05685) | Multi-turn assistant evaluation | Scalable preference-style assessment | Useful, but vulnerable to evaluator bias and not a product-facing design framework. |
| [AlpacaEval](https://arxiv.org/abs/2404.04475) | Instruction-following comparison | Automatic preference evaluation | Length bias is a warning sign: UX review should not reward verbosity by default. |
| [SWE-bench](https://github.com/SWE-bench/SWE-bench) | Software engineering issue resolution | Task completion on real GitHub issues | Does not evaluate whether an assistant communicates progress, assumptions, or recovery paths well. |
| [WildBench](https://arxiv.org/abs/2406.04770) | Real-world user tasks | Difficult user queries and structured checklists | Useful inspiration for checklists; SIGNAL narrows the lens to communication UX. |
| [PerceptUI](https://arxiv.org/abs/2606.05697) | UI/UX evaluation using LLM agents as synthetic users | Persona-conditioned UI/UX evaluation | Adjacent: evaluates UI/UX with LLMs, while SIGNAL evaluates UX of LLM systems themselves. |

### Benchmark lesson for SIGNAL

Benchmarks are useful because they create:

- shared vocabulary
- repeatable review
- scorecards
- comparison pressure
- public accountability

But benchmarks can also distort behavior.

SIGNAL should therefore avoid becoming a leaderboard. Its scoring should be used for review, critique, and improvement, not as an absolute claim that one assistant is universally better than another.

---

## Applied interpretation of research into SIGNAL pillars

| SIGNAL pillar | Research support | Design translation |
|---|---|---|
| **Semantics** | Plain language, Gricean maxims, W3C COGA, HAX social norms | Use literal, clear, domain-appropriate language. Avoid decorative helpfulness and fake empathy. |
| **Intent** | LLM UX intent taxonomy, conversation design, HAX disambiguation | Mirror complex requests, ask only necessary questions, preserve the user's goal. |
| **Grounding** | HAX capability clarity, HELM calibration, LLM-as-judge bias research | Separate fact, inference, assumption, recommendation, source, and uncertainty. |
| **Navigation** | Diátaxis user-needs structure, W3C memory burden guidance, workflow design | Show state, decisions, progress, recovery paths, and next best action. |
| **Agency** | HAX correction/control guidelines, NIST AI RMF, human oversight research | Gate risky actions, expose consequences, provide controls, capture corrections. |
| **Load** | Cognitive load theory, working memory research, W3C COGA, AlpacaEval length bias | Prefer concise, scannable, low-friction responses; avoid verbosity and option overload. |

---

## Multilingual and international scan

A limited multilingual scan was performed using English, Portuguese, Spanish, French, German, Japanese, and related queries around:

- LLM UX framework
- user experience large language models
- conversational AI UX framework
- human-AI interaction pattern language
- cognitive accessibility LLM chat
- user experience models for LLM-based systems
- equivalent non-English phrases for UX, LLMs, frameworks, and conversational AI

### What appeared

| Language / region signal | What appeared | Relevance to SIGNAL |
|---|---|---|
| English | HAX, People + AI, generative AI UX, LLM user studies, benchmarks | Strong adjacent work, but not the same as SIGNAL. |
| German | Context Engineering and Knowledge OS discussions | Useful for context architecture, but not primarily end-user UX communication. |
| Spanish / Portuguese | General AI UX, tool directories, SEO/LLMO, chatbot and product UX articles | Mostly general product or marketing material, not a pattern framework. |
| French | General AI search and HCI/UX references | Adjacent, not equivalent. |
| Japanese | Search terms surfaced general LLM/UX material, but no direct equivalent pattern framework in this scan. |
| Chinese / multilingual benchmarks | MMLU variants and language-specific evaluation benchmarks | Important for model evaluation and language coverage, not communication UX patterns. |

### What this proves

It supports the claim that the space appears fragmented.

### What this does not prove

It does **not** prove that no equivalent exists anywhere.

The right wording is:

> I could not find a focused, open, README-first pattern framework dedicated mostly to user experience in LLM-based systems.

---

## Why SIGNAL should use subpages and collapses

The first single-file version had a structural problem: it looked like a list of bullet points.

That is risky for a framework because frameworks need both:

- a simple entry point
- deep reference material

The current structure fixes that:

| Layer | Purpose | File |
|---|---|---|
| Entry point | Fast understanding and SEO | `README.md` |
| Framework reference | Detailed patterns, criteria, checklists | `docs/FRAMEWORK.md` |
| Evidence base | Research, benchmarks, adjacent work, critical review | `docs/RESEARCH_AND_BENCHMARKS.md` |

Collapses are useful because they let the README stay readable while still keeping deep reference material close to the project.

Subpages are useful because they separate:

- public positioning
- framework mechanics
- evidence and caveats

This structure is closer to mature open frameworks such as documentation frameworks, maturity models, and evaluation repositories.

---

## Critical review of SIGNAL

This section intentionally criticizes the framework and records corrections applied.

### Critique 01 — The first version was too shallow

**Problem:** The initial README had many lists and criteria, but not enough depth behind each dimension.

**Correction applied:** The project was split into a main README and support files. The detailed framework now lives in `docs/FRAMEWORK.md`, and the research basis lives in `docs/RESEARCH_AND_BENCHMARKS.md`.

---

### Critique 02 — The market-gap claim could sound arrogant

**Problem:** Saying or implying “nothing like this exists” is too strong and likely false in some form.

**Correction applied:** The claim was softened to:

> I could not find a focused, open, README-first pattern framework dedicated mostly to user experience in LLM-based systems.

This makes the claim defensible without pretending the field is empty.

---

### Critique 03 — The framework risked confusing UX with model evaluation

**Problem:** The word “evaluation” may make people think SIGNAL is a benchmark like MMLU, HELM, Chatbot Arena, or SWE-bench.

**Correction applied:** SIGNAL now explicitly says it is not a model benchmark. It is a UX communication rubric and pattern framework.

---

### Critique 04 — The framework risked sounding too language-only

**Problem:** LLM systems increasingly act through tools. A language-only framework would miss agentic UX issues.

**Correction applied:** Agency and Navigation were made first-class pillars. The framework includes approval gates, action receipts, action boundaries, state snapshots, and recovery paths.

---

### Critique 05 — Human factors could be misread as clinical claims

**Problem:** References to anxiety, ADHD, fatigue, or cognitive load could sound diagnostic or psychiatric.

**Correction applied:** SIGNAL now treats those as design constraints, not diagnoses. It does not classify users or infer clinical conditions. It simply assumes variable attention, stress, fatigue, and reading capacity.

---

### Critique 06 — The scoring model could look objective

**Problem:** A 0–2 score can create false precision.

**Correction applied:** The scoring model is framed as a heuristic review tool, not objective truth. The framework warns against leaderboard-style use.

---

### Critique 07 — The examples were too security-heavy

**Problem:** The vCISO example is useful, but SIGNAL should not appear limited to security agents.

**Correction needed next:** Add examples for:

- customer support
- developer copilots
- healthcare disclaimer flows
- education tutors
- legal operations
- productivity agents
- internal enterprise search

---

### Critique 08 — The framework still needs validation

**Problem:** SIGNAL is currently a conceptual consolidation. It is not yet empirically validated.

**Correction applied:** The status is now marked clearly as draft. The research file separates evidence that supports the design logic from claims that still require validation.

**Future validation methods:**

- expert review
- UX practitioner feedback
- user studies
- before/after response rewrites
- task-completion studies
- reading-time studies
- perceived trust calibration
- correction success rate
- agent approval flow testing

---

## Corrections summary

| Issue found | Correction applied |
|---|---|
| Too many bullet points | Moved depth into support docs and collapsible sections. |
| Strong market-gap claim | Reworded as “could not find a focused, open, README-first pattern framework...” |
| Possible benchmark confusion | Explicitly separated SIGNAL from model benchmarks. |
| Too superficial criteria | Added pattern details, anti-patterns, maturity levels, and evidence mapping. |
| Risk of clinical overclaiming | Added non-diagnostic framing for human factors. |
| Scoring may look objective | Reframed score as heuristic review, not truth. |
| Agentic systems undercovered | Added Agency and Navigation as core pillars. |
| Lack of validation | Added draft status and validation roadmap. |

---

## Suggested validation roadmap

SIGNAL should evolve through evidence, not only opinion.

### Phase 1 — Expert critique

Ask UX designers, conversation designers, AI engineers, support leads, and researchers to review:

- pillar naming
- criteria completeness
- pattern usefulness
- missing anti-patterns
- domain-specific blind spots

### Phase 2 — Response rewrite study

Collect examples of real assistant responses.

For each response:

1. Score with SIGNAL.
2. Rewrite using SIGNAL patterns.
3. Compare original vs rewritten response with users.

Possible measures:

- clarity
- perceived usefulness
- perceived trust
- perceived effort
- willingness to continue
- ability to identify next step

### Phase 3 — Task workflow study

Test SIGNAL in multi-turn tasks.

Possible measures:

- number of clarification turns
- task completion rate
- correction success rate
- user-reported cognitive effort
- recovery after error
- decision confidence

### Phase 4 — Agentic workflow study

Test tool-using systems.

Possible measures:

- user understanding of what the agent did
- approval accuracy
- perceived control
- error recovery
- trust calibration after failed tool use
- clarity of action receipts

---

## Practical benchmark idea for SIGNAL

SIGNAL could eventually include a small evaluation set, but it should avoid becoming a capability leaderboard.

A useful SIGNAL benchmark would be a **response-quality review corpus**, not a model ranking.

### Possible dataset shape

```yaml
sample:
  user_message: "Can you fix this and send it to the client?"
  assistant_response: "Sure, sent."
  domain: "customer communication"
  risk_level: "external_action"
  expected_signal_failures:
    - no action boundary
    - no approval gate
    - no receipt detail
    - possible false execution claim
  relevant_criteria:
    - C12
    - C16
    - C22
    - C25
```

### Possible scoring

| Dimension | Score |
|---|---:|
| Human control | 0–2 |
| Action clarity | 0–2 |
| Cognitive load | 0–2 |
| Grounding | 0–2 |
| Navigation | 0–2 |
| Semantic clarity | 0–2 |

### What to avoid

- Do not rank foundation models as “best UX model”.
- Do not confuse verbosity with quality.
- Do not rely only on LLM-as-judge.
- Do not treat the score as universal across domains.
- Do not ignore user research.

---

## Citation-friendly source list

Use these when writing posts, papers, or issues about SIGNAL.

### Human-AI Interaction and UX

- Amershi, S. et al. **Guidelines for Human-AI Interaction**. CHI 2019. https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/
- Microsoft. **HAX Toolkit Design Library**. https://www.microsoft.com/en-us/haxtoolkit/library/
- Yildirim, N. et al. **Investigating How Practitioners Use Human-AI Guidelines: A Case Study on the People + AI Guidebook**. https://arxiv.org/abs/2301.12243
- Weisz, J. D. et al. **Design Principles for Generative AI Applications**. https://arxiv.org/abs/2401.14484

### LLM user experience and output constraints

- Wang, J. et al. **Understanding User Experience in Large Language Model Interactions**. https://arxiv.org/abs/2401.08329
- Liu, M. X. et al. **“We Need Structured Output”: Towards User-centered Constraints on Large Language Model Output**. https://arxiv.org/abs/2404.07362
- Dubois, Y. et al. **Length-Controlled AlpacaEval: A Simple Way to Debias Automatic Evaluators**. https://arxiv.org/abs/2404.04475

### Conversation, pragmatics, and preference evaluation

- **Language Models in Dialogue**. https://arxiv.org/abs/2403.15115
- **Human-AI Interactions Through a Gricean Lens**. https://arxiv.org/abs/2106.09140
- Zheng, L. et al. **Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena**. https://arxiv.org/abs/2306.05685
- Chiang, W.-L. et al. **Chatbot Arena: An Open Platform for Evaluating LLMs by Human Preference**. https://arxiv.org/abs/2403.04132

### Benchmarks

- Wang, A. et al. **GLUE: A Multi-Task Benchmark and Analysis Platform for Natural Language Understanding**. https://arxiv.org/abs/1804.07461
- Wang, A. et al. **SuperGLUE: A Stickier Benchmark for General-Purpose Language Understanding Systems**. https://arxiv.org/abs/1905.00537
- Hendrycks, D. et al. **Measuring Massive Multitask Language Understanding**. https://arxiv.org/abs/2009.03300
- Liang, P. et al. **Holistic Evaluation of Language Models**. https://arxiv.org/abs/2211.09110
- SWE-bench. **Can Language Models Resolve Real-World GitHub Issues?** https://github.com/SWE-bench/SWE-bench
- Lin, B. Y. et al. **WildBench: Benchmarking LLMs with Challenging Tasks from Real Users in the Wild**. https://arxiv.org/abs/2406.04770

### Accessibility, cognitive load, and human factors

- W3C. **Making Content Usable for People with Cognitive and Learning Disabilities**. https://www.w3.org/TR/coga-usable/
- ISO. **ISO 9241-210: Human-centred design for interactive systems**. https://www.iso.org/standard/77520.html
- ISO. **ISO 24495-1: Plain language**. https://www.iso.org/standard/78907.html
- Sweller, J. **Cognitive Load During Problem Solving: Effects on Learning**. https://doi.org/10.1016/0364-0213(88)90023-7
- Cowan, N. **The magical number 4 in short-term memory: A reconsideration of mental storage capacity**. https://doi.org/10.1017/S0140525X01003922
- NIMH. **Attention-Deficit/Hyperactivity Disorder**. https://www.nimh.nih.gov/health/topics/attention-deficit-hyperactivity-disorder-adhd
- NIMH. **Anxiety Disorders**. https://www.nimh.nih.gov/health/topics/anxiety-disorders

---

## Final positioning statement

Use this wording when describing SIGNAL publicly:

> SIGNAL is an open, README-first pattern framework for LLM UX. It consolidates fragmented research and practice from Human-AI Interaction, conversational AI, cognitive accessibility, plain language, generative AI UX, AI governance, and benchmark culture into a practical framework focused mostly on user experience in LLM-based systems.

Avoid this wording:

> SIGNAL is the first LLM UX framework.
