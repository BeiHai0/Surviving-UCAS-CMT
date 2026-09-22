# Project Instructions

## 1. Project purpose

This repository contains study notes for graduate-level theoretical physics courses.

The notes are primarily written for personal study, review, and long-term knowledge organization.

The target reader is a graduate student in condensed matter theory.

Notes may be written in either:

- Markdown (`.md`), primarily for Obsidian;
- LaTeX (`.tex`), primarily for typeset notes, assignments, and PDF output.

The mathematical notation and writing style should remain consistent across both formats.

---

## 2. General writing principles

When creating or revising lecture notes:

- Prioritize mathematical correctness and logical clarity.
- Define concepts and notation before using them.
- Do not skip nontrivial steps in important derivations.
- Explicitly state assumptions when they are needed.
- Distinguish definitions, assumptions, derived results, and physical interpretations.
- Explain the physical or mathematical meaning of important results after deriving them.
- Avoid unnecessary repetition and excessive sectioning.
- Prefer a coherent logical progression over a collection of isolated facts.
- Do not introduce advanced results before they are needed unless clearly marked as supplementary material.

For an important derivation, prefer the structure:

1. State the problem or result to be derived.
2. State the assumptions and notation.
3. Derive the result step by step.
4. Explain why non-obvious steps are valid.
5. State the final result clearly.
6. Explain its mathematical or physical meaning.

---

## 3. Markdown files

Markdown files must render correctly in Obsidian.

Use standard Markdown syntax whenever possible.

Do not use syntax that depends on unsupported Markdown extensions unless the project already uses them.

Keep headings hierarchical:

- `#` for the document title;
- `##` for major sections;
- `###` for subsections;
- `####` only when genuinely necessary.

Do not create unnecessarily deep heading hierarchies.

For Markdown files, mathematical expressions must follow the conventions in Section 5.

---

## 4. LaTeX files

LaTeX files must compile with the existing project toolchain and document class.

When editing an existing `.tex` file:

- preserve the existing document class and overall preamble unless modification is necessary;
- reuse packages and macros already defined by the project;
- do not add redundant packages;
- do not replace project-standard mathematical notation with alternative commands;
- preserve the existing structure unless the task specifically requires restructuring.

When creating a new `.tex` file, follow the existing project template if one exists.

The notation used in `.tex` files should be consistent with the notation used in corresponding `.md` notes.

---

## 5. Mathematical formulas

### 5.1 Inline mathematics in Markdown

Use `$...$` for inline mathematics.

Example:

The state $\Ket{\psi}$ is an eigenstate of $H$.

Do not use `\(...\)` in Markdown files.

---

### 5.2 Display mathematics in Markdown

Display mathematics must use `$$`.

The opening and closing `$$` must each occupy their own line.

Correct:

$$
H\Ket{\psi}=E\Ket{\psi}.
$$

Incorrect:

`$$H\Ket{\psi}=E\Ket{\psi}.$$`

Do not use `\[...\]` in Markdown files.

---

### 5.3 Display mathematics in LaTeX

For `.tex` files, use the mathematical environments already adopted by the project.

Prefer standard AMS environments such as:

- `equation`;
- `align`;
- `gather`;

when numbering or alignment is required.

Do not convert existing structured LaTeX environments into Markdown-style `$$...$$`.

---

### 5.4 Equation numbering

Do not manually number equations with `\tag{}` unless the task explicitly requires a custom equation tag.

For `.tex` files, use standard numbered environments when equation numbering is needed.

For `.md` files, do not add equation numbers merely for visual appearance unless the project has explicitly adopted an equation-numbering system.

---

## 6. Standard mathematical notation

Notation must be consistent throughout the project.

Once a symbol has been defined, do not silently change its meaning.

### 6.1 Upright mathematical symbols

Use upright Roman type for mathematical constants, named groups, operators, and labels when appropriate.

Examples:

$$
\mathrm{SU}(2),\qquad
\mathrm{SO}(3),\qquad
\mathrm{Tr}\,A.
$$

### 6.2 Imaginary unit

Use

$$
\mathrm{i}
$$

for the imaginary unit.

For example:

$$
\mathrm{i}^2=-1.
$$

Do not use a bare italic $i$ for the imaginary unit when it can be confused with an index.

### 6.3 Natural exponential constant

Use

$$
\mathrm{e}
$$

for Euler's number, i.e. the base of the natural exponential.

For example:

$$
\mathrm{e}^{x},
\qquad
\mathrm{e}^{-\mathrm{i}Ht/\hbar},
\qquad
\mathrm{e}^{\mathrm{i}\mathbf{k}\cdot\mathbf{r}}.
$$

Do not write the natural exponential constant as a bare italic $e$.

A symbol $e$ may remain italic only when it denotes an ordinary variable, charge, index, or another quantity explicitly defined as $e$.

### 6.4 Differentials

Use `\mathrm{d}` for differentials.

For example:

$$
\int f(x)\,\mathrm{d}x.
$$

Use appropriate spacing before the differential.

For multiple integrals, write for example:

$$
\int f(x,y)\,\mathrm{d}x\,\mathrm{d}y.
$$

---

## 7. Dirac notation

Dirac notation must use the following project-standard commands:

- `\Ket{...}` for kets;
- `\Bra{...}` for bras;
- `\Braket{...}` for inner products or matrix elements when appropriate.

Examples:

$$
\Ket{\psi},
\qquad
\Bra{\psi},
\qquad
\Braket{\phi|\psi}.
$$

For matrix elements, use:

$$
\Braket{\phi|A|\psi}.
$$

Do not manually construct Dirac notation using forms such as

`|\psi\rangle`

or

`\langle\phi|\psi\rangle`

when the corresponding project-standard command can be used.

Do not replace `\Bra`, `\Ket`, or `\Braket` with alternative commands such as `\bra`, `\ket`, or `\braket`.

The project environment must provide definitions or package support for `\Bra`, `\Ket`, and `\Braket` in every output format where they are used.

---

## 8. Quantum-mechanical notation

Use `\dagger` for Hermitian conjugation:

$$
A^\dagger.
$$

Clearly distinguish:

- states;
- operators;
- eigenvalues;
- matrix representations;
- basis labels;
- scalar coefficients.

Do not identify an abstract operator with one particular matrix representation unless the context explicitly permits it.

When a basis representation is introduced, state the basis explicitly when ambiguity is possible.

---

## 9. Derivations and proofs

Do not replace a derivation with phrases such as:

- "obviously";
- "it is easy to see";
- "similarly";

when the omitted step is conceptually important.

These phrases are acceptable only when the omitted algebra is genuinely routine.

When proving a theorem or mathematical statement:

- state exactly what is assumed;
- state exactly what is being proved;
- identify any theorem used;
- do not use results that have not yet been introduced unless explicitly stated.

When manipulating operators, matrices, distributions, derivatives, or integrals, make the domain of action clear whenever ambiguity may arise.

When an equality follows from a nontrivial identity, explain which identity is being used.

---

## 10. Explanations

For important concepts, distinguish between:

1. the formal definition;
2. the mathematical consequence;
3. the intuitive interpretation;
4. the physical interpretation, when applicable.

Do not substitute intuition for a proof.

Do not substitute formal algebra for an explanation when the physical meaning is important.

When a mathematical result has a useful physical interpretation, state that interpretation after the formal derivation rather than mixing it into the algebraic steps.

---

## 11. Editing existing notes

When modifying an existing file:

- preserve the existing overall style unless there is a good reason to change it;
- preserve established notation unless it is incorrect or inconsistent with project rules;
- avoid rewriting unrelated sections;
- make the smallest coherent change needed to complete the task;
- check nearby sections for notation and logical dependencies before editing.

If existing notation conflicts with this `AGENTS.md`, prefer the project-wide convention when making substantial revisions.

Do not perform large-scale notation replacement in unrelated material unless explicitly requested.

If a requested change conflicts with existing notation or structure, identify the conflict before making a large-scale rewrite.

---

## 12. Consistency between Markdown and LaTeX

When `.md` and `.tex` versions of the same material coexist:

- use the same mathematical symbols;
- use the same Dirac notation;
- use the same conventions for $\mathrm{i}$, $\mathrm{e}$, and $\mathrm{d}$;
- preserve the same logical structure where practical;
- do not introduce notation differences merely because the output format differs.

Formatting syntax may differ between Markdown and LaTeX, but mathematical conventions must remain consistent.

---

## 13. File operations

Do not rename, move, or delete existing files unless the task requires it.

Do not create duplicate versions such as:

- `chapter-final.md`;
- `chapter-final-v2.md`;
- `chapter-new.md`;
- `chapter-final.tex`;

unless explicitly requested.

Prefer editing the canonical project file.

Do not modify unrelated files.

When both `.md` and `.tex` files exist, do not assume that both should be modified unless the task or project structure makes that relationship explicit.

---

## 14. Verification before finishing

After creating or substantially modifying lecture notes, check:

- mathematical correctness;
- consistency of notation;
- correct use of `\Bra`, `\Ket`, and `\Braket`;
- correct use of `\mathrm{i}`;
- correct use of `\mathrm{e}` for Euler's number;
- correct use of `\mathrm{d}` for differentials;
- completeness of important derivations;
- Markdown syntax for `.md` files;
- Obsidian compatibility for `.md` files;
- LaTeX syntax and compatibility for `.tex` files;
- accidental use of `\tag{}`;
- heading or section hierarchy;
- whether newly introduced symbols have been defined;
- whether the requested scope has actually been completed.

Do not claim that a derivation, formula, compilation, or statement has been verified unless it has actually been checked.

---

## 15. Task-specific instructions

Instructions in the current task may add requirements to these project rules.

Task-specific instructions should normally supplement this file.

If a task-specific instruction explicitly conflicts with a project convention, follow the more specific instruction for that task while minimizing unnecessary changes elsewhere.