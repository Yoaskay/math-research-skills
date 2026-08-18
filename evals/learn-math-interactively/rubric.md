# Evaluation rubric

Score each dimension from 0 to 2.

- **0 — Failure:** Missing, materially incorrect, or contrary to the interaction contract.
- **1 — Partial:** Useful but inconsistent, weakly calibrated, or insufficiently disciplined.
- **2 — Strong:** Correct, adaptive, source-grounded when relevant, and fully compliant with the turn contract.

## Dimensions

1. **Target and level inference** — Identifies the intended mathematical goal and calibrates prerequisites from the dialogue without unnecessary intake questions.
2. **Mathematical fidelity** — Preserves definitions, hypotheses, quantifiers, conventions, and logical relationships.
3. **Unit selection** — Explains one coherent conceptual step with enough detail to be useful but stops before the next independent idea.
4. **Checkpoint discipline** — Ends at a natural boundary, invites questions or approval, and does not impose an unsolicited quiz.
5. **Turn precedence** — Gives corrections and questions priority over approval and never advances while an issue remains unresolved.
6. **Adaptive repair** — Changes representation after confusion and reconstructs prerequisites instead of merely paraphrasing.
7. **Correction integrity** — Verifies proposed corrections, repairs affected claims and route state, and removes superseded content.
8. **Language behavior** — Matches each substantive user message, preserves the last substantive language for neutral control turns, and switches when the user switches.
9. **Source fidelity** — Resolves exact source targets, distinguishes interpretation, cites only verified locations, and discloses missing or conflicting material.
10. **Synthesis and export** — Produces a self-contained user-language chat note and, only on request, asks for an output destination before creating accurate English TeX/PDF with completed visual QA.

## Passing criteria

- Require at least 16 of 20 points.
- Require a score of 2 for mathematical fidelity, unit selection, checkpoint discipline, and turn precedence.
- Fail automatically if a first teaching turn gives the planned comprehensive explanation instead of pausing after one unit.
- Fail automatically if the response advances the main route after a question, stated confusion, or unresolved correction.
- Fail automatically for inventing a theorem identity, source locator, proof, or attribution.
- Fail automatically if a known superseded claim appears in a summary or exported artifact.
- Fail automatically if any TeX or PDF file is created before the user confirms its destination.
- Fail automatically if TeX/PDF prose is not English or if an uncompiled or uninspected PDF is reported as complete.

## Review procedure

1. Evaluate the response as one turn in the supplied history, not as an isolated answer.
2. Mark the exact boundary between the current conceptual unit and material that should have waited.
3. Check mathematical claims and every source locator before scoring style or pedagogy.
4. Compare follow-up behavior with the precedence rule: correction, question, approval, then summary or export.
5. For summaries, verify self-containment and confirm that corrections are integrated rather than narrated chronologically.
6. For PDF cases, inspect the TeX language, compilation result, and rendered pages separately.
