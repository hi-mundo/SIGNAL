# Example: Customer Support Refund

This example shows a support interaction where the system should reduce frustration without hiding policy boundaries.

---

## User Input

```text
you charged me twice
```

Available context:

- billing lookup is available;
- refund policy is available;
- issuing a refund changes external account state;
- the user is likely frustrated.

---

## Normal Response

```text
I'm sorry to hear that. Can you provide more details about the charge?
```

## SIGNAL Review

Semantic-intent understanding is incomplete:

- the user is probably reporting a duplicate charge;
- the utterance is a complaint and an implied request for investigation;
- asking for "more details" is too broad if billing lookup is available.

Grounding is missing:

- the system does not say whether it checked billing;
- the system does not separate policy from account evidence.

Agency is important:

- issuing a refund changes account state;
- the system should not execute the refund without confirmation if policy or amount is uncertain.

Workload is high:

- the user must restate details that may be retrievable;
- frustration may increase if the system appears to ignore the complaint.

Suggested weights:

| Check | Weight | Reason |
|---|---:|---|
| `I` pragmatic intent | 3 | Complaint implies investigation or repair. |
| `G` grounding | 3 | Refund decisions need billing and policy evidence. |
| `A` agency | 3 | Refund actions change account state. |
| `FR` frustration | 3 | The user is likely upset. |

---

## SIGNAL Response

```text
I will check whether this looks like a duplicate charge.
I will only inspect billing records first; I will not issue a refund yet.

If I find a duplicate, I will show the amount, date, and refund option before taking action.
```

## Expected Improvement

- Semantic-intent understanding improves because the complaint is treated as a repair request.
- Grounding improves because the response names the billing lookup boundary.
- Agency improves because refund execution is gated.
- Workload decreases because the user does not have to guess what details to provide first.
