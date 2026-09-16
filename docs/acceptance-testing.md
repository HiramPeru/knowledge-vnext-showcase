# Acceptance Testing

## From residual risk to executable criteria

The proof-of-concept stage ends with a named list of residual risks — things
demonstrated only within a narrow synthetic scope, or not demonstrated at
all. The acceptance-testing gate exists to turn every one of those residuals
into an explicit, independently-adjudicated test, rather than treating "it
worked in the lab" as sufficient.

Representative residual classes carried forward include: whether semantic
contradiction detection generalizes beyond a narrow synthetic vocabulary;
whether an approximate (non-exact) retrieval path can remain safe without
letting unauthorized candidates influence ranking; whether governance
metadata integrity holds against more than same-host tampering; whether
recovery works off-host and independent of the original identity provider;
and whether realistic multi-agent concurrency preserves a single, auditable
outcome for every write.

## Bidirectional traceability

The acceptance baseline is built as a matrix in both directions: every
normative requirement maps to the specific tests that verify it, and every
test maps back to the requirements and residual risks it is meant to close.
This makes two failure modes visible immediately — a requirement with no
test covering it, and a test that does not trace to any accepted
requirement — rather than discovering either gap late.

## Baseline acceptance is not test evidence

A first draft of the acceptance plan was independently reviewed and returned
with required remediation before being accepted as the authoritative
baseline. Acceptance of that baseline is explicitly recorded as a distinct
event from any individual test passing — no test is ever credited as passed
merely because the plan describing it was accepted.

## Execution discipline

Rather than treating each criterion as its own isolated project, related
criteria that share fixtures or infrastructure are grouped into execution
campaigns — without reducing how many distinct criteria must independently
pass. One criterion in particular was identified as a strong candidate for
closure through documented equivalence with already-accepted evidence rather
than a brand-new run, but only after an independent reviewer — not the
person who ran the original test — confirmed that equivalence explicitly.

## Independent adjudication as a hard gate

Every executed result is recorded first as an executor's own finding,
explicitly marked "pending independent adjudication," never as an accepted
fact. A separate review checks the exact code revision under test, the exact
fixture used, whether required regressions were rerun, whether any failure
along the way was remediated within the original design or instead required
quietly loosening what was being tested, and whether every disclosed
limitation is compatible with a pass or requires being logged as an
explicit, still-open residual risk.

## Exit condition

Production implementation remains unauthorized until every mandatory
criterion has final, independently-adjudicated passing evidence, no
criterion remains unresolved, every residual risk carried in from the prior
gate has an explicit disposition, and a separate, explicit decision states
that implementation may proceed.
