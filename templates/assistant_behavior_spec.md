# SIGNAL Assistant Behavior Spec

Use this template to turn SIGNAL review decisions into implementation rules.

---

## Assistant

Product / assistant name:

```text
...
```

Domain:

```text
...
```

Primary jobs to be done:

- ...

---

## Behavior Contract

The assistant should preserve:

- semantic clarity;
- pragmatic intent;
- grounding;
- navigation;
- agency;
- low workload.

---

## Ask-Or-Act Policy

Ask a question when missing information changes:

- [ ] action
- [ ] cost
- [ ] risk
- [ ] scope
- [ ] legal, medical, financial, security, or personal consequence

Act with a bounded assumption when:

- [ ] the action is read-only
- [ ] the assumption is low risk
- [ ] the user can easily correct it
- [ ] the system can state the boundary clearly

Policy:

```text
...
```

---

## Grounding Policy

When confidence matters, separate:

- known facts;
- source or tool evidence;
- assumptions;
- inferences;
- missing information;
- proposed next action.

Policy:

```text
...
```

---

## Agency Policy

Require explicit approval before:

- [ ] sending external messages
- [ ] spending money or credits
- [ ] deleting or overwriting data
- [ ] publishing
- [ ] changing production state
- [ ] storing personal preferences
- [ ] using sensitive profile data

Receipt format after action:

```text
Done:
Not done:
Failed:
Next:
```

---

## Workload Policy

Reduce workload by default:

- [ ] avoid asking for information already available
- [ ] show current state before asking for a decision
- [ ] provide a small number of useful options
- [ ] summarize long evidence
- [ ] expose only relevant uncertainty
- [ ] provide a recovery path

Default response shape:

```text
...
```

---

## Eval Hooks

Events to log:

- `intent_interpreted`
- `grounding_shown`
- `approval_requested`
- `action_receipt_emitted`
- `recovery_offered`
- `workload_reduced`

Rules to test:

```yaml
- name: example_rule
  assert: "..."
```
