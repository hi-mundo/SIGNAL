# SIGNAL Flow Spec

Use this template before redesigning or evaluating one AI interaction flow.

---

## Flow

Name:

```text
...
```

Primary user goal:

```text
...
```

---

## Context

What can the system know before responding?

- [ ] current user message
- [ ] prior conversation
- [ ] visible UI state
- [ ] selected object, file, ticket, record, or document
- [ ] user profile or preferences
- [ ] tool results
- [ ] retrieved sources
- [ ] workflow state

Notes:

```text
...
```

---

## Risk And Agency

What can create consequences for the user?

- [ ] external send
- [ ] purchase or payment
- [ ] deletion
- [ ] production change
- [ ] medical, legal, financial, or security advice
- [ ] personal data use
- [ ] preference or memory update
- [ ] irreversible or hard-to-reverse action

Approval boundary:

```text
...
```

---

## Weighted Review Setup

Choose weights before scoring.

Semantic-intent weights:

| Check | Weight | Reason |
|---|---:|---|
| `S` semantic clarity | 1 |  |
| `I` pragmatic intent / speech act | 1 |  |
| `R` relevance to user goal | 1 |  |
| `M` manner / clarity of expression | 1 |  |
| `CG` common ground preserved | 1 |  |

Workload weights:

| Check | Weight | Reason |
|---|---:|---|
| `MD` mental demand | 1 |  |
| `TD` temporal demand | 1 |  |
| `EF` effort | 1 |  |
| `FR` frustration | 1 |  |
| `P_inv` inverted performance burden | 0 | optional |

---

## Before / After

User input:

```text
...
```

Normal or current response:

```text
...
```

SIGNAL rewrite:

```text
...
```

---

## Expected Improvement

Semantic-intent improvement:

```text
...
```

Workload reduction:

```text
...
```

Agency preserved:

```text
...
```

Eval rule to add:

```text
...
```
