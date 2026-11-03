# 多期刊科研论文 LaTeX 模板

本仓库提供一个可复用的科研论文 LaTeX 文件结构：将论文正文集中放在共享内容文件中，再通过不同期刊模板的入口文件生成对应格式的稿件。

## 目录结构

- `content/content.tex`：共享论文正文，由每套期刊模板统一引入。
- `content/abstract.tex`：共享摘要。
- `references/references.bib`：BibTeX 参考文献数据库。
- `ieee-latex/main.tex`：IEEE 风格入口文件。
- `wiley-latex/main.tex`：Wiley 风格入口文件。
- `else-latex/main.tex`：Elsevier CAS 风格入口文件。

每套模板的 `main.tex` 只负责文档类、期刊元数据、宏包、参考文献样式和文档包装。论文的章节、图、表和引用建议统一放在 `content/` 与 `references/` 中，这样可以在不同期刊格式之间复用同一份论文内容。

## 使用方法

1. 在 `content/abstract.tex` 中填写摘要。
2. 在 `content/content.tex` 中编写论文正文。
3. 在 `references/references.bib` 中维护参考文献。
4. 根据目标期刊修改对应目录下的 `main.tex`，尤其是标题、作者、单位、关键词和投稿专属元数据。
5. 在对应模板目录中编译：

```powershell
cd ieee-latex
latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex
```

Wiley 和 Elsevier 模板的编译方式相同，只需将 `ieee-latex` 替换为 `wiley-latex` 或 `else-latex`。

## 隐私与版本控制

这是一个公开仓库。提交前请确认正文、作者信息、邮箱、单位、基金编号、内部数据、实验结果和投稿材料中没有不应公开的内容。编译生成的 PDF、日志、辅助文件以及 `private/`、`drafts/` 和 `submitting/` 目录已通过 `.gitignore` 排除。

---

# Multi-Journal Research Paper LaTeX Template

This repository provides a reusable LaTeX structure for research papers. Manuscript content is kept in shared files and included by journal-specific entry points to produce different submission formats.

## Directory layout

- `content/content.tex`: shared manuscript body included by every journal adapter.
- `content/abstract.tex`: shared abstract.
- `references/references.bib`: BibTeX bibliography database.
- `ieee-latex/main.tex`: IEEE-style entry point.
- `wiley-latex/main.tex`: Wiley-style entry point.
- `else-latex/main.tex`: Elsevier CAS-style entry point.

Each adapter owns the document class, journal metadata, packages, bibliography style, and document wrapper. Keep sections, figures, tables, and citations in `content/` and `references/` so that the same manuscript can be reused across journal formats.

## Usage

1. Write the abstract in `content/abstract.tex`.
2. Write the manuscript body in `content/content.tex`.
3. Maintain bibliography entries in `references/references.bib`.
4. Edit the relevant `main.tex` for the target journal, especially the title, authors, affiliations, keywords, and journal-specific metadata.
5. Compile from the selected adapter directory:

```powershell
cd ieee-latex
latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex
```

The Wiley and Elsevier adapters use the same command; replace `ieee-latex` with `wiley-latex` or `else-latex`.

## Privacy and version control

This is a public repository. Before committing, make sure the manuscript, author details, email addresses, affiliations, grant numbers, private data, internal results, and submission materials contain no information that should remain private. Generated PDFs, logs, auxiliary files, and the `private/`, `drafts/`, and `submitting/` directories are excluded by `.gitignore`.
