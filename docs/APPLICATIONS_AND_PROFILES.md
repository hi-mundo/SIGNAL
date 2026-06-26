# SIGNAL Applications and Profiles

**Domain applications, official profiles, implementations, forks, and adaptations.**

SIGNAL is a general framework for user experience in LLM-based systems.

This file is the public registry for applying SIGNAL across domains without fragmenting the core framework.

---

## Purpose

Different domains need different UX behavior.

A healthcare assistant, a public-service chatbot, a vCISO agent, a customer-support copilot, and a developer assistant should not speak, ask, refuse, remember, or act in exactly the same way.

However, the core SIGNAL model should remain centralized.

The preferred approach is:

> **One core framework, many domain profiles.**

---

## Application types

| Type | Description | Preferred location | Official status |
|---|---|---|---|
| **Core profile** | A domain-specific application accepted into this repository. | `profiles/<domain>.md` | Official after merge. |
| **Example** | A worked example showing how SIGNAL applies to a scenario. | `examples/<scenario>.md` | Official after merge. |
| **Research mapping** | A mapping between a paper, benchmark, framework, or standard and SIGNAL. | `research/<source>.md` | Official after merge. |
| **Translation** | A localized version of SIGNAL materials. | `translations/<locale>/` | Official after merge. |
| **External adaptation** | A project outside this repository that uses or modifies SIGNAL. | Listed below | Unofficial unless accepted. |
| **Forked version** | A fork that changes SIGNAL materially. | Listed below | Unofficial unless accepted. |
| **Implementation** | A product, agent, chatbot, evaluation workflow, or internal process using SIGNAL. | Listed below | Not official endorsement. |

---

## Official domain profile placeholders

Use this section to propose domain-specific applications that should live inside the canonical repository.

| Domain | Proposed profile path | Status | Maintainer | Purpose |
|---|---|---|---|---|
| Healthcare communication | `profiles/healthcare-assistant.md` | Placeholder | TBD | Safer patient-facing language, disclaimers, triage boundaries, escalation, and cognitive load. |
| Mental health support boundaries | `profiles/mental-health-support.md` | Placeholder | TBD | Non-clinical support language, crisis escalation, uncertainty, and non-therapeutic boundaries. |
| Public service | `profiles/public-service.md` | Placeholder | TBD | Plain language, eligibility explanations, accessibility, procedural state, and trust. |
| Customer support | `profiles/customer-support.md` | Placeholder | TBD | Frustration repair, escalation, refund boundaries, concise resolution paths, and tone consistency. |
| Cybersecurity / vCISO agent | `profiles/vciso-agent.md` | Placeholder | TBD | Evidence boundaries, risk language, approval gates, auditability, and action receipts. |
| Developer copilot | `profiles/developer-copilot.md` | Placeholder | TBD | Debugging state, uncertainty, concise technical explanation, and code-action boundaries. |
| Education and tutoring | `profiles/education-tutor.md` | Placeholder | TBD | Scaffolding, learner agency, progressive disclosure, and feedback tone. |
| Legal operations | `profiles/legal-operations.md` | Placeholder | TBD | Non-lawyer disclaimers, document review boundaries, evidence labeling, and escalation. |
| Finance operations | `profiles/finance-assistant.md` | Placeholder | TBD | Risk language, non-advisory constraints, source boundaries, and decision support. |
| HR and internal operations | `profiles/hr-assistant.md` | Placeholder | TBD | Sensitive communication, policy boundaries, employee trust, and escalation. |
| E-commerce | `profiles/ecommerce-assistant.md` | Placeholder | TBD | Product guidance, return/refund clarity, persuasion limits, and decision overload reduction. |
| Accessibility support | `profiles/accessibility-support.md` | Placeholder | TBD | Cognitive accessibility, plain language, assistive workflows, and low-friction interaction. |
| Government and civic services | `profiles/government-civic-services.md` | Placeholder | TBD | Public trust, procedural clarity, eligibility, documentation, and accessibility. |
| Travel and booking | `profiles/travel-booking.md` | Placeholder | TBD | Time-sensitive decisions, uncertainty, user control, and error recovery. |
| Research assistants | `profiles/research-assistant.md` | Placeholder | TBD | Citation boundaries, uncertainty, source traceability, and literature review workflow. |
| Cultural pragmatics and multilingual interaction | `profiles/cultural-pragmatics.md` | Draft | TBD | Indirect requests, idioms, expressions, locale-specific pragmatics, and non-literal user intent. |
| Brazilian Portuguese locale | `profiles/brazilian-portuguese-locale.md` | Placeholder | TBD | Soft requests, mixed Portuguese-English workflows, idioms, abbreviated phrasing, and cultural pragmatics. |
| Retrieval Overlap and grounded domain context | `profiles/retrieval-overlap-grounding.md` | Draft | TBD | Source-of-truth grounding, model-prior control, tool triggers, domain aliases, and high-stakes no-drift behavior. |
| Retrieval overlap for high-stakes domains | `profiles/retrieval-overlap-high-stakes.md` | Draft | TBD | Training-prior drift mitigation, source hierarchy, retrieval overlap, tool triggers, and high-risk no-drift behavior. |

---

## External projects, implementations, and forks

Use this section to list projects that apply, extend, or fork SIGNAL outside the canonical repository.

External projects are allowed under the license, but should clearly state whether they are official or unofficial.

| Project | Type | Domain | Repository / URL | Maintainer | Status | Notes |
|---|---|---|---|---|---|---|
| Example Project Name | SIGNAL-based implementation | Customer support | `https://github.com/<org>/<repo>` | `@maintainer` | Placeholder | Replace this row with a real implementation. |
| Example Domain Fork | Unofficial fork | Healthcare | `https://github.com/<org>/<repo>` | `@maintainer` | Placeholder | Must state that it is not official SIGNAL unless merged. |
| Example Translation | Translation | Portuguese | `https://github.com/<org>/<repo>` | `@maintainer` | Placeholder | Prefer contributing translations to `translations/<locale>/`. |
| Example Agent Review Kit | Implementation | AI agents | `https://github.com/<org>/<repo>` | `@maintainer` | Placeholder | Could map SIGNAL criteria to review prompts. |
| Example Grounded RAG Assistant | SIGNAL-based implementation | RAG / Knowledge base | `https://github.com/<org>/<repo>` | `@maintainer` | Placeholder | Uses Retrieval Overlap to map messy user wording to trusted sources and tools. |

---

## Submission format for external projects

Add a row using this format:

```md
| Project name | Type | Domain | Repository / URL | Maintainer | Status | Notes |
|---|---|---|---|---|---|---|
| My Project | SIGNAL-based implementation | Public service | https://github.com/org/repo | @handle | Unofficial | Applies SIGNAL criteria to chatbot response review. |
```

Status values:

| Status | Meaning |
|---|---|
| **Official** | Accepted into the canonical SIGNAL repository. |
| **Unofficial** | Uses or adapts SIGNAL outside the canonical repository. |
| **Experimental** | Early-stage adaptation or test. |
| **Internal** | Used inside an organization but not publicly released. |
| **Research** | Used in academic, empirical, or benchmark-related work. |
| **Deprecated** | No longer recommended or maintained. |

---

## Profile template

Use this template when proposing a domain profile.

~~~~md
# SIGNAL Profile: [Domain]

## Domain

What domain does this profile address?

## Users

Who are the primary users?

## User state assumptions

Users may be:

- tired;
- anxious;
- distracted;
- under time pressure;
- unfamiliar with the domain;
- using mobile;
- dealing with sensitive information.

## Domain risks

What can go wrong if the assistant communicates poorly?

## Required tone

Describe the expected tone.

## Forbidden tone

Describe tone patterns that should not be used.

## Required SIGNAL patterns

- Brief Mirror
- Assumption Labeling
- Confidence Split
- Action Boundary
- Next Best Action

## Forbidden anti-patterns

- Therapist Mask
- Oracle Voice
- Rogue Agent
- Politeness Tax
- Hidden State

## Criteria weighting

| SIGNAL criterion | Weight | Reason |
|---|---:|---|
| C08 Uncertainty calibration | 2x | High-risk domain. |
| C12 User control | 2x | User approval is required before external action. |
| C11 Cognitive accessibility | 2x | Users may be stressed or non-expert. |

## Example bad response

```text
...
```

## Example SIGNAL-style response

```text
...
```

## Escalation rules

When should the assistant stop and escalate to a human or qualified professional?

## References

List domain-specific references, laws, standards, papers, or product guidelines.
~~~~

---

## Fork and adaptation notice

If you publish an external adaptation, include this notice or equivalent:

> This project is an unofficial adaptation of SIGNAL: Semantic Interaction Guidelines for Natural AI Language.
> The official SIGNAL framework is maintained at https://github.com/hi-mundo/SIGNAL.
> This version has not necessarily been reviewed or accepted by the SIGNAL maintainers.

---

## Recommended repository structure for profiles

```text
profiles/
├── healthcare-assistant.md
├── mental-health-support.md
├── public-service.md
├── customer-support.md
├── vciso-agent.md
├── developer-copilot.md
├── education-tutor.md
├── legal-operations.md
├── finance-assistant.md
├── hr-assistant.md
├── ecommerce-assistant.md
├── accessibility-support.md
├── government-civic-services.md
├── travel-booking.md
├── enterprise-search.md
├── productivity-agent.md
└── research-assistant.md
```

---

## Governance rule

A profile, fork, translation, or implementation becomes **official SIGNAL** only after it is merged into the canonical repository.

Until then, it should be labeled as unofficial, experimental, internal, research, or SIGNAL-based.
