# SIGNAL Profile: Cultural Pragmatics and Multilingual Interaction

## Domain

Multilingual and culturally variable LLM interactions, especially cases where users use indirect requests, idioms, sayings, abbreviations, slang, or non-literal language.

## Users

Users may be:

- multilingual;
- switching between languages;
- using cultural expressions;
- softening commands as questions;
- writing quickly or informally;
- relying on shared context;
- unwilling to repeat themselves formally.

## Domain risks

Poor handling of cultural pragmatics can cause:

- literal but unhelpful answers;
- unnecessary clarification loops;
- missed requests;
- cultural stereotyping;
- wrong intent inference;
- overconfident action based on weak context;
- increased user frustration.

## Required SIGNAL patterns

- Pragmatic Intent Bridge
- Capability Question as Soft Request
- Idiom and Expression Resolution
- Brief Mirror
- Assumption Labeling
- Action Boundary
- Safe Default

## Forbidden anti-patterns

- Literal Capability Answer
- Cultural Overfitting
- Idiom Flattening
- Helpful Fog
- Infinite Intern
- Hidden State

## Criteria weighting

| SIGNAL criterion | Weight | Reason |
|---|---:|---|
| C31 Pragmatic intent recognition | 2x | Core profile behavior. |
| C32 Indirect request handling | 2x | Users often soften requests as questions. |
| C33 Idiom and expression handling | 2x | Non-literal language is common in natural conversation. |
| C34 Cultural-context sensitivity | 2x | Cultural context must not become stereotyping. |
| C35 Defeasible inference | 2x | Pragmatic inference can be wrong and must be correctable. |
| C36 Capability-to-action conversion | 2x | Safe capability questions should move toward action. |

## Example bad response

```text
User: Can you access the Notion dashboard?
Assistant: It depends on the integration configuration.
```

## Example SIGNAL-style response

```text
I am treating this as a request to check what dashboard content is available to this integration.

I will only read; I will not modify anything.
```

If unavailable:

```text
I cannot access your Notion workspace from this chat right now.

To check it, I need the relevant Notion pages shared with the integration or the dashboard content pasted here.
```

## Escalation rules

Ask for confirmation before:

- sending messages;
- changing documents;
- deleting content;
- modifying records;
- making commitments;
- acting in medical, legal, financial, security, or public-service contexts.

## References

See [`../docs/CULTURAL_PRAGMATICS.md`](../docs/CULTURAL_PRAGMATICS.md).
