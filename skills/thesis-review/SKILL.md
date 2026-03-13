name: thesis-review
description: Review, audit, or repair thesis LaTeX sources against the EasyLatex workflow and the active repository's exact rules.
---

# Thesis Review

## Use This Skill When

- the user asks for an audit, repair, compliance check, or structural review
- the repository already contains `.tex` sources that may violate the template contract

## First Read

1. Read the active repository rule file first. In this repo that is `D:/whuthesis/doc/rules.md`.
2. Read `D:/whuthesis/EasyLatex/workflows/txt-to-latex-workflow.md`.
3. Read the active root `.tex` file.

## Review Priorities

1. Wrong thesis profile or class options
2. Broken repository structure
3. Missing `\whusetup` fields
4. Missing `bib-backend` or `bib-resource`
5. Shared wrapper files overwritten with task content
6. Manual frontmatter or bibliography hacks
7. Placeholder handling regressions from source conversion
8. TexPage compatibility risks

## Conversion Checks

- standalone figure/table placeholders remain identifiable
- `【留空】` was not expanded into fabricated prose
- reference input stayed traceable to the original numbered entries
- task-specific content lives in task-specific files

## Fix Strategy

- prefer the smallest patch that restores compliance
- preserve user manuscript content whenever possible
- change structure before changing prose

## Maintenance Sync Rule

- When the parent `whuthesis` workspace gains new generic conversion capabilities, workflow improvements, template conventions, or reusable review logic, update the corresponding generic parts in `EasyLatex/` in the same task whenever feasible.
- Sync only the generic layer into `EasyLatex/`. Keep repository-specific rules, file contracts, and school-specific template constraints outside the generic toolkit unless they have been explicitly generalized.
