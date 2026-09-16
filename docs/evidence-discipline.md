# Evidence Discipline

## What every accepted result must record

An acceptance result is only credited when its evidence bundle records, at
minimum: the exact code/configuration revision under test; the exact fixture
or configuration identity used; which architectural role each component
played; confirmation that the working tree was clean immediately before the
official run; a machine-readable result; the actual observed behavior rather
than an expected value written down as if it had been observed; the full
failure and remediation history leading to that result; and any residual
limitation that still applies.

No result is accepted on documentation alone where observable runtime
behavior is what the criterion actually requires.

## Preserved failure as part of the record

When a run fails, its evidence is not deleted once a later run succeeds —
it is kept alongside the eventual passing run, with an explicit
classification of what went wrong: a defect in the test harness or fixture
itself, a defect in the implementation, a security defect, a defect in how
the evidence was gathered or interpreted, or a genuine failure to meet the
requirement. In practice, most failures across this project have resolved as
harness or fixture defects — missing setup steps, a query that filtered out
valid evidence, an environment-permission conflict — rather than as failures
of the underlying security or correctness property being tested. That
distinction is treated as something to demonstrate with evidence each time,
not to assume.

## Independent adjudication, not self-certification

The person or process that produced a result is never the same one that
certifies it as final. Every result starts as "executor result, pending
independent adjudication," and only a separate review — one that checks the
evidence bundle against the exact normative criterion text, not just against
a summary of it — can close it.

## Regression discipline without indiscriminate repetition

Each new round of testing is required to identify which previously-accepted
guarantees it could plausibly affect, and to re-run only that applicable
subset — rather than either re-running everything indiscriminately or
skipping regression checks altogether. A guarantee that is "preserved, not
re-run" in an intermediate report must still receive an explicit,
independently-reviewed judgment on whether that is materially sound before
the phase can be considered closed.

## Why this matters

This discipline exists to make a specific failure mode visible before it
becomes expensive: a plan that reads as rigorous on paper but whose
individual results were never actually checked against what they claim to
prove. Treating "the plan was accepted" and "the test passed" as two
separate, separately-evidenced facts — and never allowing the first to stand
in for the second — is the concrete mechanism that keeps that gap from
opening.
