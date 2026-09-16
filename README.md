# Knowledge vNext — Gated Architecture Design Showcase

Knowledge vNext is a sanitized public portfolio repository documenting a
gated, independently-audited process for selecting and acceptance-testing a
persistent knowledge architecture for AI agents, before any production
implementation is authorized.

This repository is intended to demonstrate technical judgment in requirements
discipline, adversarial architecture review, falsification-driven proof of
concept, and acceptance-test governance. It does not publish the private
implementation, evidence bundles, or any production domain data.

## Executive Summary

The project evaluates how AI agents should read and write persistent,
governed knowledge across multiple sensitivity domains (public, organizational,
and personal-like data) without collapsing them into a single trust boundary.
Rather than selecting a technology stack directly, the project runs a
nine-gate process — requirements, research, candidate architectures,
adversarial audit, falsification proof of concept, and staged acceptance
testing — where every advance requires independent, adversarial review before
the next gate opens.

## Repository Purpose

This public repository exists to:

- present a professional, sanitized methodology showcase;
- document the gate structure and governance rules at a high level;
- describe how architecture candidates were adversarially audited and how one
  was falsification-tested before being preferred;
- describe how acceptance-test criteria are derived from residual risk and
  independently adjudicated; and
- do this without exposing the private domain, real evidence bundles, or
  internal implementation assets.

## Public Scope Notice

This is a sanitized public portfolio repository. It does not include the
private implementation repository, real evidence bundles, CI run logs,
production or client domain data, credentials, or internal-only delivery
assets. All examples below are described at the level of methodology and
requirement class, not literal reproduced content.

## Methodology Overview

The project runs through nine gates, each with explicit entry/exit criteria
and an independent audit before the next gate may open:

| Gate | Purpose |
|---|---|
| F0 | Requirements baseline |
| F1 | Research |
| F2 | Research consolidation (independently audited) |
| F3 | Candidate architectures — multiple, materially distinct, no preference yet |
| F4 | Adversarial audit — try to break each candidate, not select a favorite |
| F5 | Falsification proof of concept — a decisive, unmitigable failure invalidates the candidate |
| F6 | Acceptance testing — convert every residual risk into an executable, independently-adjudicated criterion |
| F7 | Production implementation — gated on a separate, explicit exit decision |

No gate is treated as passed by documentation alone where observable
behavior is required, and no reviewer may adjudicate their own evidence.

## Key Governance Principles

- **Requirement vs. design decision.** A requirement is a property the system
  must satisfy; a design decision is one concrete way to satisfy it. Passing
  a test can never be achieved by weakening the requirement — only by meeting
  it, or by an independently-adjudicated architecture-level failure.
- **Adversarial-first, not self-graded.** Every gate transition requires an
  independent reviewer whose role is to find the failure case, not to confirm
  the author's conclusion.
- **Preserved failure, not just success.** Failed attempts and their
  remediation are kept as part of the evidence record instead of being
  overwritten by the eventual passing run.
- **Residual risk becomes an acceptance criterion.** A proof-of-concept
  cannot declare a risk solved; every residual limitation from the PoC stage
  is carried forward as an explicit, testable acceptance criterion in the
  next gate.

See [Governance Methodology](docs/governance-methodology.md) for the full
rule set.

## Architecture Selection Summary

Three materially distinct architecture families were evaluated and
adversarially audited before one was selected as the falsification-testing
candidate, with the other two retained as fallback and long-term challenger.
See [Architecture Candidates](docs/architecture-candidates.md).

## Acceptance Testing Summary

The selected architecture entered a staged acceptance-testing phase built
from an explicit bidirectional traceability matrix — every normative
requirement maps to the tests that verify it, and every test maps back to
the requirements and residual risks it closes. See
[Acceptance Testing](docs/acceptance-testing.md).

## Evidence Discipline Summary

Every accepted test result records the exact code/config revision under
test, the exact fixture identity, a clean working-tree precondition, and
observed (not expected-and-assumed) behavior — with failed attempts and
their remediation preserved rather than discarded. See
[Evidence Discipline](docs/evidence-discipline.md).

## My Role / Contribution

I designed and operate this gated process end to end: defining the
requirement baseline, running the adversarial audits and the falsification
proof of concept, writing the acceptance-test plan and its traceability
matrix, and coordinating independent adjudication at every gate transition.

## Evidence / Outcomes

- Three candidate architectures survived adversarial audit with required
  mitigations; none was disqualified outright.
- One candidate survived a falsification proof of concept designed to
  invalidate it, with every material failure preserved and remediated rather
  than hidden.
- A 25-criterion acceptance-test baseline was independently audited and
  accepted before any test execution began, closing the gap between
  "we wrote a plan" and "the plan passed review."
- Acceptance-test execution is in progress under independent adjudication;
  general production implementation remains unauthorized until every
  criterion and every residual risk is explicitly closed.

No production deployment, data migration, or business-outcome claim is made
by this repository.

## Documentation Index

- [Governance Methodology](docs/governance-methodology.md)
- [Architecture Candidates](docs/architecture-candidates.md)
- [Acceptance Testing](docs/acceptance-testing.md)
- [Evidence Discipline](docs/evidence-discipline.md)
- [Gate Flow Diagram](diagrams/gate-flow.mmd)

## Repository Boundary

This repository is a sanitized public showcase only. It does not include the
private implementation repository, real test evidence, CI logs, production
or client domain data, credentials, or internal-only delivery assets.
