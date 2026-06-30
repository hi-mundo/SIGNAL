# SIGNAL Patterns

This document contains practical techniques for designing AI user experience through language.

Each pattern follows the same structure:

- Problem
- Technique
- User effect
- Bad example
- Better example
- Theory behind it
- References

---

## 1. Brief Mirror

### Problem

The user gives a complex, informal, or ambiguous request. The assistant may answer the wrong task.

### Technique

Briefly restate the assistant's interpretation before acting.

### User effect

The user can quickly see whether the system understood the goal.

### Bad

```text
Sure, here is an explanation of productivity systems.
```

### Better

```text
I am treating this as a request to organize your weekday routine, not as a deep-work schedule.
```

### Theory behind it

Conversation works through shared context. A brief mirror creates alignment before work begins.

### References

- Clark & Brennan — grounding in communication
- Speech act theory
- Human-AI interaction guidelines

---

## 2. Ask-or-Act

### Problem

Assistants often ask too many questions, even when a safe default is enough.

### Technique

Ask only when the missing information would materially change the result. Otherwise, proceed with an explicit assumption.

### User effect

Reduces friction and typing effort.

### Bad

```text
What format, tone, audience, length, style, goal, and structure do you want?
```

### Better

```text
I will assume this is for a public README and keep it concise.
```

### Theory behind it

Users have limited attention and working memory. Unnecessary questions increase cognitive load.

### References

- Cognitive load theory
- Working memory research
- Conversational repair

---

## 3. Context Recovery

### Problem

The user's latest message does not clearly connect to the previous turn. The assistant may ask the user to repeat context that already exists in the conversation, active state, visible environment, or recent tool results.

### Technique

Before asking a broad clarification question, check earlier conversation, active task, selected file, open screen, recent tool output, and current environment. If there is a likely reference, make that interpretation explicit and proceed only when the action is safe. Ask a focused question when ambiguity changes the action, cost, risk, or consequence.

### User effect

Reduces typing effort and preserves conversational continuity. The user does not have to restate the whole situation just because the latest message was compressed or indirect.

### Bad

```text
What do you mean?
```

### Better

```text
I am treating "that one" as the deployment error from earlier. I will use that interpretation unless you meant a different item.
```

### Theory behind it

Conversation depends on shared context. Users often refer to earlier topics, visible state, or something happening now without naming it again.

### References

- Conversational grounding
- Context continuity
- Cognitive load theory

---

## 4. Confidence Split

### Problem

The assistant mixes facts, assumptions, inferences, and recommendations.

### Technique

Separate what is known, inferred, assumed, and recommended.

### User effect

The user can act without confusing certainty with speculation.

### Bad

```text
This is definitely the best architecture.
```

### Better

```text
Known: the repo is public.
Assumption: the target audience is product and engineering teams.
Recommendation: keep the README short and move research details into docs.
```

### Theory behind it

Trust depends on calibrated confidence. Users need to know what the answer is based on.

### References

- Trust in automation
- Human-AI interaction guidelines
- Explainability and transparency research

---

## 5. Visible Work Trace

### Problem

The assistant goes silent during long work. The user does not know if it is working, stuck, or broken.

### Technique

Show short, truthful operational progress updates.

### User effect

Reduces uncertainty and makes waiting easier.

### Bad

```text
Thinking...
```

### Better

```text
I am checking the calendar now.
I will keep deep-work blocks empty and only create fixed routine events.
```

### Theory behind it

Silence in conversation is meaningful. In a language interface, silence can feel like failure or abandonment. Progress feedback makes waiting more understandable.

### References

- Progress indicators in HCI
- Waiting-time perception
- Turn-taking in conversation
- Operational transparency

---

## 6. Approval Boundary

### Problem

The user may not know whether the assistant is only suggesting something or actually taking action.

### Technique

Clearly separate recommendation, draft, and execution.

### User effect

Preserves user control and prevents surprise.

### Bad

```text
I updated your calendar.
```

### Better

```text
I can update your calendar, but I need your approval before creating events.
```

### Theory behind it

Automation trust depends on appropriate reliance and visible control boundaries.

### References

- Trust in automation
- Human-AI interaction guidelines
- Agency and consent patterns

---

## 7. Action Receipt

### Problem

After the assistant acts, the user may not know what changed.

### Technique

Give a concise receipt after external action.

### User effect

Improves confidence, auditability, and recovery.

### Bad

```text
Done.
```

### Better

```text
Done: created 5 recurring weekday events.
Not changed: deep-work blocks.
Failed: none.
```

### Theory behind it

Users need closure after state changes. Receipts reduce ambiguity and support recovery.

### References

- Service design
- Error recovery UX
- Human-AI interaction guidelines

---

## 8. Recovery Path

### Problem

When something fails, assistants often stop at the error.

### Technique

Explain what failed and what the user can do next.

### User effect

Reduces frustration and keeps the task recoverable.

### Bad

```text
Permission error.
```

### Better

```text
Permission error: I could not update the calendar.
Next: check calendar access or create the events manually from this list.
```

### Theory behind it

Failure is less stressful when the user has a next step.

### References

- Error recovery UX
- Cognitive accessibility
- Human factors

---

## 9. Cognitive Compression

### Problem

The assistant gives too much information at once.

### Technique

Compress the response around the user's immediate decision or next action.

### User effect

Reduces reading fatigue and decision effort.

### Bad

```text
A long essay explaining every possible option.
```

### Better

```text
Use option A.
Reason: it is safer and easier to reverse.
Alternative: option B if you need speed.
```

### Theory behind it

Working memory is limited. The interface should reduce unnecessary processing.

### References

- Cognitive load theory
- Working memory research
- Plain language

---

## 10. Constraint Preservation

### Problem

The assistant may ignore an important user constraint during a long task.

### Technique

Repeat the constraint only when it matters to the action.

### User effect

The user can see that the system is respecting the boundary.

### Bad

```text
I will organize your calendar.
```

### Better

```text
I will organize only the fixed routine blocks and leave deep-work time empty.
```

### Theory behind it

Users trust systems more when important constraints remain visible.

### References

- Goal preservation
- Grounding in communication
- Trust calibration

---

## 11. Human Repair

### Problem

The assistant gets something wrong and makes the user do the repair work.

### Technique

Accept the correction, update the state, and continue.

### User effect

Reduces frustration and keeps the flow moving.

### Bad

```text
Can you explain better?
```

### Better

```text
Correction applied: you mean communication UX for AI, not visual UX. I will use that framing now.
```

### Theory behind it

Good conversations include repair. The system should absorb correction without punishing the user.

### References

- Conversational repair
- Grounding in communication
- Human-AI interaction guidelines
