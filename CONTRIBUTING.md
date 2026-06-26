# Contributing to SIGNAL

SIGNAL is upstream-first.

Before creating a separate version of the framework, consider whether your idea can become part of the canonical repository.

---

## Preferred contribution types

You can contribute:

- patterns;
- anti-patterns;
- criteria;
- scoring improvements;
- research notes;
- benchmark mappings;
- retrieval overlap maps;
- model-specific behavior notes based on measured tests;
- examples;
- templates;
- translations;
- domain profiles;
- cultural pragmatics examples;
- idiom and expression examples;
- locale-specific prompt modules;
- glossary improvements;
- diagrams;
- criticism;
- issue reports;
- contributor photos and metadata.

---

## Before creating a forked framework

Ask:

1. Is this a new SIGNAL pattern?
2. Is this a domain profile?
3. Is this a cultural pragmatics example or locale-specific expression?
4. Is this a translation?
5. Is this a research note?
6. Is this a benchmark mapping?
7. Is this an example?
8. Is this a correction to the core model?
9. Is this better as a pull request?

If yes, prefer contributing upstream.

---

## Alpha collaboration workflow

SIGNAL is still in alpha. During this phase, prefer small, structurally coherent pull requests.

Pull requests may target `main` directly as their base branch. Direct commits to `main` are reserved for maintainers.

Each merged pull request should represent one structural change. A PR may touch multiple files when those files are part of the same change, such as adding one extension and linking it from the index, framework, and research map. Avoid mixing unrelated documentation cleanup, new benchmarks, profile changes, and pillar changes in the same PR.

Use `v0` only as the first clean baseline marker. During alpha, use `alpha baseline`, `alpha marker`, or `change marker` instead of release-language.

### Change scale

Use this scale to describe the size of a documentation change:

| Marker | Use for | Examples |
|---|---|---|
| `patch / 0.0.x` | Text corrections, example fixes, formatting fixes, and structure-only corrections. | Fix typos, tighten examples, repair links, clarify wording without changing meaning. |
| `minor / 0.x.0` | Topic additions, benchmark additions, or corrections that change a topic's meaning. | Add a research row, add a benchmark mapping, rewrite a topic to change its semantic claim. |
| `major / x.0.0` | New content areas or changes to SIGNAL pillars, core criteria, or governing concepts. | Add a new extension, revise a pillar, change the core model. |

### Naming

Use one naming shape across branches, PRs, and merge commits:

```text
Branch: docs/<scale>/<structural-slug>
PR title: docs(<area>): <scale> - <structural change>
Merge commit: same as the PR title
```

Examples:

```text
docs/patch/fix-visible-work-trace-examples
docs(visible-work-trace): patch - fix examples

docs/minor/add-progress-feedback-benchmarks
docs(research): minor - add progress feedback benchmarks

docs/major/revise-navigation-pillar
docs(framework): major - revise Navigation pillar
```

If work happens across GitHub accounts, keep the branch and PR naming stable. The account that opens the PR can own the PR record. Add `Co-authored-by:` trailers only when another person materially authored part of the contribution.

---

## Domain-specific adaptations

Domain-specific adaptations should usually be added as profiles.

Examples:

```text
profiles/healthcare-assistant.md
profiles/mental-health-support.md
profiles/public-service.md
profiles/customer-support.md
profiles/vciso-agent.md
profiles/developer-copilot.md
profiles/education-tutor.md
profiles/legal-operations.md
profiles/finance-assistant.md
profiles/accessibility-support.md
profiles/cultural-pragmatics.md
profiles/brazilian-portuguese-locale.md
```

A profile should not redefine SIGNAL from scratch.

It should apply SIGNAL to a specific domain.

---

## How to submit a profile

1. Open an issue with the proposed domain.
2. Explain the users, risks, context, and why a profile is needed.
3. Add a profile file under `profiles/<domain>.md`.
4. Add a row to `docs/APPLICATIONS_AND_PROFILES.md`.
5. Include examples of bad, average, and SIGNAL-style responses.
6. Map the profile to SIGNAL criteria.
7. Add references when domain claims are scientific, legal, medical, financial, safety-related, or regulatory.

---

## Profile contribution template

~~~~md
# SIGNAL Profile: [Domain]

## Domain

What domain does this profile address?

## Users

Who are the primary users?

## User state assumptions

Users may be tired, anxious, distracted, under time pressure, non-expert, or using mobile.

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

## Pattern contribution template

Use this when proposing a reusable SIGNAL pattern.

````md
# Pattern: [Name]

## Problem

What user experience problem does this solve?

## Context

When does this pattern apply?

## Solution

What should the assistant, chatbot, or agent do?

## Example

### Bad

```text
...
```

### Good

```text
...
```

## Risks

When can this pattern be harmful?

## Related SIGNAL pillars

- Semantics
- Intent
- Grounding
- Navigation
- Agency
- Load

## Related patterns

- ...
````

---

## Anti-pattern contribution template

````md
# Anti-pattern: [Name]

## Problem

What bad behavior does this describe?

## Why it happens

Why do LLM systems commonly produce this?

## Why it hurts UX

What does it do to trust, clarity, control, or cognitive load?

## Bad example

```text
...
```

## Better alternative

```text
...
```

## Related SIGNAL criteria

- C01
- C08
- C12
````

---

## Adding an external project, implementation, or fork

Add the project to `docs/APPLICATIONS_AND_PROFILES.md` using this format:

```md
| Project name | Type | Domain | Repository / URL | Maintainer | Status | Notes |
|---|---|---|---|---|---|---|
| My Project | SIGNAL-based implementation | Public service | https://github.com/org/repo | @handle | Unofficial | Applies SIGNAL criteria to chatbot response review. |
```

External versions should not imply official status unless accepted into the canonical repository.

---

## Adding yourself as a contributor

After contributing, add yourself to `CONTRIBUTORS.md`.

Example:

```html
<td align="center" width="120">
  <a href="https://github.com/example-user">
    <img src="https://github.com/example-user.png?size=120" width="96" height="96" alt="example-user" style="border-radius: 50%;" />
    <br />
    <sub><strong>@example-user</strong></sub>
  </a>
  <br />
  <sub>Pattern / Research</sub>
</td>
```

Recommended contribution labels:

- Framework
- Pattern
- Anti-pattern
- Criteria
- Research
- Benchmark mapping
- Domain profile
- Translation
- Example
- Documentation
- Review
- Governance
- Accessibility
- Community

---

## Contribution quality bar

A good contribution should be:

- clear;
- practical;
- scoped;
- reusable;
- non-manipulative;
- human-centered;
- easy to review;
- consistent with the SIGNAL pillars;
- supported by examples or references when possible.

---

## What maintainers may reject

Maintainers may reject contributions that:

- fragment the framework unnecessarily;
- duplicate existing concepts;
- confuse UX criteria with model benchmarks;
- make unsupported claims about a model's behavior, training data, country, or vendor;
- make unsupported scientific claims;
- reduce clarity;
- increase cognitive load;
- promote manipulative AI behavior;
- imply official endorsement of external tools;
- introduce legal, clinical, financial, or security claims without careful scope.

---

## Official status

A contribution becomes official only after it is merged into the canonical repository.

Forks, adaptations, and external versions are not official unless accepted by maintainers.
