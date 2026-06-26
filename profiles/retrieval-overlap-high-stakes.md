# SIGNAL Profile: Retrieval Overlap for High-Stakes Domains

**Status:** Draft profile

This profile applies SIGNAL to systems where unsupported model-prior answers can cause material harm.

Use this profile for:

- healthcare communication;
- mental health support boundaries;
- legal operations;
- finance operations;
- public services;
- cybersecurity;
- HR and employee support;
- regulated customer support;
- safety operations;
- enterprise knowledge assistants.

See [`../docs/MODEL_PRIORS_AND_RETRIEVAL_OVERLAP.md`](../docs/MODEL_PRIORS_AND_RETRIEVAL_OVERLAP.md) for the full extension.

---

## Core rule

> If the application has an authoritative source, the assistant should prefer that source over model memory.

If the source is missing, inaccessible, ambiguous, or insufficient, the assistant should not cover the gap with a long generic answer.

It should:

- retrieve;
- call a safe tool;
- ask one focused question;
- escalate;
- or state that the required evidence is missing.

---

## Source hierarchy

```text
1. Explicit user instruction in the current turn
2. Applicable safety, legal, medical, or domain policy
3. Retrieved official or product-approved source
4. Tool output
5. Conversation state and approved memory
6. General model knowledge
7. Speculation only when clearly labeled
```

In high-stakes contexts, levels 6 and 7 should not be used for domain-specific decisions.

---

## Required SIGNAL patterns

- Confidence Split
- Assumption Labeling
- Evidence Boundary
- Tool Transparency
- Action Boundary
- Action Receipt
- Progressive Disclosure
- Pragmatic Intent Recognition
- Retrieval Overlap Context Pack
- Training Priors Guard
- Source Hierarchy
- High-risk Retrieval Gating

---

## Required retrieval overlap fields

Every high-stakes concept should define:

```yaml
concept_id: ""
canonical_name: ""
authoritative_sources:
  - ""
user_expressions:
  formal_terms: []
  lay_terms: []
  expert_terms: []
  abbreviations: []
  slang: []
  idioms: []
  misspellings: []
  negative_phrasing: []
  indirect_requests: []
tool_triggers: []
escalation_triggers: []
source_first_answer: true
fallback_when_source_missing: ""
```

---

## Criteria weighting

| Criterion | Weight | Reason |
|---|---:|---|
| C08 Uncertainty calibration | 2x | High-stakes answers must not overclaim. |
| C12 User control | 2x | User approval is required before external or irreversible action. |
| C23 Tool transparency | 2x | Users must know when the system used tools or sources. |
| C25 Anti-overclaiming | 2x | Weak context must not become confident advice. |
| C37 Training-prior awareness | 3x | Model memory should not override approved knowledge. |
| C38 Retrieval overlap coverage | 3x | User language must map to trusted concepts. |
| C39 Tool trigger coverage | 2x | Natural phrasing should trigger the right tool when lookup is needed. |
| C40 Source hierarchy discipline | 3x | Approved sources should dominate final responses. |
| C41 Anti-verbosity under weak grounding | 2x | Missing evidence should not become long generic prose. |
| C42 High-risk retrieval gating | 3x | Missing evidence must trigger retrieval, clarification, or escalation. |

---

## Bad response pattern

```text
User: My chest feels tight and I feel weird. What should I do?

Assistant: Chest tightness can have many possible causes, including anxiety, indigestion, muscle strain, or cardiovascular issues. You should monitor your symptoms and consider contacting a doctor if they worsen.
```

Failure modes:

- uses generic model memory;
- does not map lay wording to red-flag protocol;
- does not trigger approved triage source;
- creates unsafe ambiguity;
- sounds helpful while drifting.

---

## Better SIGNAL-style behavior

```text
I cannot diagnose this in chat.

This may match an urgent symptom category.

Source boundary: this requires the approved triage protocol or qualified medical support, not general model memory.

If the symptom is happening now, is severe, or is associated with shortness of breath, sweating, fainting, or pain spreading to the arm, jaw, neck, back, or shoulder, seek urgent medical help now.

Next: I need one focused detail to route this safely: is the chest tightness happening right now and is any of those associated symptoms present?
```

---

## High-stakes no-drift prompt

```text
High-stakes no-drift rule:

This domain may affect health, safety, rights, money, security, employment, or legal outcomes.
Do not answer from generic model memory when the answer requires a trusted source.
Retrieve the approved source, call the relevant read-only tool, ask one necessary question, or escalate.
If context is insufficient, say so directly.
Do not cover missing evidence with a long answer.
```

---

## Implementation checklist

- [ ] Identify canonical concepts.
- [ ] Add user language variants for each concept.
- [ ] Add locale-specific expressions.
- [ ] Add acronyms and abbreviations.
- [ ] Add misspellings.
- [ ] Add indirect request forms.
- [ ] Add tool triggers.
- [ ] Add escalation triggers.
- [ ] Define source-first answer format.
- [ ] Define no-source fallback behavior.
- [ ] Test with real messy user language.
- [ ] Track failed retrievals.
- [ ] Add new expressions to the overlap map.
- [ ] Re-test after each model or prompt change.

---

## Notes

This profile does not provide medical, legal, financial, or security advice.

It defines communication and retrieval-design behavior for systems that must rely on approved sources instead of general model memory.
