# Discuss Math Research Ideas

`$discuss-math-research-ideas` acts as a mathematical research-seminar collaborator. It tests conjectures and proof ideas, looks for counterexamples and known results, extracts immediate consequences, and suggests a small number of promising next moves through a sustained dialogue.

## When to use it

Use this skill when you have an original conjecture, possible generalization, proof strategy, definition, example, or research direction that you want to explore interactively. It is designed for work in progress: the idea may be false, standard, incomplete, or genuinely promising.

The skill distinguishes what has been proved, what is known from verified literature, what is only recalled, and what remains speculative. It does not treat encouragement as evidence or lack of a search result as proof of novelty.

## Usage

Invoke the skill explicitly when desired:

```text
Use $discuss-math-research-ideas to think through this conjecture with me: ...
```

During the dialogue, you can propose examples, revise hypotheses, object to a claim, ask for a literature check, or say `OK` to continue. Each response normally makes one central research move and then pauses for your reaction.

## How ideas are handled

- A false claim receives an explicit counterexample and, when natural, a nearby repair.
- A short known argument is proved directly; a result requiring substantial machinery is explained briefly with verified source pointers.
- A viable-looking idea receives a provisional assessment, immediate consequences, and at most one or two routes worth trying next.
- An unclear idea is separated into established facts, heuristics, and the most informative next check.

Literature searches are targeted rather than automatic. They are used when known status, novelty, prior work, or exact bibliography matters.

## Language, notes, and export

Responses follow the language of the current user message and retain the latest substantive language for neutral control messages. The skill adapts its level to the mathematics demonstrated in the conversation.

On request, the skill summarizes the discussion directly in chat as a self-contained research note rather than a transcript. A chat note is written in the language of the summary request; if the request is language-neutral, it uses the language of the most recent substantive message. The note records established results, counterexamples, useful failed approaches and their failure mechanisms, literature connections, promising directions, and unresolved questions while omitting conversational noise.

TeX and PDF export is a separate, explicitly requested operation. If no destination was supplied, the skill asks where to save the files before creating them. TeX and PDF prose is always written in English, regardless of the dialogue language, and the PDF is compiled, rendered, and visually inspected before delivery.

## Limitations

- Counterexample checks and literature searches are necessarily bounded and are not proofs of completeness or novelty.
- Exact attributions are given only after verification; inaccessible or conflicting sources are reported as such.
- The skill intentionally avoids pursuing a difficult idea to a complete solution unless the user explicitly expands the scope.
- It is not intended for step-by-step learning of established mathematics, routine exercises, one-shot literature surveys, full formal proof verification, LaTeX debugging, or copyediting.

## Evaluation

Evaluation cases and the scoring rubric are in [`evals/discuss-math-research-ideas`](../../evals/discuss-math-research-ideas). The suite covers false, known, viable, and unclear ideas; corrections; language changes; research-note synthesis; export safety; and negative triggers.
