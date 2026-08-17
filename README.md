# Math Research Skills

Reusable Codex skills for mathematical research workflows.

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

Open this repository in Codex. The repository-scoped skill under `.agents/skills` is discovered automatically.

Invoke it explicitly when desired:

```text
Use $explain-math-proof-idea to explain the core proof idea of Theorem 2.3 in this paper.
```

```text
この論文の主定理の証明のコアアイデアを説明してください。
```

When several results are genuinely co-primary, the skill lists the candidates and asks you to select one before explaining a proof.

For personal installation after this repository is published, ask `$skill-installer` to install `.agents/skills/explain-math-proof-idea` from the GitHub repository URL. Codex can install skills from other repositories as described in the [official OpenAI documentation](https://learn.chatgpt.com/docs/build-skills).

## Source handling

The skill prefers TeX source from the same version for labels and proof dependencies, while using the PDF version the user is reading for displayed theorem numbers, pages, and equations. It reports version mismatches rather than silently combining sources.

Papers and TeX sources used for evaluation are downloaded temporarily and are not redistributed in this repository. The public evaluation suite stores only arXiv identifiers, prompts, synthetic fixtures, and expected behavior.

## Evaluate

Evaluation cases and the scoring rubric are in [`evals/explain-math-proof-idea`](evals/explain-math-proof-idea). The suite covers explicit theorem selection, semantic main-theorem selection, multiple main results, externally delegated proofs, source-version mismatches, language selection, and negative trigger cases.

Validate the skill structure with the `quick_validate.py` script bundled with OpenAI's `skill-creator`, passing `.agents/skills/explain-math-proof-idea` as the skill path.

## Known limitations

- Accurate page and displayed-number references require the PDF version the user is reading.
- TeX-first analysis requires source from the same version; otherwise the skill reports the mismatch.
- A proof delegated to an unavailable external reference can be explained only up to the reduction given in the supplied paper.
- When several results are co-primary, the skill requires the user to choose one before it continues.

## Contributing

Keep each change tied to a reproducible prompt. Update `SKILL.md`, add or revise a case under `evals/explain-math-proof-idea`, run structural validation, and forward-test the changed behavior on raw source material. Do not commit downloaded papers or copied TeX sources; use public identifiers or minimal synthetic fixtures.

## License

MIT
