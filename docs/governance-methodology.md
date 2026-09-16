# Governance Methodology

## Gate structure

The project advances through nine sequential gates. Each gate has an explicit
entry artifact, an explicit exit artifact, and a rule against skipping ahead:
no candidate architecture may be selected before the adversarial audit gate
closes, and no production implementation may begin before the acceptance
gate closes.

## Requirement vs. design decision

Every rule in the project is classified as one of two kinds:

- **Requirement** — a property the system must satisfy, established by
  requirements/research/audit and never weakened just to make a later test
  pass.
- **Design decision** — one concrete mechanism, technology, or threshold
  chosen to satisfy a requirement. A prototype's specific technology choices
  are treated as experiments, not as an automatic production selection,
  unless separately adjudicated.

Example pattern: a requirement might state that authorization must constrain
a result set before ranking or scoring occurs; the specific mechanism used to
enforce that (an exact filter, a partitioning strategy, or another approach)
is a design decision, evaluated on whether it preserves the same invariant,
not on which technology it happens to use.

## Adversarial-first review

At every gate transition, an independent reviewer is asked to find the
failure case, not to confirm the author's conclusion. Concretely:

- Candidate architectures are audited by a reviewer whose mandate is to try
  to break each one, with explicit instructions not to reward a candidate
  for using more familiar technology and not to penalize a candidate for
  leaving implementation specifics open.
- Findings are classified on a scale from "survives" through
  "survives with required mitigation," "unproven — requires proof of
  concept," "material gap," to "disqualifying" — with a clear distinction
  between an architecture-level flaw and a missing implementation detail.
- No executor may declare their own test result final. Every acceptance
  result is recorded as "executor result, pending independent adjudication"
  until a separate review confirms it.

## Preserved failure

Failed attempts are not deleted or silently replaced once a later attempt
succeeds. Each preserved failure records what was attempted, what broke, and
how it was classified — as a test/fixture defect, an implementation defect, a
security defect, an evidence-methodology defect, or a genuine requirement
failure. Only a small number of these classifications ever justify weakening
a requirement; most resolve through fixing the harness or the fixture, not
the rule being tested.

## Residual risk becomes an acceptance criterion

A proof of concept is not allowed to declare an open risk "solved" by
observing no failure within its own limited scope. Instead, every residual
limitation identified at the end of the proof-of-concept stage is carried
forward explicitly into the next gate as a named, independently-adjudicated
acceptance criterion — so the project's own record of what it does not yet
know keeps shrinking, rather than being quietly dropped.

## Status vocabulary

Only a small, closed set of outcomes is valid at any gate: pass; fail with a
possible remediation path; fail in a way that invalidates the candidate
itself; or inconclusive, pending further evidence. An inconclusive result is
never allowed to remain open at the point a phase is declared complete.
