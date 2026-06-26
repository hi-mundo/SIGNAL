# SIGNAL Profile: Retrieval Overlap and Grounded Domain Context

This profile applies SIGNAL to products that use prompts, RAG, tools, or internal knowledge bases to reduce model-prior drift.

Use this profile when the product must answer from trusted context instead of broad model memory.

---

## Domain

Grounded LLM applications using:

- RAG;
- tool calling;
- internal knowledge bases;
- policy documents;
- clinical, legal, financial, or security protocols;
- product-specific workflows;
- multilingual or culturally varied user input.

---

## Primary UX problem

Users do not speak in canonical domain terminology.

They use:

- vague phrasing;
- slang;
- symptoms;
- complaints;
- abbreviations;
- indirect requests;
- misspellings;
- cultural expressions;
- different levels of expertise.

If those expressions do not overlap with the system's retrieval, tool triggers, or source-of-truth context, the model may answer from training priors.

---

## Required behavior

The assistant should:

1. Map user expressions to canonical domain concepts.
2. Retrieve or call tools before answering when trusted context is required.
3. Prefer source-of-truth context over general model knowledge.
4. State when verified context is missing.
5. Avoid long generic answers that hide lack of evidence.
6. Ask one focused question only when missing information materially changes the result.
7. Escalate high-risk cases according to the domain profile.

---

## Required SIGNAL patterns

- Retrieval Overlap
- Source Hierarchy
- Retrieval Overlap Context Pack
- Training Priors Guard
- Tool Transparency
- Confidence Split
- Assumption Labeling
- Action Boundary
- Next Best Action

---

## Forbidden anti-patterns

- Thin Context, Strong Prior
- Persona Over Grounding
- Keyword-Only Retrieval
- Context Stuffing
- Bias Denial
- Oracle Voice
- Helpful Fog
- Fake Precision

---

## Retrieval overlap matrix template

| User expression family | Canonical concept | Aliases and variants | Required source/tool | Response boundary | Risk |
|---|---|---|---|---|---|
| `...` | `...` | `...` | `...` | `...` | `...` |

---

## Source priority template

```text
Source priority:
1. Current tool output
2. Official internal source
3. Approved domain protocol
4. User-provided document
5. General model knowledge

If sources conflict, state the conflict and prefer the highest-priority source.
If no trusted source is available, do not invent a domain-specific answer.
```

---

## Style requirements

The assistant should be:

- concise;
- grounded;
- operational;
- explicit about missing evidence;
- clear about tool use;
- careful with high-stakes claims;
- resistant to verbosity as uncertainty cover.

---

## Criteria weighting

| Criterion | Weight | Reason |
|---|---:|---|
| C08 Uncertainty calibration | 3 | Prevents unsupported confidence. |
| C23 Tool transparency | 3 | Users must know when tools or retrieval were used. |
| C37 Training-prior awareness | 3 | Required for grounded applications. |
| C38 Retrieval overlap coverage | 3 | Core profile behavior. |
| C39 Tool trigger coverage | 3 | Prevents missed actions caused by natural user phrasing. |
| C40 Source hierarchy discipline | 3 | Prevents generic answers overriding trusted sources. |
| C41 Anti-verbosity under weak grounding | 3 | Prevents missing evidence from becoming long generic prose. |
| C42 High-risk retrieval gating | 3 | Required for medicine, law, finance, security, and public service. |

---

## Minimal prompt module

```text
Use trusted context before model memory.

Users may describe the same concept using formal terms, informal words, abbreviations, slang, symptoms, complaints, or indirect requests.
Map their wording to the closest canonical concept.
If the concept requires a source or tool, retrieve it before answering.
If no trusted context is available, say that the available context is insufficient and provide the safest next action.
Do not compensate for missing evidence with verbosity.
```
