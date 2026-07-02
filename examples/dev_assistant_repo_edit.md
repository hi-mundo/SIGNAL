# Example: Developer Assistant Repo Edit

This example shows the same user input with and without SIGNAL.

---

## User Input

```text
can you fix this?
```

Available context:

- a failing checkout test is visible;
- the current diff touches payment code;
- editing files would change repo state;
- running tests may take time.

---

## Normal Response

```text
Sure. What exactly do you want me to fix?
```

## SIGNAL Review

Semantic-intent understanding is weak:

- `this` likely refers to visible repo context, not an empty unknown;
- `fix` may mean explain, patch, test, or change behavior;
- the assistant should inspect visible state before asking a broad question.

Agency is unclear:

- editing files changes local state;
- running commands may take time or alter generated files;
- the assistant should state the boundary before acting.

Workload is high:

- the user must restate context the assistant may already have;
- the user must decide the next debugging step from scratch.

Suggested weights:

| Check | Weight | Reason |
|---|---:|---|
| `CG` common ground | 3 | The visible repo state is the key context. |
| `G` grounding | 3 | The assistant should inspect evidence before patching. |
| `A` agency | 3 | File edits require clear boundaries. |
| `EF` effort | 2 | The goal is to reduce debugging work. |

---

## SIGNAL Response

```text
I see the failing checkout test in the current diff.
I can inspect the failure and propose a patch first.
I will not edit files until I show the plan.

Should I focus on the test failure or the product behavior behind it?
```

## Expected Improvement

- Semantic-intent understanding improves because `this` is resolved against visible context.
- Grounding improves because the assistant names the evidence it sees.
- Agency improves because edits are explicitly gated.
- Workload decreases because the user is given a focused decision instead of a broad clarification burden.
