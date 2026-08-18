# Explain Math Proof Idea

`$explain-math-proof-idea` explains the decisive idea in the proof of one theorem, proposition, lemma, or corollary from a mathematical research paper. It is designed to sound like a focused five-to-ten-minute explanation from the author to another specialist.

## When to use it

Use this skill when you want to understand the proof mechanism of a specific result rather than receive a whole-paper summary or a line-by-line proof rewrite.

The target may be:

- an explicit result such as `Theorem 2.3`, `Proposition 4`, or a quoted statement;
- a result identified by section or another unambiguous description;
- the main theorem of a paper.

Supported sources include PDF files, arXiv URLs, and TeX source.

## Usage

Invoke the skill explicitly when desired:

```text
Use $explain-math-proof-idea to explain the core proof idea of Theorem 2.3 in this paper.
```

```text
Explain the core proof idea of the main theorem in this paper.
```

For an explicit target, the skill verifies the result, traces its proof and essential dependencies, and explains the obstacle, decisive move, and role of the hypotheses.

For a request about "the main theorem," the skill compares the abstract, introduction, formal result statements, and dependency structure. If several results are genuinely co-primary, it lists the candidates and asks you to select one before explaining a proof.

## Output

The explanation identifies:

- the verified target result and its role in the paper;
- the proof architecture;
- the core idea and why it works;
- the role of essential hypotheses and dependencies;
- the technical remainder;
- verified source pointers and any limits of the analysis.

English is the default. The language of the user's prompt or an explicit language request takes precedence.

## Source handling

The skill prefers TeX source from the same paper version for theorem environments, labels, proof boundaries, cross-references, and dependency tracing. It uses the PDF version the user is reading to verify displayed theorem numbers, pages, equations, and typography-dependent notation.

When TeX and PDF numbering disagree, the skill reports the mismatch and uses the user's PDF numbering in the explanation. It does not silently combine versions.

For an arXiv URL, the skill inspects the versioned paper and obtains source and PDF when available. Temporary downloads stay outside the user's repository unless the user asks to retain them.

Papers and TeX sources used for evaluation are not redistributed in this repository. The public evaluation suite stores only arXiv identifiers, prompts, synthetic fixtures, and expected behavior.

## Limitations

- Accurate page and displayed-number references require the PDF version the user is reading.
- TeX-first analysis requires source from the same version; otherwise the skill reports the mismatch.
- A proof delegated to an unavailable external reference can be explained only up to the reduction given in the supplied paper.
- When several results are co-primary, the user must choose one before the skill continues.
- The skill does not perform whole-paper summaries, full formal proof verification, LaTeX debugging, or copyediting.

## Evaluation

Evaluation cases and the scoring rubric are in [`evals/explain-math-proof-idea`](../../evals/explain-math-proof-idea). The suite covers target resolution, proof tracing, source-version handling, language selection, and negative triggers.
