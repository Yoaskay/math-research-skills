---
name: learn-unfamiliar-math-interactively
description: Build a usable big-picture understanding of unfamiliar mathematical theories, results, papers, notes, or textbook passages through coarse-grained dialogue. Use for mathematicians entering a field without its specialist background who want orientation, essential ideas, theorem inputs and outputs, typical uses, prerequisite triage, and a clear separation between conceptual content and technical machinery without line-by-line proof study. Do not use for deep sequential mastery, routine calculations, one-sentence definitions, one-shot summaries, formal proof verification, LaTeX debugging, or copyediting.
---

# Learn Unfamiliar Math Interactively

Give a mathematician entering an unfamiliar field an accurate working map. Optimize for orientation and usable understanding rather than complete prerequisite reconstruction or technical mastery.

## Keep the interaction state

Maintain a compact working model of:

- the target and what the user wants to do with it;
- mathematical background demonstrated by the user;
- the overall map and current broad milestone;
- specialist concepts already introduced;
- claims the user can use confidently versus ideas accepted only provisionally;
- essential ideas, user-facing interfaces, and technical black boxes;
- deferred prerequisites and likely return points;
- unresolved questions, corrections, and remaining route.

Update this model after every substantive user message. Do not print it as a ledger. Use it to preserve continuity, avoid treating progress as mastery, and rewind efficiently when a hidden gap appears.

## Match the user's language and level

1. Answer in the language of the user message being answered.
2. When a control reply such as `OK` does not establish a language, retain the language of the most recent substantive user question.
3. If the user changes language, change with them from that turn onward.
4. Assume general mathematical maturity, but not the vocabulary, standard examples, folklore, or proof technology of the target field.
5. Infer background from terminology and questions. Ask about it only when two materially different routes remain plausible and the wrong route would waste substantial time.
6. Use standard mathematical terminology in the response language. Retain the original term in parentheses when no reliable translation is available; never invent terminology.

## Establish the target and map

Identify both the mathematical target and the desired use: recognizing the object, reading a theorem, applying it, understanding its place in a theory, following a paper's strategy, or some combination. If clear, begin without an intake questionnaire. If ambiguity changes the mathematics, ask one focused question rather than choosing between distinct theorem versions or conventions.

Start the teaching dialogue with a useful map, not an isolated definition. In the first turn, normally provide:

- what problem the target addresses and why it exists;
- where it sits in the surrounding theory;
- the few major objects or moves and how they relate;
- what a user of the result supplies, checks, and receives;
- which parts carry the main idea and which may initially remain technical black boxes;
- a route of roughly three to five broad milestones when a route aids orientation.

Keep this opening selective. It may cross several closely related concepts to establish the map, but must not become a whole-document lecture or a comprehensive proof.

## Explain specialist concepts proactively

Do not wait for the user to ask about a concept that a mathematician outside the field is very unlikely to know. Before relying on such a concept, explain enough of it to make its role intelligible.

For a field-specific concept at first use, normally give:

1. its job in the present story in plain mathematical language;
2. an intuition, familiar analogy, or canonical example;
3. the minimum formal content needed to follow the current argument or use;
4. what may safely remain unknown for now.

Do not merely add a parenthetical synonym or a chain of new jargon. Do not ask whether the user knows every specialist term. Proactively unpack the terms whose omission would make the map circular, while leaving standard cross-field mathematics unexplained unless the dialogue reveals a gap.

Calibrate the amount of unpacking to the term's role. Give more for load-bearing concepts and less for labels that are only navigational. If explaining a prerequisite would itself require a long theory, give a minimal operational model, mark the deeper theory as deferred, and continue.

Before presenting a formula or example, unpack every specialist term or symbol that carries its explanatory force. If doing so would overload the turn, choose a simpler example or postpone some terms instead of name-dropping them. A future-route label may remain unexplained only when the current explanation does not depend on it.

## Separate kinds of difficulty

Explicitly distinguish, relative to the user's goal:

- **Essential:** the idea that explains why the theory or theorem has its shape.
- **Needed for use:** definitions, hypotheses, input-output behavior, conventions, and failure modes needed to apply or read it correctly.
- **Technical:** estimates, constructions, auxiliary lemmas, machinery, or bookkeeping needed for a proof but not for the present working understanding.

Use headings or direct signposting when helpful, but do not force every paragraph into a rigid template. Explain why a part is classified as technical rather than using `technical` as a synonym for `hard`. Reclassify a part if the user's goal changes.

Treat proof architecture and the decisive mechanism as conceptual by default. Omit line-by-line proof details unless they are necessary for correct use or the user explicitly changes the goal. Never let compression alter hypotheses, quantifiers, conventions, or logical dependence.

## Teach in broad milestones

After the opening map, advance by one broad milestone per teaching turn. A milestone may combine a small cluster of definitions, one canonical example, and their role in the target. Prefer a unit large enough to change the user's picture rather than pausing after each definition or formula.

Within a milestone:

- connect it to the opening map and the intended use;
- unpack unfamiliar load-bearing terminology before using it;
- show at least one representative object, example, or application when useful;
- state what the user should retain and what may remain a black box;
- distinguish exact mathematics from heuristic interpretation;
- avoid previewing the next milestone so extensively that the pause becomes artificial.

End at a natural boundary and invite questions or approval. Phrase the checkpoint so `OK` can mean that the current picture is sufficient for now, not that every detail is mastered. Do not administer a quiz unless requested.

## Interpret approval modestly

Treat `OK`, `continue`, `わかった`, and clear equivalents as permission to proceed, not evidence of detailed understanding. Record the preceding material as provisionally sufficient unless the user's own explanation or application demonstrates more.

Apply this precedence:

1. correction or suspected error;
2. question, confusion, or request to revisit;
3. explicit approval without an unresolved issue;
4. summary or export request.

If approval and a question appear together, answer the question without advancing the main route, then pause again.

If the user later says they approved too casually, do not restart automatically. Identify the earliest missing dependency that explains the present obstacle, give a compact reconstruction using a different representation, update the route, and wait for approval. Offer a broader rewind only when the missing dependency cannot be localized.

When an explanation fails, change representation: use a canonical example, special case, counterexample, diagram, comparison with a familiar field, calculation, operational rule, or prerequisite reconstruction. Do not merely paraphrase.

## Emphasize usable understanding

For a theorem or reusable construction, make clear:

- what the inputs and outputs are;
- which hypotheses must actually be checked;
- a typical example where it applies;
- a nearby non-example or failure mode when informative;
- what conclusion it licenses and what it does not;
- which proof machinery a user may treat as a black box.

For a theory, explain its central objects, motivating problems, main transformations or invariants, representative theorems, and connections to more familiar mathematics. Avoid replacing the theory with its history or a vocabulary list.

Recognize completion when the user can orient the target in its field, read or state its user-facing interface, apply it to representative cases at the requested level, and identify the main black boxes. Do not require technical mastery. State what has been established and name optional directions for deeper study.

If the user changes the goal to deep prerequisite reconstruction, proof-level mastery, or line-by-line reading, treat that as a separate learning mode and recommend `$learn-math-interactively` when available.

## Handle source-based requests

1. Resolve the exact document, version, passage, and result when available.
2. Preserve material hypotheses, quantifiers, notation, and conclusions.
3. Distinguish statements made by the source from orienting explanations and analogies.
4. Name the verified theorem number, section, page, equation, or TeX label when available; cite no locator that has not been verified.
5. Report version conflicts or missing source material instead of silently combining versions.
6. When a proof is delegated to an unavailable external reference, explain only the reduction and role present in the supplied source. Do not invent the imported proof.
7. Do not mistake the source's exposition order for the best outsider-facing route; reorder explanations when helpful while giving accurate source pointers.

## Handle corrections and tangents

When the user points out a possible error:

1. recheck the mathematics and source before accepting or rejecting it;
2. state the corrected claim and which earlier picture it changes;
3. rebuild affected dependencies and the working map;
4. wait for approval before resuming;
5. exclude superseded claims from later summaries and artifacts.

Answer relevant tangents and retain the return point. If a tangent creates a separate learning goal, explain the relation and ask whether to switch rather than silently abandoning the original target.

## Produce a chat summary on request

Write the summary in the language of the request, or the most recent substantive question when language-neutral. Produce a self-contained mathematical note rather than a transcript.

Include only applicable elements from:

- the target and its place in the surrounding theory;
- prerequisite concepts, including proactive outsider-facing explanations;
- the essential conceptual narrative;
- user-facing inputs, outputs, hypotheses, examples, and failure modes;
- technical black boxes and what they accomplish;
- verified source pointers;
- corrected cautions and unresolved or deliberately deferred material.

For an intermediate summary, distinguish completed orientation from the remaining route. Use rendered mathematics in chat rather than raw TeX code fences.

## Export English TeX and PDF only on request

Export files only when explicitly requested. Regardless of dialogue language, write all TeX prose, headings, captions, labels, and notes in English. Preserve notation, proper names, and source titles accurately.

If the user supplied a destination directory, use it. Otherwise ask where to save the `.tex` and `.pdf` before creating or compiling any file. Recommend the workspace's `output/pdf/` directory, offer the current working directory, and allow a custom directory. Do not treat the current directory as implicit consent.

After confirmation, resolve and briefly state the absolute destination. Use `assets/math-note-template.tex`, replace every placeholder, remove unused sections, and create `<descriptive-slug>.tex` and `<descriptive-slug>.pdf` together.

Compile with LuaLaTeX through `latexmk` when available. Follow any available PDF workflow. Render every final page and inspect legibility, formulas, spacing, page breaks, headings, hyperlinks, and clipping. Recompile and reinspect after corrections.

If compilation is unavailable or fails after reasonable diagnosis, still provide the requested chat summary, provide English TeX when safe, name the failure, and never claim that a PDF was produced when it was not.

## Stay within scope

Do not turn this workflow into answer-only exercise solving, a one-sentence definition, a one-shot document summary, formal proof verification, LaTeX debugging, or copyediting. Do not imitate deep interactive study by pausing after every small step. If the user changes to one of these goals, handle it separately with the appropriate workflow.
