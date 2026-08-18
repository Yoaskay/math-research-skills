# Math Research Skills

Reusable Codex skills for mathematical research workflows.

## Learn Math Interactively

`$learn-math-interactively` develops a serious understanding of a mathematical definition, theorem, proof, or theory through a paced dialogue. It explains one coherent conceptual unit, stops at a natural boundary, and waits for the user's question or explicit approval before continuing.

The skill supports direct mathematical questions as well as passages identified in PDFs, arXiv papers, TeX sources, and textbooks. It infers the user's background from the conversation instead of starting with a questionnaire, and revises both the explanation level and route when later questions expose missing prerequisites or misconceptions.

Invoke it explicitly when you want an interactive explanation:

```text
Use $learn-math-interactively to help me understand the implicit function theorem deeply. Pause at natural points so I can ask questions.
```

```text
$learn-math-interactively を使って、この論文の Theorem 2.3 を前提から対話的に理解したい。
```

At each pause:

- `OK`, `わかった`, `continue`, or an equivalent approval advances by one conceptual unit.
- A question is answered without advancing the main route; the skill then waits again.
- `まとめて` or an equivalent request produces a self-contained chat note in the language of that request.
- `PDFにして` or an equivalent request produces an English TeX source and PDF, regardless of the dialogue language. PDF export is never automatic.

Dialogue responses follow the language of the user message being answered. If the user switches languages, the skill switches with them. Chat summaries use the user's current language, while TeX and PDF prose is always English.

## Explain Math Proof Idea

`$explain-math-proof-idea` explains the decisive idea in the proof of one theorem, proposition, lemma, or corollary from a mathematical research paper. It is designed to sound like a focused five-to-ten-minute explanation from the author to another specialist.

The skill supports:

- an explicit target such as `Theorem 2.3`, `Proposition 4`, or a quoted statement;
- a semantic target such as “the main theorem of this paper”;
- PDF files, arXiv URLs, and TeX source;
- TeX-first proof tracing with PDF-based page and displayed-number verification;
- English by default, with the user's prompt language or explicit language request taking precedence.

It does not perform whole-paper summaries, full formal proof verification, LaTeX debugging, or copyediting.

## Use

Open this repository in Codex. The repository-scoped skills under `.agents/skills` are discovered automatically.

Invoke it explicitly when desired:

```text
Use $explain-math-proof-idea to explain the core proof idea of Theorem 2.3 in this paper.
```

```text
この論文の主定理の証明のコアアイデアを説明してください。
```

When several results are genuinely co-primary, the skill lists the candidates and asks you to select one before explaining a proof.

For personal installation after this repository is published, ask `$skill-installer` to install `.agents/skills/explain-math-proof-idea` from the GitHub repository URL. Codex can install skills from other repositories as described in the [official OpenAI documentation](https://learn.chatgpt.com/docs/build-skills).

### Local development installation

During local development, keep this repository as the source of truth and expose either or both skills globally with symbolic links rather than copying them. From the repository root, run:

```bash
mkdir -p "$HOME/.agents/skills"
ln -s \
  "$PWD/.agents/skills/explain-math-proof-idea" \
  "$HOME/.agents/skills/explain-math-proof-idea"
ln -s \
  "$PWD/.agents/skills/learn-math-interactively" \
  "$HOME/.agents/skills/learn-math-interactively"
```

The global entry is a symbolic link, not a second copy. Changes made in this repository are therefore visible through the global skill path. Verify the link and inspect its target with:

```bash
ls -l "$HOME/.agents/skills/explain-math-proof-idea"
readlink "$HOME/.agents/skills/explain-math-proof-idea"
ls -l "$HOME/.agents/skills/learn-math-interactively"
readlink "$HOME/.agents/skills/learn-math-interactively"
```

If the destination already exists, `ln` exits with an error instead of overwriting it.

## Source handling

The skill prefers TeX source from the same version for labels and proof dependencies, while using the PDF version the user is reading for displayed theorem numbers, pages, and equations. It reports version mismatches rather than silently combining sources.

Papers and TeX sources used for evaluation are downloaded temporarily and are not redistributed in this repository. The public evaluation suite stores only arXiv identifiers, prompts, synthetic fixtures, and expected behavior.

## Evaluate

Evaluation cases and scoring rubrics are in [`evals/explain-math-proof-idea`](evals/explain-math-proof-idea) and [`evals/learn-math-interactively`](evals/learn-math-interactively). The interactive suite covers pacing, question-first behavior, level and language adaptation, corrections, source fidelity, chat-note synthesis, English TeX/PDF export, and negative trigger cases.

Validate each skill structure with the `quick_validate.py` script bundled with OpenAI's `skill-creator`, passing the relevant directory under `.agents/skills` as the skill path.

## Known limitations

- Accurate page and displayed-number references require the PDF version the user is reading.
- TeX-first analysis requires source from the same version; otherwise the skill reports the mismatch.
- A proof delegated to an unavailable external reference can be explained only up to the reduction given in the supplied paper.
- When several results are co-primary, the skill requires the user to choose one before it continues.

## Contributing

Keep each change tied to a reproducible prompt. Update the relevant `SKILL.md`, add or revise a case under the matching `evals/<skill-name>` directory, run structural validation, and forward-test the changed behavior on raw source material. Do not commit downloaded papers or copied TeX sources; use public identifiers or minimal synthetic fixtures.

## License

MIT
