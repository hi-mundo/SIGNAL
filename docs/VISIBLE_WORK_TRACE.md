# Visible Work Trace

**Status:** draft SIGNAL extension
**Primary pillar:** N — Navigation
**Secondary pillars:** G — Grounding, A — Agency, L — Load
**Related patterns:** Tool Transparency, Action Boundary, Action Receipt, State Snapshot, Recovery Path, Progressive Disclosure

---

## Core thesis

A long AI turn is not only a performance event. It is a communication event.

In a language-first product, silence is not neutral. Silence is an ambiguous signal. The user may interpret it as latency, system failure, abandoned work, a lost stream, a weak model, or a tool bug.

**Visible Work Trace** means exposing concise, truthful, user-facing operational state during long-running AI work.

It is not chain-of-thought exposure. It is not a fake transcript of private reasoning. It is not decorative text such as `thinking...` repeated until completion.

A useful work trace shows:

- what operation is being performed;
- what boundary or constraint is being preserved;
- what tool or source is being used at a human level;
- what changed;
- what did not change;
- what will happen next.

The user does not need to see the model's private reasoning. The user needs evidence that the work is active, bounded, and moving in the right direction.

---

## Short definition

> **Visible Work Trace:** a concise operational progress signal that lets the user understand what an AI system is doing during long or tool-mediated work, without exposing private reasoning or adding fake progress.

---

## Why this matters in LLM UX

Traditional UI can show progress through changing visual surfaces: a diff, a file tree, a review checklist, a status tracker, a progress bar, an install log, or a loading skeleton.

Coding agents make this especially visible. When an AI code tool modifies a repository, the user can inspect additions, deletions, changed files, tests, commits, and diffs. The work becomes legible because the interface exposes transformation.

Chat-first agents often lose this property. If the assistant disappears during tool use and returns minutes later with only `Done`, the user has no evidence of continuity. This can cause retries, page refreshes, duplicate actions, interrupted streams, or loss of trust.

For SIGNAL, this is mainly a **Navigation** failure: the user loses state, progress, and next action. It is also a **Load** failure, because the user must hold uncertainty in working memory. It is a **Grounding** failure when tool use is hidden. It can become an **Agency** failure if the system modifies external state without a clear action boundary and receipt.

---

## Evidence map

This is not a claim that every AI system must constantly narrate itself. The evidence supports a narrower claim:

> When a task is slow, uncertain, multi-step, tool-mediated, or externally state-changing, timely and meaningful progress feedback reduces uncertainty and improves the user's ability to wait, trust, recover, and stay oriented.

| Evidence area | Source signal | What it supports for Visible Work Trace |
|---|---|---|
| Usability heuristics | Nielsen's visibility-of-system-status heuristic says systems should keep users informed through timely feedback. | A silent long turn violates a core UI principle: users need to know what is happening. |
| Response-time thresholds | Nielsen summarizes long-standing HCI thresholds: about 0.1s feels instantaneous, about 1s preserves flow, and about 10s is the limit for keeping attention on the dialogue. | For AI turns longer than a few seconds, status feedback becomes part of the interface, not decoration. |
| Progress indicators | Myers (1985) and later UX guidance show that percent-done indicators and running progress feedback reduce anxiety and make waiting more tolerable. | A work trace is the language-first equivalent of progress feedback when a true percent is unavailable. |
| Wait tolerance | NN/g reports a study in which users shown a moving progress indicator were willing to wait on average about 3 times longer than users with no progress indicator. | Feedback does not merely report progress; it changes the user's experience of the wait. |
| Perceived performance | Gao et al. (2017) found that common web performance metrics such as `onLoad` and `TTFB` matched human perceived speed less than 60% of the time; a simple 3-variable model predicted perceived speed choices with 87 ± 2% accuracy. | Objective latency and experienced latency differ. AI UX should optimize perceived continuity, not only raw speed. |
| Progress-bar perception | Wang, Kang, and Rau (2022) tested 5-second progress bars with 40 trials per condition and found constant and speed-up progress bars were perceived as fastest. | Progress design changes time perception; generic indicators can be inferior to better-structured feedback. |
| Human-AI interaction guidelines | Amershi et al. (2019) proposed 18 Human-AI Interaction guidelines and validated them with 49 design practitioners across 20 AI-infused products. | AI systems need interaction-level feedback, uncertainty handling, correction support, and state clarity. |
| Conversation and turn-taking | Conversation-analysis work shows that human turn-taking minimizes gaps and overlaps; Stivers et al. (2009) studied 10 languages and found both universal pressure toward short gaps and cultural variation in timing. | Silence in a conversational interface is socially meaningful, not merely absent data. |
| Grounding in communication | Clark and Brennan's grounding theory treats acknowledgments, confirmations, and evidence of understanding as part of successful joint activity. | Work traces act as grounding signals: they show the system received the task and is acting within the right shared context. |
| Waiting psychology | Maister's service-design rules argue that uncertain and unexplained waits feel longer, while occupied and explained waits feel shorter. | `Thinking...` only says the system is alive; an operational trace explains what kind of wait this is. |
| Operational transparency | Buell and Norton argue that making operational work visible can increase perceived effort and value. | Users may value AI work more when they can see credible evidence of effort and transformation. |
| Cognitive load | Cognitive load theory and working-memory research show that unnecessary mental bookkeeping harms task performance. | A silent agent forces the user to maintain state, doubt, and recovery plans mentally. Visible state reduces that burden. |
| Anxiety and uncertainty | Clinical and neuroscience literature links uncertainty and anticipation to anxiety and vigilance. | SIGNAL should not make psychiatric claims about ordinary users, but it can safely treat uncertainty as a stress-amplifying UX factor. |
| Algorithmic transparency | Kizilcec (2016) found that too little or too much algorithmic transparency can reduce trust; moderate transparency can be preferable. | Visible Work Trace should reveal enough operational state to orient the user, not flood them with internals. |
| Chain-of-thought faithfulness | Turpin et al. (2023) and Lanham et al. (2023) show that chain-of-thought explanations are not always faithful to the model's actual causal process. | The safe design target is operational transparency, not private-reasoning disclosure. |

---

## Practical benchmark thresholds

These are working thresholds for product review, not universal laws.

| Situation | Recommended signal |
|---|---|
| Under ~1 second | Usually no separate progress message. Return the result. |
| ~1–10 seconds | Give immediate lightweight feedback if the user action is not visibly acknowledged by the UI. |
| Over ~10 seconds | Provide visible progress or work-state feedback. If duration is unknown, report absolute work done or current step instead of fake percentages. |
| Tool use with external state | Always show an action boundary before execution when risk exists, and an action receipt after execution. |
| Multi-step agent workflow | Expose meaningful step transitions: checked, found, created, skipped, failed, next. |
| High-risk or high-anxiety context | Prefer earlier receipts, clearer boundaries, and explicit recovery paths. |
| Unknown duration | Use operational trace rather than a fake progress bar. Example: `Checked 3 sources. Next: validating conflicts.` |

---

## Pattern: Visible Work Trace

### Problem

The assistant performs a long-running task, uses tools, or changes external state, but the user cannot tell whether the task is active, stalled, forgotten, failed, or completed.

In chat-first products, the conversation is the main interface. If the assistant stays silent, the user loses the only available signal of continuity.

### Solution

Expose concise, truthful operational state during long AI turns.

A work trace should show task progress without exposing private reasoning. It should be tied to real state, a real tool result, or a real decision boundary.

### Use when

- the task may take more than a few seconds;
- the assistant is using tools;
- the assistant is modifying files, calendars, emails, tickets, databases, or external systems;
- the workflow has multiple steps;
- the user could reasonably worry about duplication, failure, or lost context;
- the user has no other feedback surface besides language.

### Avoid when

- the answer is immediate;
- the trace would be fake or decorative;
- the trace would leak sensitive internals, private reasoning, credentials, policy details, or security-relevant implementation details;
- the user needs a concise final answer and progress updates would add noise;
- the task is high-risk and needs approval before execution.

---

## Good trace shape

```text
I will create only the fixed weekday anchors and leave deep-work blocks empty.
I will avoid duplicating the existing 8:00 meeting.
```

```text
Checked calendar.
Found the existing 8:00 meeting, so I will not create another one.
Next: creating the recurring support blocks.
```

```text
Done.
Created weekday recurring anchors starting June 29, 2026.
Left deep-work periods empty.
Marked visual-only routines as non-blocking.
```

Why this works:

- states the interpreted task;
- preserves constraints;
- exposes tool progress;
- reports skipped/unchanged scope;
- gives an action receipt;
- avoids private reasoning.

---

## Bad trace shape

```text
Thinking...
```

```text
Still working...
```

```text
Almost done...
```

```text
Done.
```

Why this fails:

- does not reduce uncertainty;
- does not expose the current operation;
- does not preserve user constraints visibly;
- does not help the user recover if something fails;
- may feel like a weak spinner translated into text.

---

## Distinguish work trace from chain-of-thought

Visible Work Trace should reveal **workflow state**, not **private reasoning**.

| Reveal | Do not reveal |
|---|---|
| `Checking the calendar for existing Monday events.` | Full hidden deliberation about why the schedule should be arranged one way or another. |
| `Found an existing 8:00 meeting; I will not duplicate it.` | Unfiltered internal token-by-token reasoning. |
| `Created 5 recurring events; 1 failed because permission was missing.` | Speculative internal explanations not grounded in tool output. |
| `Next: summarizing what changed.` | Security-sensitive implementation details. |

A good trace is **auditable at the workflow level**. It does not pretend to expose the model's true internal cognition.

---

## Anti-pattern: Silent Long Turn

### Definition

The assistant performs a long-running operation without any visible status or progress signal.

### Bad

```text
[No response for several minutes]

Done.
```

### Why it fails

- The user cannot distinguish work from failure.
- The user may refresh, retry, or interrupt the stream.
- Duplicate actions may be triggered.
- The system appears slower and less reliable than it may actually be.
- The final receipt carries more trust burden because no intermediate state was visible.

### Fix

```text
I will check the calendar first, then create only the non-deep-work anchors.
I will report exactly what changed and what I skipped.
```

---

## Anti-pattern: Spinner Theater

### Definition

The interface shows generic activity without meaningful work state.

### Bad

```text
Thinking...
Thinking...
Thinking...
```

### Why it fails

A spinner or animated label can prove that the UI has not died, but it usually does not tell the user whether the system is doing the right work.

### Better

```text
Checked the current calendar.
Next: creating lunch, closing, and pet-care anchors only.
```

---

## Anti-pattern: Fake Work Trace

### Definition

The assistant emits progress-like statements that are not connected to actual state, tool output, or completed work.

### Bad

```text
Almost done...
Just polishing...
Finalizing...
```

### Why it fails

Fake progress can be worse than silence because it creates false trust. A work trace must be grounded in actual state transitions.

### Better

```text
Tool result received.
Created 5 recurring events.
Failed: 1 event could not be created because calendar permission was missing.
```

---

## Anti-pattern: Internal Log Dump

### Definition

The assistant exposes too much raw operational detail, API noise, stack traces, or implementation internals.

### Bad

```text
Calling calendar.events.insert with RRULE:FREQ=WEEKLY;BYDAY=MO,TU,WE,TH,FR and extendedProperties.private...
```

### Better

```text
Creating weekday recurring calendar anchors.
They will repeat Monday through Friday and stay within the fixed routine scope.
```

The user should see the product-level operation unless they are debugging the integration.

---

## Criteria additions

These criteria can be added to the SIGNAL criteria table.

| ID | Criterion | Pillar | Good | Weak | Failure |
|---|---|---|---|---|---|
| C-VWT-1 | Long-turn visibility | Navigation | Long or tool-mediated tasks expose concise work state before, during, and after meaningful state changes. | Only a generic loading label appears. | The assistant stays silent for a long period and returns only `Done`. |
| C-VWT-2 | Operational trace fidelity | Grounding | Progress updates correspond to actual tool use, source checks, state changes, or explicit workflow boundaries. | Updates are plausible but vague. | The assistant claims progress that did not happen. |
| C-VWT-3 | Constraint preservation in progress | Intent / Navigation | The trace mentions important user constraints being preserved. | The trace shows activity but not scope. | The user cannot tell whether exclusions or boundaries were respected. |
| C-VWT-4 | Action receipt completeness | Agency | Final receipt states what changed, what did not change, failures, and recovery path if needed. | Final receipt says only that the task is done. | The system modifies external state without a reviewable receipt. |
| C-VWT-5 | No private-reasoning leakage | Grounding / Safety | The trace exposes workflow state, not hidden chain-of-thought. | The assistant mixes useful state with unnecessary internal explanation. | The system exposes sensitive internals or presents speculative reasoning as fact. |
| C-VWT-6 | Progress signal economy | Load | Updates are short and meaningful. | Updates are too frequent or repetitive. | Progress chatter becomes a second task for the user to parse. |

---

## Evaluation checklist

Use this checklist when reviewing a long-running AI interaction.

- Did the assistant acknowledge the task quickly enough?
- Did it preserve the user's important constraints visibly?
- Did it distinguish recommendation, draft, and execution?
- Did it expose tool use at a human level?
- Did it avoid fake chain-of-thought?
- Did it avoid raw implementation noise?
- Did intermediate updates correspond to real state transitions?
- Did the final receipt say what changed?
- Did the final receipt say what did not change?
- Did it give a recovery path for failures or partial completion?

---

## Design guidance

### Prefer operational verbs

Use verbs such as:

- checking;
- searching;
- reading;
- comparing;
- creating;
- updating;
- skipping;
- validating;
- summarizing;
- reporting.

### Prefer bounded scope

Good:

```text
I will update only the documentation files and leave the source code untouched.
```

Weak:

```text
I will work on it.
```

### Prefer meaningful state transitions

Good:

```text
Found the current framework file.
Next: adding the Visible Work Trace pattern and anti-patterns.
```

Weak:

```text
Still going.
```

### Prefer receipts over celebration

Good:

```text
Done: added the pattern, 3 anti-patterns, 6 criteria, and the evidence section.
Not changed: no source code files.
```

Weak:

```text
All set!
```

---

## Product implications

Visible Work Trace can be implemented through different surfaces:

| Surface | Example |
|---|---|
| Chat message | `Checked the repo. Next: creating the documentation patch.` |
| Inline status chip | `Reading calendar` → `Creating events` → `Summarizing changes` |
| Tool trace card | Human-readable tool event with input boundary and output summary. |
| Diff view | Files changed, lines added, lines removed, tests run. |
| Timeline | Step-by-step receipts for long agent workflows. |
| Notification | `Task still running: 3 of 8 files processed.` |

The best surface depends on task length, risk, product category, and user attention state.

---

## Conservative wording for the paper

Use:

> Research in HCI, service design, cognitive psychology, and Human-AI Interaction supports the claim that timely, meaningful progress feedback reduces uncertainty and helps users stay oriented during slow or multi-step interactions. In language-first AI systems, this suggests that long-running turns should expose concise operational state rather than remain silent.

Avoid:

> Humans always hate silence.

Avoid:

> Showing chain-of-thought is necessary for trust.

Better:

> Users do not need access to private reasoning to understand progress. They need visible workflow evidence: what is being checked, what changed, what was skipped, and what happens next.

---

## Limits and cautions

- Do not add artificial delay to seem human.
- Do not narrate every micro-step.
- Do not expose hidden chain-of-thought.
- Do not use progress text to cover up missing capability.
- Do not claim external state changed unless a tool result confirms it.
- Do not show raw logs unless the user is debugging.
- Do not assume one cadence fits all cultures, tasks, or users.
- Do not over-humanize the assistant; the goal is legibility, not impersonation.

---

## References

Amershi, S., Weld, D., Vorvoreanu, M., Fourney, A., Nushi, B., Collisson, P., Suh, J., Iqbal, S., Bennett, P. N., Inkpen, K., Teevan, J., Kikin-Gil, R., & Horvitz, E. (2019). *Guidelines for Human-AI Interaction*. CHI 2019. https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/

Buell, R. W., & Norton, M. I. (2017). The labor illusion: How operational transparency increases perceived value. *Management Science, 63*(6), 1673–1695. https://doi.org/10.1287/mnsc.2016.2464

Carleton, R. N. (2016). Fear of the unknown: One fear to rule them all? *Journal of Anxiety Disorders, 41*, 5–21. https://doi.org/10.1016/j.janxdis.2016.03.011

Clark, H. H. (1996). *Using language*. Cambridge University Press.

Clark, H. H., & Brennan, S. E. (1991). Grounding in communication. In L. B. Resnick, J. M. Levine, & S. D. Teasley (Eds.), *Perspectives on socially shared cognition* (pp. 127–149). American Psychological Association. https://doi.org/10.1037/10096-006

Cowan, N. (2001). The magical number 4 in short-term memory: A reconsideration of mental storage capacity. *Behavioral and Brain Sciences, 24*(1), 87–114. https://doi.org/10.1017/S0140525X01003922

Gao, Q., Dey, P., & Ahammad, P. (2017). Perceived performance of webpages in the wild: Insights from large-scale crowdsourcing of above-the-fold QoE. https://arxiv.org/abs/1704.01220

Grupe, D. W., & Nitschke, J. B. (2013). Uncertainty and anticipation in anxiety: An integrated neurobiological and psychological perspective. *Nature Reviews Neuroscience, 14*, 488–501. https://doi.org/10.1038/nrn3524

Harrison, C., Amento, B., Kuznetsov, S., & Bell, R. (2007). Rethinking the progress bar. *UIST '07*, 115–118. https://doi.org/10.1145/1294211.1294231

Harrison, C., Yeo, Z., & Hudson, S. E. (2010). Faster progress bars: Manipulating perceived duration with visual augmentations. *CHI '10*, 1545–1548. https://doi.org/10.1145/1753326.1753556

Hoff, K. A., & Bashir, M. (2015). Trust in automation: Integrating empirical evidence on factors that influence trust. *Human Factors, 57*(3), 407–434. https://doi.org/10.1177/0018720814547570

Kizilcec, R. F. (2016). How much information? Effects of transparency on trust in an algorithmic interface. *CHI '16*, 2390–2395. https://doi.org/10.1145/2858036.2858402

Lanham, T., Chen, A., Radhakrishnan, A., Steiner, B., Denison, C., Hernandez, D., Li, D., Durmus, E., Hubinger, E., Kernion, J., Lukošiūtė, K., Nguyen, K., Cheng, N., Schiefer, N., Rausch, O., Larson, R., McCandlish, S., Kundu, S., Kadavath, S., Yang, S., Henighan, T., Telleen-Lawton, T., Hume, T., Hatfield-Dodds, Z., Kaplan, J., Brauner, J., Bowman, S. R., & Perez, E. (2023). Measuring faithfulness in chain-of-thought reasoning. https://arxiv.org/abs/2307.13702

Lee, J. D., & See, K. A. (2004). Trust in automation: Designing for appropriate reliance. *Human Factors, 46*(1), 50–80. https://doi.org/10.1518/hfes.46.1.50_30392

Maister, D. H. (1985). The psychology of waiting lines. In J. A. Czepiel, M. R. Solomon, & C. F. Surprenant (Eds.), *The service encounter* (pp. 113–123). Lexington Books.

Miller, R. B. (1968). Response time in man-computer conversational transactions. *Proceedings of the AFIPS Fall Joint Computer Conference, 33*, 267–277. https://doi.org/10.1145/1476589.1476628

Myers, B. A. (1985). The importance of percent-done progress indicators for computer-human interfaces. *CHI '85*, 11–17. https://doi.org/10.1145/317456.317459

Nielsen, J. (1993). Response times: The 3 important limits. Nielsen Norman Group. https://www.nngroup.com/articles/response-times-3-important-limits/

Nielsen, J. (1994). 10 usability heuristics for user interface design. Nielsen Norman Group. https://www.nngroup.com/articles/ten-usability-heuristics/

Sherwin, K. (2014). Progress indicators make a slow system less insufferable. Nielsen Norman Group. https://www.nngroup.com/articles/progress-indicators/

Stivers, T., Enfield, N. J., Brown, P., Englert, C., Hayashi, M., Heinemann, T., Hoymann, G., Rossano, F., de Ruiter, J. P., Yoon, K.-E., & Levinson, S. C. (2009). Universals and cultural variation in turn-taking in conversation. *Proceedings of the National Academy of Sciences, 106*(26), 10587–10592. https://doi.org/10.1073/pnas.0903616106

Sweller, J. (1988). Cognitive load during problem solving: Effects on learning. *Cognitive Science, 12*(2), 257–285. https://doi.org/10.1016/0364-0213(88)90023-7

Turpin, M., Michael, J., Perez, E., & Bowman, S. R. (2023). Language models don't always say what they think: Unfaithful explanations in chain-of-thought prompting. https://arxiv.org/abs/2305.04388

Wang, Q., Kang, X., & Rau, P.-L. P. (2022). The magic of slow-to-fast and constant: Evaluating time perception of progress bars by Bayesian model. https://arxiv.org/abs/2211.13909
