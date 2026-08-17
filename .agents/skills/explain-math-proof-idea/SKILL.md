---
name: explain-math-proof-idea
description: Explain the core proof idea of a specified theorem, proposition, or lemma in a mathematical research paper at expert depth. Use when the user supplies a PDF, arXiv URL, or TeX source and identifies a result by number, quotation, or section, or asks for the paper's main theorem. Resolve the target, trace its proof and essential dependencies, and explain the decisive mechanism with source locators. Do not use for whole-paper summaries, full formal proof verification, LaTeX debugging, or copyediting.
---

# Explain Math Proof Idea

Explain the decisive idea in one proof as if the paper's author were giving a five-to-ten-minute explanation to a specialist. Preserve the mathematics, emphasize the mechanism that makes the proof work, and include only the context needed to understand that mechanism.

## Set the language and scope

1. Use an explicitly requested output language.
2. Otherwise, use the language of the user's request.
3. Default to English when the request does not establish a language. Do not infer the output language from the paper.
4. Focus on one theorem, proposition, lemma, or corollary. Do not turn the response into a whole-paper summary or a line-by-line proof rewrite.
5. Treat correctness review, formalization, and reconstruction of omitted proofs as separate tasks unless the user explicitly requests them.

## Resolve the target result

Pin the paper and version before analyzing the proof. Record the title, authors, version or date when available, and the source formats actually inspected.

Apply this precedence:

1. Prefer the user's explicit result number, name, quotation, or section reference.
2. Prefer TeX source from the same paper version for theorem environments, labels, references, proof boundaries, and dependency tracing.
3. Use the PDF from the version the user is reading to verify displayed theorem numbers, pages, equations, and typography-dependent notation.
4. When TeX and PDF numbering disagree, report the mismatch and use the user's PDF numbering in the explanation. Do not silently combine versions.
5. Map an informal introduction statement to the formal result whose proof is given later. Distinguish the formal theorem from a highlighted corollary or application.

For an arXiv URL, inspect the versioned abstract page and obtain both source and PDF when available. Keep temporary downloads outside the user's repository unless the user asks to retain them.

When the user asks for "the main theorem":

- Inspect the abstract, introduction, explicit phrases such as "main theorem" or "main result," formal result statements, and the paper's dependency structure.
- If one result is clearly primary, identify it, give one sentence explaining the choice, and continue.
- If two or more results are genuinely co-primary, stop before explaining a proof. List each candidate's number, page or TeX label when verified, and a one-sentence statement; ask the user to select one.
- Do not select a result solely because it appears first or has the strongest-looking conclusion.

If the requested result cannot be located, state what sources and identifiers were checked. Offer verified nearby candidates instead of inventing a match.

## Trace the proof

Read the exact statement and retain every material hypothesis, quantifier, and conclusion. Locate the proof even when it is deferred to another section or expressed as a chain of propositions.

Build a compact dependency map before writing:

- Separate results proved in the paper from results imported from other sources.
- Include only dependencies essential to the core mechanism.
- Follow cross-references far enough to understand why the decisive step applies.
- Distinguish reductions, constructions, estimates, compactness arguments, inductions, contradiction steps, and case-specific cleanup.
- Mark any step whose justification is unavailable in the supplied sources.

If the paper cites an external proof without reproducing it, explain only the reduction and role established in the supplied paper. Name the missing external dependency and do not reconstruct its proof from general knowledge unless the user supplies or requests that source.

## Identify the core idea

Determine:

1. The main obstacle that a routine argument does not overcome.
2. The non-obvious move that changes the problem: a construction, change of viewpoint, invariant, auxiliary object, decomposition, comparison, or decisive estimate.
3. Why that move removes the obstacle.
4. Where the key hypotheses enter.
5. Which remaining steps are technical completion rather than conceptual novelty.

Prefer the conceptual vocabulary used by the paper. When later literature gives the argument a useful name or reinterpretation, label that description as later terminology rather than attributing it to the authors. Clearly mark interpretive synthesis with phrases such as "Conceptually, the proof can be viewed as..." when the paper does not make that interpretation explicit.

## Write the explanation

Use the following headings in order. Omit a field only when it is genuinely unavailable, and say why in `Limits`.

### Target result

State the verified theorem, proposition, lemma, or corollary number; give a faithful compact statement; and include the PDF page and TeX label when available.

### Role in the paper

Give only the context needed to understand why this result matters and how it supports the paper's larger argument.

### Proof architecture

Summarize the proof as a short sequence of conceptual stages. Show the flow of implication without reproducing every calculation.

### Core idea

Devote most of the explanation to the decisive move. Preserve the essential formulas and explain how the relevant objects interact. Write at a level from which a specialist can reconstruct the strategy.

### Why it works

Connect the decisive move to the theorem's hypotheses and to the essential lemmas or estimates. Explain the exact point at which the main obstacle disappears.

### Technical remainder

Briefly identify bookkeeping, approximation, limiting, regularity, sign, or case-checking steps that complete the proof but are not its central idea.

### Source pointers

List only verified locations: result and proof pages, section names, TeX labels, equation numbers, and essential dependency locations. Never guess a page, label, or number.

### Limits

Disclose unavailable source, OCR uncertainty, version mismatches, omitted or externally cited proofs, and any interpretive claim not stated explicitly by the authors.

Keep the response roughly suitable for a five-to-ten-minute expert explanation. Expand beyond that only when the user asks for prerequisites, proof details, or a deeper dependency.
