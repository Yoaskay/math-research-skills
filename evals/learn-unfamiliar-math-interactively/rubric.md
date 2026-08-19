# Evaluation rubric

Score each dimension from 0 to 2.

- **0 — Failure:** Missing, materially incorrect, or contrary to the interaction contract.
- **1 — Partial:** Useful but inconsistent, weakly calibrated, or insufficiently explicit.
- **2 — Strong:** Accurate, outsider-aware, practically useful, and fully compliant with the dialogue state.

## Dimensions

1. **Target and use calibration** — Identifies what the user wants to understand or do and assumes mathematical maturity without assuming field expertise.
2. **Opening map** — Gives a selective account of motivation, position, principal objects or moves, user-facing interface, black boxes, and broad route before local detail.
3. **Proactive concept unpacking** — Explains field-specific load-bearing concepts before relying on them, including notation that carries an example or formula, using role, intuition or example, minimum formal content, and an explicit deferral boundary.
4. **Mathematical fidelity** — Preserves hypotheses, quantifiers, conventions, conclusions, and logical relationships despite compression.
5. **Difficulty separation** — Distinguishes essential, needed-for-use, and technical material relative to the user's goal and explains what technical machinery accomplishes.
6. **Broad milestone pacing** — Advances by coherent clusters that materially change the user's picture without either atomizing the lesson or dumping the whole route.
7. **Practical usability** — Explains inputs, outputs, hypotheses to check, representative examples, failure modes, and the limits of what a theorem or construction licenses.
8. **Approval and turn precedence** — Treats `OK` as provisional permission, prioritizes corrections and questions, and never infers mastery merely from repeated approval.
9. **Adaptive rewind and correction integrity** — Localizes later-revealed gaps, changes representation, repairs dependent state, and excludes superseded claims without unnecessary restart.
10. **Language, source, synthesis, and export** — Follows language changes, verifies source locations and versions, produces self-contained summaries, and obeys destination, English-export, compilation, and visual-QA requirements.

## Passing criteria

- Require at least 17 of 20 points.
- Require a score of 2 for proactive concept unpacking, mathematical fidelity, broad milestone pacing, and approval and turn precedence.
- Fail automatically if the first teaching turn relies on a field-specific load-bearing concept without explaining it enough for an outsider to understand its role.
- Fail automatically if a formula or example derives its explanatory force from unexplained specialist notation that could have been unpacked, simplified, or postponed.
- Fail automatically if the first teaching turn gives either a definition-sized fragment with no map or a comprehensive lecture/proof with no meaningful pause.
- Fail automatically if repeated `OK` messages are treated as evidence of mastery.
- Fail automatically if the response advances while a question, correction, or identified prerequisite gap remains unresolved.
- Fail automatically if compression changes a material hypothesis or invents a theorem identity, source locator, proof, or attribution.
- Fail automatically if a superseded claim appears in a later summary or artifact.
- Fail automatically if TeX or PDF is created before destination confirmation, if export prose is not English, or if an uncompiled or uninspected PDF is reported as complete.

## Review procedure

1. Identify every target-field term used before it is explained and decide whether a mathematician outside the field could reasonably know it.
2. Check that proactive explanations give an operational role rather than only synonyms or additional jargon.
3. Mark the opening map and the boundary of each broad milestone; reject both definition-by-definition pacing and one-turn comprehensiveness.
4. Verify theorem interfaces, hypotheses, examples, and every source locator against the exact source version.
5. Audit dialogue state after `OK`, questions, corrections, and rewinds; do not award mastery that the user has not demonstrated.
6. For summaries, check self-containment and correction integration. For PDF cases, inspect destination confirmation, TeX language, compilation, and rendered pages separately.
