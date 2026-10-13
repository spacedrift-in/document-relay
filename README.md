# DocumentRelay

Raw OCR output is difficult to trust without validation, source evidence, and a human correction workflow.

**Status:** Product brief. No working application or performance claims yet.
Built as a Spacedrift portfolio demonstration for **finance operations, back-office teams, and document-heavy businesses**.

## Client demonstration

Upload a synthetic invoice → extract fields → validate totals → review uncertain values → export approved JSON or CSV.

Process clean and degraded synthetic invoices, correct an uncertain field, and demonstrate that invalid totals never pass silently.

Use synthetic data, identify the demonstration as a demo, and show failure recovery
alongside the happy path. The objective is a credible discovery conversation with a client.

## MVP scope

- PDF and image intake with type and size validation
- Structured invoice extraction with source page and region references
- Arithmetic, required-field, and duplicate checks
- Human review queue with correction history
- Versioned approved exports and retention controls

**Outside the first release:** Unreviewed accounting automation, all document types or languages, and claimed confidence calibration without evaluation.

## Proposed architecture

React, TypeScript, FastAPI, PostgreSQL, object storage; interchangeable OCR adapter.

Core entities: Document, ExtractionVersion, FieldEvidence, ValidationIssue, ReviewDecision, Export.

This stack is a starting recommendation, not an implemented system. The assigned developer
should document alternatives and finalize the architecture before adding dependencies.
Keep authorization server-side, validate inputs, and separate external integrations behind adapters.
Add AI only where its benefit can be measured; review uncertain outputs rather than hiding them.

## Delivery milestones

| Milestone | Required evidence |
| :--- | :--- |
| 1 · Definition | User flow, data model, API or storage contract, and agreed acceptance criteria |
| 2 · Vertical slice | One complete workflow on synthetic fixtures, with setup instructions |
| 3 · Reliability | Relevant failure recovery, access checks, and meaningful automated tests |
| 4 · Demonstration | Repeatable demo, screenshots, short walkthrough, and documented limitations |
| 5 · Handoff | Reproducible setup, deployment or build instructions, and maintenance notes |

The owner estimates effort after milestone 1. Do not promise a date before platform and integration risks are assessed.

## Acceptance criteria

- [ ] Invalid files are rejected before extraction.
- [ ] Each extracted field exposes its source evidence or is marked unsupported.
- [ ] Incorrect invoice arithmetic triggers review.
- [ ] Exported values match the approved extraction version.
- [ ] Repeated processing preserves history and does not duplicate approved records.
- [ ] Extraction quality is reported on a labeled held-out fixture set, with errors shown.
- [ ] A new developer can follow the documented setup on a clean environment.
- [ ] Secrets and private client information are absent from code, fixtures, logs, and screenshots.
- [ ] Loading, empty, error, and success states are implemented.
- [ ] Primary screens use black and white, readable contrast, and consistent spacing.
- [ ] The demo includes limitations and measured results rather than unsupported claims.

## Developer handoff

1. Assign a primary owner and a separate reviewer.
2. Open a planning issue linking this brief; resolve unknowns before implementation.
3. Record the architecture decision and create the smallest runnable vertical slice.
4. Replace the placeholder structure with the chosen platform structure.
5. Add actual setup commands only after verifying them; record required versions.
6. Deliver through focused pull requests with validation evidence.

No install, build, or deployment commands are provided yet because application code has not been implemented.
Android releases require an Android toolchain; iOS builds require macOS, Xcode, and appropriate signing.

## Quality and originality

Implement the product from this brief. Track third-party libraries and their licenses.
Attribute reused material and do not copy competitors’ interfaces, proprietary code, or private datasets.
Names are working titles; trademark and package availability have not been cleared.
Keep client names and case-study claims out of the demo unless authorized.

## Repository guide

- `docs/decisions/`: architecture decisions once made.
- `docs/demo.md`: repeatable client demonstration and limitations.
- `tests/fixtures/`: synthetic test inputs only.
- Platform application structure: to be created by the assigned developer.

## Contact and usage

[Spacedrift](https://spacedrift.in) · [Project enquiries](mailto:lourdu@spacedrift.in)

Copyright © 2026 Spacedrift. No open-source license is granted in this scaffold.
Select explicit license terms before inviting public code reuse.
