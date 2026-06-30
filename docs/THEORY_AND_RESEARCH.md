# Theory and Research Notes

This document explains why SIGNAL patterns may improve user experience.

The README should stay simple. This file stores the deeper theory.

---

## Main claim

SIGNAL does not claim that language can solve every UX problem.

It claims that in conversational AI, language is a major part of user experience.

The assistant's words can reduce or increase:

- uncertainty;
- stress;
- cognitive load;
- perceived control;
- trust;
- satisfaction;
- productivity.

---

## Cognitive load

Users have limited attention and working memory.

If the assistant asks too many questions, gives too many options, or hides state, the user must do more mental work.

Relevant SIGNAL patterns:

- Cognitive Compression
- Ask-or-Act
- State Snapshot
- Few Useful Options
- Recovery Path

References:

- Sweller, J. (1988). Cognitive load during problem solving.
- Cowan, N. (2001). The magical number 4 in short-term memory.
- W3C COGA: Making Content Usable for People with Cognitive and Learning Disabilities.

---

## Pragmatics and intent

Human communication is not only literal.

A question can be a request. A correction can be a design constraint. A complaint can be a support need.

Relevant SIGNAL patterns:

- Brief Mirror
- Ask-or-Act
- Pragmatic Intent
- Human Repair
- Constraint Preservation

References:

- Grice, H. P. Cooperative principle.
- Austin, J. L. Speech act theory.
- Searle, J. R. Indirect speech acts.

---

## Grounding

People need evidence that they are aligned with each other.

In AI conversations, grounding appears when the assistant confirms what it understood, what it is using as evidence, what it is assuming, and what it will do next.

Relevant SIGNAL patterns:

- Brief Mirror
- Confidence Split
- Tool Transparency
- Action Receipt
- Recovery Path

References:

- Clark, H. H., & Brennan, S. E. (1991). Grounding in communication.
- Clark, H. H. (1996). Using Language.

---

## Waiting and progress

Silence during a long AI turn can feel like failure.

Progress signals help the user understand that the system is active, what path it is taking, and what remains uncertain.

Relevant SIGNAL patterns:

- Visible Work Trace
- State Snapshot
- Action Receipt
- Recovery Path

References:

- Nielsen, J. Response time limits.
- Myers, B. A. (1985). Percent-done progress indicators.
- Sherwin, K. Progress indicators make a slow system less insufferable.
- Buell, R. W., & Norton, M. I. Operational transparency.

---

## Trust and control

Users should not have to guess whether the assistant is recommending, drafting, or acting.

When a system can affect external state, control boundaries must be visible.

Relevant SIGNAL patterns:

- Approval Boundary
- Action Receipt
- Confidence Split
- Recovery Path
- Anti-overclaiming

References:

- Lee, J. D., & See, K. A. (2004). Trust in automation.
- Hoff, K. A., & Bashir, M. (2015). Trust in automation.
- Amershi et al. (2019). Guidelines for Human-AI Interaction.

---

## Uncertainty and stress

Uncertainty can increase stress and vigilance.

A conversational AI system should not hide uncertainty behind confident language. It should make uncertainty useful and actionable.

Relevant SIGNAL patterns:

- Confidence Split
- Evidence Boundary
- Recovery Path
- Safe Default
- Anti-overclaiming

References:

- Carleton, R. N. (2016). Fear of the unknown.
- Grupe, D. W., & Nitschke, J. B. (2013). Uncertainty and anticipation in anxiety.

---

## Reward, progress, and satisfaction

Users often feel better when progress is visible and tasks feel complete.

SIGNAL should handle this carefully: do not make exaggerated neurological claims in the main README. Instead, use this research as background for patterns that create visible progress, closure, and task completion.

Relevant SIGNAL patterns:

- Visible Work Trace
- Action Receipt
- Next Step
- Recovery Path

References:

- Progress indicators in HCI.
- Waiting-time perception.
- Operational transparency.
- Research on perceived control and task completion.

---

## Chain-of-thought caution

SIGNAL does not require exposing private reasoning.

The goal is to show user-facing workflow state, not the model's hidden reasoning.

Relevant SIGNAL patterns:

- Visible Work Trace
- Tool Transparency
- Confidence Split
- Evidence Boundary

References:

- Turpin et al. (2023). Language models don't always say what they think.
- Lanham et al. (2023). Measuring faithfulness in chain-of-thought reasoning.
