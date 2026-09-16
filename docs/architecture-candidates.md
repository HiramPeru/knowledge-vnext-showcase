# Architecture Candidates

## Problem framing

The system needs to let AI agents read and write persistent knowledge that
spans multiple sensitivity domains — public, organizational, and
personal-like data — without collapsing those domains into a single trust
boundary, while still allowing an agent to use permitted context from one
domain without silently replicating that domain's entire content elsewhere.

## Operating profile

Before comparing candidates, the project records an explicit operating
profile rather than assuming one: how much the system must tolerate being
offline, how much concurrent multi-agent/multi-device writing is expected
now versus in the near future, and how important independently verifiable
export/restitution is if it needs to remain operationally simple.

## Three materially distinct candidates

Three architecture families were defined precisely so that none could be
mistaken for a variant of another:

- **Federated, origin-enforced data** — canonical knowledge stays inside
  domain-owned stores, with enforcement anchored at the origin of each
  domain rather than in a separate coordinating layer.
- **Federated data with a shared knowledge control plane** — canonical
  knowledge remains domain-owned and federated, while a separate shared
  control plane supplies authorization, classification, lineage, audit,
  and revocation as first-class, independently recoverable state.
- **Service-centric canonical platform** — a single canonical service
  owns knowledge directly, favoring strong consistency and centralized
  enforcement over domain-local ownership.

No candidate was preferred at the point they were defined; the adversarial
audit gate exists specifically so that a favorite is not picked before the
evidence is in.

## Adversarial audit outcome

All three candidates survived the adversarial audit stage with required
mitigations attached; none was disqualified outright. Each carried distinct
follow-up obligations into the next gate — for the shared-control-plane
candidate, these centered on the integrity of that control-plane metadata
itself, on coherent recovery after loss, and on proving that a mixed-scope
query could not let unauthorized data influence ranking before an
authorization check ran.

## Falsification proof of concept

One candidate — federated data with a shared control plane — was selected as
the primary target for a falsification-style proof of concept: the explicit
rule going in was that a decisive, unmitigable failure would invalidate the
candidate outright, not just prompt a patch. The proof of concept exercised
composite recovery after simulated loss, mixed-scope retrieval with
authorization enforced before ranking, fail-closed behavior during a
policy-enforcement outage, tamper-evidence for governance metadata itself,
and governed device/browser context without trusting client self-reports.

The candidate survived without needing to change its defining architecture,
though several material failures were found and remediated along the way —
each preserved in the record rather than discarded. The other two candidates
remain retained: one as an operational fallback, the other as a long-term
challenger if the system's usage pattern shifts toward much higher
concurrency.

## What this stage does not decide

Surviving this stage establishes architecture-family plausibility, not
production readiness. It explicitly does not select a final technology
stack, and it does not authorize any production migration — that decision is
deferred to the acceptance-testing gate that follows.
