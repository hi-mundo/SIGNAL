# SIGNAL: A LLM user experience framework

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![PR Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)](https://github.com/hi-mundo/SIGNAL/pulls)

<p align="center">
  <img src="docs/assets/signal-cover.svg" alt="SIGNAL: A UX framework for language-based AI systems" width="100%">
</p>

> A signal is a gesture, token, or action used to transmit information, communicate a command, or serve as a warning.

**SIGNAL is a UX framework for language-based AI systems.**

It helps teams design agents, bots, assistants, copilots, and AI products where conversation is the primary interface.

When conversation is the interface, communication is the product experience.

---

## Why SIGNAL

Users do not want to write perfect prompts.

They communicate like people: short messages, vague references, metaphors, idioms, incomplete context, frustration, shortcuts, corrections, and indirect requests.

LLMs are optimized to generate plausible continuations of language. Product experiences require more than plausible continuation: they require visible intent, grounding, progress, agency, cost, and value.

That gap is where UX matters.

SIGNAL designs the communication layer between messy human language and useful AI behavior.

---

## The framework

| Letter | Dimension | Product question |
|---|---|---|
| **S** | **Semantics** | Does the system create clear meaning? |
| **I** | **Intent** | Does it understand what the user means, not only what the user explicitly asked? |
| **G** | **Grounding** | Does it show what the answer or action is based on? |
| **N** | **Navigation** | Does it keep the user oriented through context, state, progress, and next steps? |
| **A** | **Agency** | Does it ask before taking technical actions, using profile data, storing preferences, changing state, or creating consequences for the user? |
| **L** | **Load** | Does it reduce mental load by summarizing complex facts, keeping context clear, preserving semantic consistency, and avoiding unsupported user decision burden? |

---

## Canonical Concept Map

SIGNAL uses product-facing names, but each dimension is grounded in established concepts from Human-AI Interaction, linguistics, cognitive psychology, information retrieval, and agent research.

| SIGNAL | Canonical concepts | Primary references |
|---|---|---|
| **Semantics** | [Plain language](https://www.iso.org/standard/78907.html), [pragmatics](https://en.wikipedia.org/wiki/Pragmatics), conversational maxims, semantic clarity | Grice 1975; [ISO 24495-1](https://www.iso.org/standard/78907.html); [W3C COGA](https://www.w3.org/TR/coga-usable/) |
| **Intent** | [Speech acts](https://en.wikipedia.org/wiki/Speech_act), indirect speech acts, intent recognition, [query rewriting](https://arxiv.org/abs/2408.17072) | Searle 1975; [LLM UX intent taxonomy](https://arxiv.org/abs/2401.08329); [MaFeRw](https://arxiv.org/abs/2408.17072) |
| **Grounding** | Groundedness, [retrieval-augmented generation](https://arxiv.org/abs/2005.11401), calibration, source attribution | [Lewis et al. 2020](https://arxiv.org/abs/2005.11401); [HELM](https://arxiv.org/abs/2211.09110); [Microsoft HAX](https://www.microsoft.com/en-us/haxtoolkit/library/) |
| **Navigation** | Visibility of system status, conversational grounding, progress feedback, state tracking | [Nielsen](https://www.nngroup.com/articles/response-times-3-important-limits/); Clark and Brennan 1991; [Myers 1985](https://doi.org/10.1145/317456.317459) |
| **Agency** | Human-AI control, oversight, approval gates, reversibility, correction | [Amershi et al. 2019](https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/); [Microsoft HAX](https://www.microsoft.com/en-us/haxtoolkit/library/); [NIST AI RMF](https://airc.nist.gov/airmf-resources/airmf/) |
| **Load** | [Cognitive load](https://doi.org/10.1016/0364-0213(88)90023-7), working memory, cognitive accessibility, progressive disclosure | [Sweller 1988](https://doi.org/10.1016/0364-0213(88)90023-7); [Cowan 2001](https://doi.org/10.1017/S0140525X01003922); [W3C COGA](https://www.w3.org/TR/coga-usable/) |

SIGNAL is not inventing these concepts from scratch. It organizes them into a practical framework for teams building AI experiences through language.

---

## Wall of Understanding

SIGNAL does not explain how an agent is implemented internally.

It explains how SIGNAL components sit on top of a common AI flow and turn user/context information into proactive behavior, visible value, and precise communication about what the user expects.

The implementation can use RAG, tools, memory, workflows, agents, MCP, databases, or only prompting. The UX responsibilities stay the same.

```mermaid
flowchart TB
    subgraph L["SIGNAL layer: Wall of Understanding"]
        direction LR
        S["S<br/>Semantics"] --- I["I<br/>Intent"] --- G["G<br/>Grounding"] --- N["N<br/>Navigation"] --- A["A<br/>Agency"] --- LD["L<br/>Load"]
    end

    subgraph F["Common AI flow"]
        direction LR
        U["User / Context"] --> UN["Understand"]
        UN --> R["Reason"]
        R --> AC["Act"]
        AC --> V["Validate"]
        V --> RP["Respond"]
        RP --> U
    end

    S -.-> UN
    I -.-> UN
    G -.-> R
    N -.-> R
    A -.-> AC
    G -.-> V
    A -.-> V
    N -.-> V
    LD -.-> RP
```

This is not an internal architecture diagram. It is a reusable allocation model.

SIGNAL shows what each part of a common AI loop must preserve for the user experience to work.

---

## Core idea

AI conversation UX is not only about producing an answer with cosmetic quality, concision, or explanation.

A good AI experience makes the AI context closer to what the user is trying to communicate and what the user actually needs.

It should understand:

- the current turn;
- what the system is doing actively and passively;
- what context helps answer the user;
- what the user is uncertain about;
- what the AI needs from the user;
- what may cost, risk, or create consequences for the user.

It should communicate:

- what changed;
- what value was delivered;
- what remains uncertain;
- what the user controls;
- what the AI can do next.

If the user says something that does not clearly connect to the last message, the system should not immediately ask "what do you mean?". It should first check whether the user is referring to something earlier in the conversation, something visible in the current environment, or something that just happened.

---

## How to apply SIGNAL

SIGNAL can be applied to any prompt engineering, agent, bot, assistant, workflow, or AI product by mapping its communication UX to a common AI loop.

The loop can change by architecture, but most AI experiences contain the same product-facing stages:

```mermaid
flowchart LR
    U["User / Context"] --> A["Understand"]
    A --> B["Reason"]
    B --> C["Act"]
    C --> D["Validate"]
    D --> E["Respond"]
    E --> U
```

SIGNAL defines what each stage must preserve.

| AI loop stage | SIGNAL responsibility | What belongs here |
|---|---|---|
| **Understand** | **Semantics + Intent** | Translate messy user language into clear meaning and likely goal. Handle vague references, metaphors, idioms, corrections, missing context, and indirect requests. |
| **Reason** | **Grounding + Navigation** | Decide what the answer or action should be based on, what evidence is available, what state matters, what remains uncertain, and what path should be followed. |
| **Act** | **Agency** | Use tools, memory, workflows, profile data, databases, or external systems only inside clear user-control boundaries. Ask before actions that create consequences. |
| **Validate** | **Grounding + Agency + Navigation** | Check whether the result is supported, whether the action stayed within scope, whether anything failed, and whether the user needs a recovery path or approval. |
| **Respond** | **Load** | Communicate the result with the lowest useful cognitive effort: clear summary, visible value, relevant evidence, next step, and no unnecessary reading or typing burden. |

This makes SIGNAL reusable across architectures.

It does not matter whether the system is only a prompt, a RAG assistant, a tool-using agent, an MCP workflow, a database-backed bot, or a multi-agent system.

The implementation may change. The UX responsibilities remain the same:

```text
Understand -> preserve meaning and intent.
Reason -> preserve evidence, uncertainty, and state.
Act -> preserve user control.
Validate -> preserve correctness, scope, and recovery.
Respond -> preserve clarity, value, and low effort.
```

Use it in five steps:

1. Map the product's AI behavior to the loop.
2. Assign SIGNAL responsibilities to each stage.
3. Choose patterns for the stages that are failing.
4. Define checks for prompts, tools, retrieval, memory, workflows, and responses.
5. Convert failures into product changes: better wording, better retrieval, clearer state, safer approval, lower user effort, or a stronger action boundary.

The output of a SIGNAL review should be concrete: rewritten responses, clearer action boundaries, better tool behavior, improved retrieval overlap, evaluation checks, and visible value receipts.

---

## Patterns

Each SIGNAL pattern is a reusable answer to a recurring AI UX problem.

```mermaid
flowchart TD
    P["User communication problem"] --> D["SIGNAL dimension"]
    D --> C["Canonical concept"]
    C --> R["Reference-backed principle"]
    R --> X["Reusable UX pattern"]
    X --> E["Evaluation criterion"]
```

Example:

| Problem | SIGNAL dimension | Pattern |
|---|---|---|
| User sends vague follow-up | Intent / Navigation | Context Recovery |
| AI may act externally | Agency | Action Boundary |
| Answer depends on uncertain evidence | Grounding | Confidence Split |
| Long task leaves user waiting | Navigation / Load | Visible Work Trace |
| User faces too many choices | Load | Few Useful Options |

---

## Start here

| File | Purpose |
|---|---|
| [`docs/FRAMEWORK.md`](docs/FRAMEWORK.md) | Full framework: pillars, criteria, patterns, anti-patterns, maturity model, and templates. |
| [`docs/RESEARCH_AND_BENCHMARKS.md`](docs/RESEARCH_AND_BENCHMARKS.md) | Research map, canonical concepts, adjacent frameworks, benchmark comparison, and references. |
| [`docs/PATTERNS.md`](docs/PATTERNS.md) | Practical patterns for conversation UX. |
| [`docs/WHY_SIGNAL.md`](docs/WHY_SIGNAL.md) | The thesis behind language-first AI UX. |
| [`docs/FOR_TEAMS.md`](docs/FOR_TEAMS.md) | How product, design, engineering, support, and eval teams can use SIGNAL. |
| [`templates/conversation_ux_review.md`](templates/conversation_ux_review.md) | Copyable review template. |

---

## What SIGNAL is not

SIGNAL is not:

- a model benchmark;
- a prompt engineering trick;
- an internal agent architecture;
- a replacement for product research;
- a leaderboard;
- a claim that one assistant is universally better than another.

SIGNAL is a communication UX layer for AI product experiences.

It helps teams ask:

> Did the AI understand what the user meant, act within the right boundaries, reduce user effort, and make the delivered value visible?
