# Test-step convention

Compiled from the lesson "From Acceptance Criteria to Test Steps". Downstream stages parse this format — keep it exactly.

## The fixed template

```
Test Step [number]
  Source AC:        [AC tag(s) this step covers]
  Precondition:     [System state / user state required before action]
  Action:           [Precise user or system action]
  Expected Result:  [Observable, verifiable outcome]
```

## Four quality criteria

- ✅ **Complete** — every AC has at least one step.
- 🎯 **Precise** — two testers would set up the same state and do the same thing. Concrete test data, not "a valid user".
- ✔ **Testable** — the expected result can be observed; "works correctly" is not a result.
- 🔗 **Traceable** — every step has a Source AC. A step with none is noise, however sensible.

## Three failure modes to expect from an AI draft

1. Two ACs merged into one step with more than one independently failable outcome.
2. A generic precondition with no test data.
3. An invented step — reasonable, but traced to no AC.

## Open points

Where the card leaves a value or behaviour undefined, flag it inline: `[⚠ AMBIGUOUS: …]`. Never guess, never skip.
