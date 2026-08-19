# Learn Unfamiliar Math Interactively

`$learn-unfamiliar-math-interactively` helps a mathematician enter an unfamiliar field without first reconstructing all of its prerequisites. It builds an accurate working map through a coarse-grained dialogue, with enough detail to read and use representative results while leaving appropriate proof machinery as explicit black boxes.

## When to use it

Use this skill when you have general mathematical training but little background in the target field and want to understand a theory, theorem, paper, note, or textbook passage at a practical overview level.

The skill is designed to answer questions such as:

- What problem is this theory organized around?
- Which ideas are essential, and which parts are proof technology?
- What are the inputs, hypotheses, and outputs of this theorem?
- How would I recognize a typical application?
- Which specialist concepts must I know, and which may remain black boxes?

Use `$learn-math-interactively` instead when the goal is deep prerequisite reconstruction, proof-level mastery, or line-by-line understanding.

## Usage

Invoke the skill explicitly when desired:

```text
Use $learn-unfamiliar-math-interactively to help me understand étale cohomology well enough to follow how it is used in this paper.
```

```text
I am a differential geometer with no background in derived categories. Use $learn-unfamiliar-math-interactively to give me a usable picture of this section.
```

The first teaching turn gives a selective map of the target and a short route through it. Later turns advance by broad milestones rather than pausing after every definition.

## Unfamiliar terminology

The skill assumes mathematical maturity but not field-specific vocabulary, examples, folklore, or proof techniques. When a concept is unlikely to be known outside the field, it explains the concept before relying on it instead of waiting for a question.

The explanation normally covers the concept's role, an intuition or canonical example, the minimum formal content needed now, and what can safely remain unknown. Long prerequisite theories receive a compact operational model and are marked as deferred rather than silently assumed.

## Essential, usable, and technical content

The dialogue distinguishes three roles relative to your goal:

- **Essential:** the idea that gives the theory or result its shape.
- **Needed for use:** definitions, hypotheses, conventions, inputs, outputs, and failure modes.
- **Technical:** machinery needed to prove the result but not to use or orient it at the requested level.

Technical does not merely mean difficult. If your goal changes, the classification changes with it.

## Checkpoints and revisiting gaps

At a checkpoint, `OK` means that the current picture is sufficient to continue; it does not claim that every detail has been mastered. Questions and corrections take priority over progression.

If you later realize that you accepted too much provisionally, say so. The skill locates the earliest missing dependency that explains the current obstacle and reconstructs that part without automatically restarting the whole route.

## Language, sources, summaries, and export

Dialogue responses follow the language of the current user message and switch when the user switches. For source-based requests, the skill resolves the exact version and passage, preserves hypotheses and notation, distinguishes source claims from interpretation, and cites only verified locations.

A summary request produces a self-contained note rather than a transcript. TeX and PDF export occurs only when explicitly requested and after the destination is confirmed. Exported prose is English, and the compiled PDF is rendered and visually inspected before delivery.

## Limitations

- The skill aims at accurate orientation and representative use, not complete technical mastery.
- It does not provide a one-shot whole-document summary or a comprehensive proof in the first turn.
- It may pause for one focused clarification when theorem versions, conventions, or goals materially differ.
- It does not handle routine calculations, one-sentence definitions, formal proof verification, LaTeX debugging, or copyediting.

## Evaluation

Evaluation cases and the scoring rubric are in [`evals/learn-unfamiliar-math-interactively`](../../evals/learn-unfamiliar-math-interactively). The suite covers proactive terminology explanation, opening maps, broad pacing, provisional approval, targeted rewinds, source fidelity, language behavior, summaries, and English TeX/PDF export.
