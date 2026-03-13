# EasyLatex

EasyLatex is a reusable toolkit for converting structured source material into repository-ready LaTeX thesis files.

EasyLatex 是一套可复用的论文转换工具包，用于把结构化源材料快速整理成可直接落库的 LaTeX 论文文件。

## What It Contains / 包含内容

- `templates/`: source templates for `.txt` input
- `workflows/`: end-to-end conversion workflow documents
- `skills/`: reusable Codex skill documents for generation and review
- `adapters/`: adapter contracts, with `.txt` active now and `.docx` reserved for extension

- `templates/`：`.txt` 输入模板
- `workflows/`：端到端转换工作流说明
- `skills/`：可复用的 Codex skill 文档
- `adapters/`：适配层约定，当前以 `.txt` 为主，预留 `.docx` 扩展

## Directory Layout / 目录结构

```text
EasyLatex/
  README.md
  adapters/
    docx-adapter-spec.md
  skills/
    thesis-generate/
      SKILL.md
    thesis-review/
      SKILL.md
  templates/
    conversion-source-guide.txt
    conversion-source-bachelor-template.txt
    conversion-source-master-template.txt
    conversion-source-doctor-template.txt
  workflows/
    txt-to-latex-workflow.md
```

## Quick Start / 快速开始

1. Pick the matching template in `templates/`.
2. Fill it with plain text and LaTeX math only.
3. Keep heading levels with `#`, `##`, `###`, `####`.
4. Keep figure/table placeholders on their own lines.
5. Put references in `[n] full entry text` format.
6. Run the generation flow with the `thesis-generate` skill.
7. Run the compliance pass with the `thesis-review` skill.

1. 在 `templates/` 中选择对应学位类型模板。
2. 只填写纯文本正文和 LaTeX 数学公式。
3. 用 `#`、`##`、`###`、`####` 保持标题层级。
4. 图表占位文字必须单独成行。
5. 参考文献统一写成 `[序号] 完整条目文本`。
6. 使用 `thesis-generate` 执行生成流程。
7. 使用 `thesis-review` 做合规复核。

## Supported Input Now / 当前支持输入

- `.txt` is the production input format.
- UTF-8 is recommended.
- Content should contain text and LaTeX math only.

- `.txt` 是当前正式输入格式。
- 建议使用 UTF-8 编码。
- 输入内容只应包含文本和 LaTeX 公式。

## Planned Extension / 规划中的扩展

- `.docx` is not the default input yet.
- The extension boundary is defined in `adapters/docx-adapter-spec.md`.
- The intended approach is: normalize `.docx` into the same intermediate structure used by `.txt`, then reuse the same LaTeX generation and review flow.

- `.docx` 目前还不是默认输入格式。
- 扩展边界定义见 `adapters/docx-adapter-spec.md`。
- 预期方案是先把 `.docx` 归一化到与 `.txt` 相同的中间结构，再复用同一套 LaTeX 生成与复核流程。

## Workflow Summary / 工作流摘要

- Source intake: template-driven `.txt`
- Structural parse: metadata, abstracts, chapters, appendix, references
- LaTeX mapping: root entry, `pages/*.tex`, `ref/*.bib`
- Repository compliance: frontmatter automation, bibliography settings, wrapper-file safety

- 源文件采集：模板化 `.txt`
- 结构解析：元数据、摘要、章节、附录、参考文献
- LaTeX 映射：根入口文件、`pages/*.tex`、`ref/*.bib`
- 仓库合规：前置部分自动化、参考文献配置、共享包装文件保护

## Recommended Usage Inside This Repo / 在本仓库中的推荐用法

- Read `doc/rules.md` first.
- Treat the active repository's template class file as the final authority.
- Keep `pages/abstract.tex`, `pages/enabstract.tex`, and `pages/innovation.tex` generic.
- Write task-specific content into dedicated body files.

- 先读 `doc/rules.md`。
- 以当前仓库的模板类文件作为最终权威。
- 保持 `pages/abstract.tex`、`pages/enabstract.tex`、`pages/innovation.tex` 为通用包装层。
- 任务正文写入专属 body 文件。

## File Guide / 文件说明

- [txt-to-latex-workflow.md](/D:/whuthesis/EasyLatex/workflows/txt-to-latex-workflow.md): canonical conversion workflow
- [docx-adapter-spec.md](/D:/whuthesis/EasyLatex/adapters/docx-adapter-spec.md): `.docx` extension contract
- [conversion-source-guide.txt](/D:/whuthesis/EasyLatex/templates/conversion-source-guide.txt): source authoring guide
- [thesis-generate/SKILL.md](/D:/whuthesis/EasyLatex/skills/thesis-generate/SKILL.md): generation skill
- [thesis-review/SKILL.md](/D:/whuthesis/EasyLatex/skills/thesis-review/SKILL.md): review skill

## Maintenance Rule / 维护规则

- New generic conversion knowledge should go into `EasyLatex/` first.
- Repo-only constraints may still live in `doc/rules.md`.

- 新的通用转换能力优先沉淀到 `EasyLatex/`。
- 仅限本仓库的约束仍可保留在 `doc/rules.md`。
