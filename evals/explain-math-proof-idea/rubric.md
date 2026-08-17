# Evaluation rubric

Score each dimension from 0 to 2.

- **0 — Failure:** Missing, materially incorrect, or unsupported.
- **1 — Partial:** Substantially useful but incomplete, imprecise, or weakly supported.
- **2 — Strong:** Correct, focused, source-grounded, and useful to a specialist.

## Dimensions

1. **Target resolution** — Identifies the intended formal result and handles numbering, restatements, and main-result ambiguity correctly.
2. **Statement fidelity** — Preserves material hypotheses, quantifiers, and conclusions.
3. **Proof architecture** — Gives a compact and accurate dependency flow rather than a section summary.
4. **Core-idea isolation** — Identifies the genuinely non-obvious move and separates it from technical completion.
5. **Mechanism and dependencies** — Explains why the move works and how essential lemmas and hypotheses enter.
6. **Source fidelity** — Distinguishes the paper's claims, imported results, later terminology, and the explainer's interpretation.
7. **Source pointers** — Gives accurate theorem, page, section, label, and equation locations without guessing.
8. **Expert usefulness** — Delivers enough mathematical detail for a specialist to reconstruct the strategy in roughly five to ten minutes.

## Passing criteria

- Require at least 13 of 16 points.
- Require a score of 2 for target resolution and statement fidelity.
- Fail automatically if the response invents a proof, source locator, theorem identity, or attribution.
- For a main-theorem request with multiple co-primary results, pass only if the response asks the user to choose before explaining a proof.
- Apply the language rule separately: explicit request, then prompt language, then English.

## Review procedure

1. Compare the response with the exact paper version and all cited proof dependencies.
2. Mark every unsupported locator or attribution before assigning scores.
3. Ask a domain expert whether the stated core idea is the move they would emphasize in a short author-to-expert explanation.
4. Save only the prompt, scores, concise corrections, and public source identifier. Do not commit copyrighted paper content.
