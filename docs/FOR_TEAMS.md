# UX Framework for Teams

SIGNAL is meant to be used by teams building LLM-based products and AI-assisted workflows.

It is not a software tool, a research paper, or only a writing guide.

It is a practical framework for reviewing and improving the user experience created by AI language.

---

## Product teams

Use SIGNAL to define the user experience goal of a conversational flow.

Product should answer:

- What is the user trying to accomplish?
- What can go wrong?
- What requires approval?
- What should the user feel in control of?
- What counts as a successful interaction?

Product owns:

- user goal;
- risk level;
- approval boundaries;
- success criteria;
- recovery paths.

---

## Design and UX teams

Use SIGNAL to design the conversation itself.

Design should answer:

- What should the assistant say first?
- When should it ask a question?
- When should it act with a safe assumption?
- How should it show uncertainty?
- How should it reduce stress and cognitive load?
- How should it recover from misunderstanding?

Design owns:

- conversational flow;
- message hierarchy;
- cognitive load;
- confirmation patterns;
- error language;
- user control.

---

## Engineering teams

Use SIGNAL to connect language patterns with system behavior.

Engineering should answer:

- What can the assistant actually do?
- What tool states should be visible?
- What failures can happen?
- What actions need approval?
- What receipts can be generated?
- What latency or cost should be communicated?

Engineering owns:

- tool capability;
- state visibility;
- failure modes;
- latency behavior;
- action receipts;
- runtime constraints.

---

## Eval and QA teams

Use SIGNAL to test whether the assistant communicates well.

Eval should check:

- Did the assistant understand the user goal?
- Did it ask unnecessary questions?
- Did it expose uncertainty?
- Did it show tool use clearly?
- Did it ask before external action?
- Did it give a receipt?
- Did it reduce cognitive load?
- Did it provide a recovery path?

Eval owns:

- conversation test cases;
- bad/good examples;
- scoring rubrics;
- regression tests;
- failure examples.

---

## 30-minute SIGNAL review

1. Pick one real AI conversation flow.
2. Mark each assistant message:
   - intent;
   - uncertainty;
   - progress;
   - approval;
   - action;
   - receipt;
   - recovery;
   - cognitive load.
3. Find missing user signals.
4. Rewrite the weakest 3 turns.
5. Add tests or eval checks for those turns.

---

## Output of a SIGNAL review

A useful review should produce:

- improved assistant messages;
- explicit approval boundaries;
- clearer progress updates;
- better error recovery;
- action receipts;
- eval checks;
- implementation notes for engineering.
