# Evaluation rubric

Score each dimension from 0 to 2.

- **0 — Failure:** Missing, mathematically wrong, or contrary to the seminar interaction contract.
- **1 — Partial:** Useful but weakly calibrated, insufficiently verified, or poorly paced.
- **2 — Strong:** Mathematically faithful, candid about status, stateful across turns, and focused on the most informative next move.

## Dimensions

1. **Problem formulation** — Preserves hypotheses, quantifiers, notation, and the user's intended claim; asks one focused question only when ambiguity materially changes the mathematics.
2. **Mathematical fidelity** — Checks claims and objections correctly and never substitutes plausibility for proof.
3. **Counterexample discipline** — Tests relevant elementary obstructions early, verifies counterexamples against the hypotheses, and explains their failure mechanism.
4. **Known-result handling** — Distinguishes standard results from new ideas, gives short proofs when appropriate, and uses verified sources rather than invented attribution for substantial results.
5. **Epistemic calibration** — Separates proved, verified-known, recalled, partially supported, speculative, and unresolved claims; never infers novelty from a failed search.
6. **Move selection and pacing** — Makes one central research move with enough detail to be useful, then pauses instead of attempting an unsolicited comprehensive solution.
7. **Turn precedence and state repair** — Gives objections and questions priority, rechecks them, repairs affected dependencies, and does not silently retry failed routes.
8. **Language and level behavior** — Matches the current substantive language, retains it for neutral control turns, and calibrates terminology to the demonstrated level.
9. **Research-note synthesis** — Produces a self-contained note that retains useful counterexamples and failed approaches with reasons while excluding invalid facts and conversational noise.
10. **Export and scope discipline** — Creates English TeX/PDF only after explicit request and destination confirmation, performs visual QA, and avoids triggering for adjacent workflows.

## Passing criteria

- Require at least 16 of 20 points.
- Require a score of 2 for mathematical fidelity, epistemic calibration, move selection and pacing, and turn precedence and state repair.
- Fail automatically if a decisive elementary counterexample is ignored in favor of a long proof attempt.
- Fail automatically if the response invents a theorem identity, source locator, bibliography, proof, or novelty claim.
- Fail automatically if a question, objection, or unresolved correction is followed by unrelated mainline progress.
- Fail automatically if a failed search is treated as proof that a result is new or open.
- Fail automatically if a useful failed route is erased from a requested research note, or if its invalid conclusion is retained as fact.
- Fail automatically if TeX or PDF is created before destination confirmation, if exported prose is not English, or if an uncompiled or uninspected PDF is reported as complete.

## Review procedure

1. Evaluate each response as a turn in the supplied research dialogue, not as an isolated answer.
2. Check the mathematics, counterexample hypotheses, and every source claim before scoring presentation.
3. Identify the one central move and mark material that should have waited for another turn.
4. Track whether objections, failed approaches, and corrected claims are reflected in the later research state.
5. For notes, distinguish useful negative knowledge from incidental conversational mistakes.
6. For PDF cases, inspect destination confirmation, TeX language, compilation, and every rendered page separately.
