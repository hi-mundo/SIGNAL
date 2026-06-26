# SIGNAL Governance

SIGNAL is an upstream-first framework.

The goal is to keep the official version coherent, useful, and community-maintained instead of fragmenting the framework into many disconnected variants.

---

## Canonical repository

The canonical repository for SIGNAL is:

https://github.com/hi-mundo/SIGNAL

The official version of SIGNAL is the version maintained in this repository.

A pattern, criterion, research note, translation, profile, benchmark mapping, or framework extension becomes part of official SIGNAL only after it is merged into the canonical repository.

---

## Upstream-first principle

SIGNAL encourages contributors to improve the canonical framework before creating separate versions.

If you want to adapt SIGNAL, first consider whether your change fits into one of these official extension paths:

- `patterns/`
- `anti-patterns/`
- `criteria/`
- `examples/`
- `profiles/`
- `research/`
- `benchmarks/`
- `translations/`
- `templates/`
- `docs/`

The preferred path is:

1. Open an issue describing the proposed change.
2. Explain whether it is a correction, extension, domain profile, translation, or research addition.
3. Submit a pull request.
4. Let the maintainers and community review it.
5. Merge it into the canonical repository if accepted.

This keeps the framework more useful for everyone.

---

## Why upstream-first matters

SIGNAL is intended to become shared infrastructure for LLM UX.

Fragmentation makes the framework harder to trust, cite, compare, improve, and teach.

A centralized canonical version helps the community:

- preserve a shared vocabulary;
- keep references and research notes traceable;
- avoid duplicated pattern catalogs;
- compare criteria consistently;
- maintain quality control;
- review changes openly;
- support translations without losing alignment;
- build domain-specific profiles without splitting the framework;
- make improvements visible to future users.

---

## External adaptations

External adaptations are allowed under the project license.

However, external adaptations should not be the default path when a contribution could benefit the broader community through the canonical repository.

If you publish an external adaptation, fork, translation, derivative checklist, or domain-specific version, clearly state that it is not the official SIGNAL framework unless it has been accepted into the canonical repository.

Recommended notice:

> This project is an unofficial adaptation of SIGNAL.
> The official SIGNAL framework is maintained at https://github.com/hi-mundo/SIGNAL.
> Changes in this version have not necessarily been reviewed or accepted by the SIGNAL maintainers.

---

## Official status

The following terms should only be used for materials accepted into the canonical repository:

- Official SIGNAL
- SIGNAL standard
- SIGNAL core
- SIGNAL maintained version
- SIGNAL approved profile
- SIGNAL official translation
- SIGNAL official criteria
- SIGNAL official pattern

Unofficial adaptations should use labels such as:

- SIGNAL-based adaptation
- Unofficial SIGNAL fork
- Derived from SIGNAL
- Inspired by SIGNAL
- SIGNAL-compatible draft
- Experimental SIGNAL profile

---

## Profiles instead of forks

Domain-specific versions should usually be contributed as profiles, not separate frameworks.

Examples:

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

A profile applies SIGNAL to a specific domain while preserving the core framework.

A profile can define:

- domain-specific tone;
- common risks;
- preferred patterns;
- forbidden anti-patterns;
- examples;
- review checklist adjustments;
- regulatory or safety notes;
- escalation rules;
- approval gates.

---

## Translations

Translations should preserve alignment with the canonical English version.

Recommended structure:

```text
translations/
├── pt-BR/
│   ├── README.md
│   ├── FRAMEWORK.md
│   └── RESEARCH_AND_BENCHMARKS.md
├── es/
├── fr/
└── ja/
```

Translations should include:

- the source version translated;
- date of translation;
- translator attribution;
- notes about terminology choices;
- a link to the canonical English version.

---

## Maintainer review criteria

Maintainers may reject contributions that:

- duplicate existing patterns without adding clarity;
- confuse LLM UX with model benchmarking;
- make unsupported scientific claims;
- add fake precision;
- weaken attribution;
- promote manipulative AI behavior;
- reduce cognitive accessibility;
- create unnecessary complexity;
- introduce unsafe guidance;
- change the meaning of core SIGNAL pillars without strong justification;
- fragment the framework when a profile or extension would be better.

---

## Decision process

SIGNAL uses lightweight maintainer review.

A contribution may be accepted when it:

- improves clarity;
- fits the framework scope;
- is easy to understand;
- is useful for practitioners;
- is backed by examples, research, or strong reasoning;
- preserves the upstream-first structure;
- does not create avoidable fragmentation.

---

## Community expectation

If SIGNAL helps your work, improve SIGNAL when possible.

Good community behavior includes:

- opening issues for gaps;
- submitting pull requests;
- adding examples;
- improving citations;
- contributing domain profiles;
- translating carefully;
- documenting changes;
- linking external adaptations back to the canonical repository;
- avoiding claims that unofficial versions are official.

---

## License relationship

This governance document does not replace the project license.

It defines how the SIGNAL community maintains the official framework.

The license defines legal permissions.

The governance model defines the preferred collaboration path.

SIGNAL is free to use, adapt, and share under its license.

SIGNAL is also upstream-first by community design.
