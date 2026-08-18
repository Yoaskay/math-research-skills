# Learn Math Interactively

`$learn-math-interactively` develops a serious understanding of a mathematical definition, theorem, proof, or theory through a paced dialogue. It explains one coherent conceptual unit at a time, stops at a natural boundary, and waits for the user's question or explicit approval before continuing.

## When to use it

Use this skill when you want to learn mathematics deeply and interactively rather than receive a one-shot answer. It supports direct mathematical questions as well as passages identified in PDFs, arXiv papers, TeX sources, and textbooks.

The skill infers the user's background from the conversation instead of starting with a questionnaire. It revises both the explanation level and the route when later questions expose missing prerequisites or misconceptions.

## Usage

Invoke the skill explicitly when desired:

```text
Use $learn-math-interactively to help me understand the implicit function theorem deeply.
```

You do not need to specify the pacing or ask the skill to pause; it does that automatically. You can also invoke `$learn-math-interactively` without a full prompt and provide the topic when asked, but naming the topic up front lets the lesson begin immediately.

At each pause:

- `OK`, `understood`, `continue`, or an equivalent approval advances by one conceptual unit.
- A question is answered without advancing the main route; the skill then waits again.
- A correction or suspected error takes precedence over progression and causes the affected mathematics to be rechecked.
- A summary or export request does not advance the lesson.

## Language and adaptation

Dialogue responses follow the language of the user message being answered. If the user switches languages, the skill switches with them. It adapts the level, examples, and route to the understanding demonstrated during the conversation.

When an explanation does not land, the skill changes representation by using an example, special case, counterexample, diagram, alternate formulation, calculation, or prerequisite reconstruction instead of merely repeating the same explanation.

## Summaries and export

A summary request produces a self-contained mathematical note rather than a transcript. Chat summaries use the language of the request, or the most recent substantive question when the request is language-neutral.

TeX and PDF export happens only when explicitly requested. If no destination was supplied, the skill asks where to save the files before creating them. Exported prose is always English, regardless of the dialogue language, and the TeX and PDF are rendered and visually checked before delivery.

## Limitations

- The workflow is intentionally paced and does not provide the whole route in every turn.
- It does not treat repeated approval messages as evidence of mastery beyond what the dialogue supports.
- Ambiguous theorem versions, conventions, or source passages may require one focused clarification before teaching begins.
- Proofs delegated to unavailable external sources are explained only to the extent supported by the supplied material.
- The skill is not intended for answer-only calculations, one-sentence definitions, one-shot summaries, full formal proof verification, LaTeX debugging, or copyediting.

## Evaluation

Evaluation cases and the scoring rubric are in [`evals/learn-math-interactively`](../../evals/learn-math-interactively). The suite covers pacing, question-first behavior, level and language adaptation, corrections, source fidelity, summary synthesis, English TeX/PDF export, and negative triggers.
