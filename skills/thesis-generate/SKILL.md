name: thesis-generate
description: Generate or update thesis LaTeX sources from structured user material. Use EasyLatex templates and workflow first, then enforce the active repository's rules.
---

# Thesis Generate

## Use This Skill When

- the user provides thesis material, source text, metadata, references, or chapter content
- the target is repository-ready `.tex` and `.bib`
- the input is already in `.txt` form or can be normalized into the same structure

## First Read

1. Read the active repository rule file first. In this repo that is `D:/whuthesis/doc/rules.md`.
2. Read `D:/whuthesis/EasyLatex/workflows/txt-to-latex-workflow.md`.
3. Open only the specific repository files needed for the current task.

## Canonical EasyLatex Inputs

- `D:/whuthesis/EasyLatex/templates/conversion-source-guide.txt`
- `D:/whuthesis/EasyLatex/templates/conversion-source-bachelor-template.txt`
- `D:/whuthesis/EasyLatex/templates/conversion-source-master-template.txt`
- `D:/whuthesis/EasyLatex/templates/conversion-source-doctor-template.txt`

## Workflow

1. Determine `type`.
2. Determine `class` when applicable.
3. Choose a stable task slug.
4. Parse source content into metadata, abstracts, chapters, appendix, and references.
5. Start from `demo.tex` structure rather than an empty file.
6. Bind task-specific body files from the root entry file.
7. Keep shared wrapper files generic.
8. Generate `pages/*.tex` and `ref/*.bib`.
9. Prefer TexPage-compatible defaults unless the user requests otherwise.

## Source-Specific Rules

- Treat LaTeX math as source, not prose.
- Treat standalone `图x.x.x ...` and `表x.x.x ...` lines as centered placeholders.
- Preserve `【留空】` as an intentional empty block.
- Normalize copied artifacts such as `&amp;`.
- Do not invent missing bibliography facts.

## Hard Constraints

- Do not handwrite frontmatter pages.
- Do not overwrite `pages/abstract.tex`, `pages/enabstract.tex`, or `pages/innovation.tex` with task content.
- Do not use raw `\bibliography`.
- Do not move the root thesis entry file into a subdirectory.

## Maintenance Sync Rule

- When the parent `whuthesis` workspace gains new generic conversion capabilities, workflow improvements, template conventions, or reusable review logic, update the corresponding generic parts in `EasyLatex/` in the same task whenever feasible.
- Sync only the generic layer into `EasyLatex/`. Keep repository-specific rules, file contracts, and school-specific template constraints outside the generic toolkit unless they have been explicitly generalized.
