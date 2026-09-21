# Graduate Final Exam — Research Paper Template

**English** | [한국어](README.ko.md)

A blank LaTeX template for writing **your own research paper as a graduate course final exam**.
It uses an IEEE-style, two-column layout with letter-sized paper and 10pt text.
It includes no original research content, authors, experimental results, figures, references, or Git history from the source paper.
All instructional paragraphs, figures, equations, tables, and citations are placeholders to replace with your own work.

## Quick start — Overleaf

1. Select **Use this template → Create a new repository** on GitHub to create your own repository. Using the template feature instead of forking gives you an independent history.
2. In your repository, select **Code → Download ZIP**.
3. In Overleaf, select **New Project → Upload Project** and upload the ZIP.
4. Set the main document to `main.tex` and the compiler to **pdfLaTeX**, then click Recompile.
5. Update the title, author, and affiliation/email inside `\thanks`, then replace the paragraphs in `src/` with your own writing.

`main.pdf` is a preview of the expanded dummy paper. Its length is not capped at four pages. Recompile after editing to update the PDF.

## File structure

| File | Purpose |
| --- | --- |
| `main.tex` | Title, author, affiliation/email footnote at the bottom left of page one, packages, and section inputs |
| `src/abstract.tex` | Abstract |
| `src/introduction.tex` | Introduction, research question, and contributions |
| `src/related_work.tex` | Related work |
| `src/problem_formulation.tex` | Problem definition and notation |
| `src/method.tex` | Proposed method |
| `src/experiments.tex` | Experimental setup and results |
| `src/discussion.tex` | Interpretation and limitations |
| `src/conclusion.tex` | Conclusion |
| `figures/hook.tex` | Fig. 1: visual hook at the top right of page one |
| `figures/overview.tex` | Fig. 2: full-width method overview at the top of page two |
| `figures/component.tex` | Fig. 3: internal mechanism of an individual component |
| `figures/qualitative.tex` | Fig. 4: placeholder qualitative comparison |
| `figures/sensitivity.tex` | Fig. 5: empty plot for sensitivity or robustness analysis |
| `tables/results.tex` | Placeholder results table with no measured values |
| `tables/component_ablation.tex` | Table II: component-removal ablation for components A/B |
| `tables/design_ablation.tex` | Table III: performance/cost ablation across design alternatives |
| `references.bib` | 15 fictional references, cited by role throughout the text — replace with real sources |
| `ieeeconf.cls` | Shared LaTeX class providing the paper layout |

## Build locally

With TeX Live or MiKTeX, `latexmk`, and the required packages installed:

```sh
latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex
```

Without `latexmk`:

```sh
pdflatex -interaction=nonstopmode -halt-on-error main.tex
bibtex main
pdflatex -interaction=nonstopmode -halt-on-error main.tex
pdflatex -interaction=nonstopmode -halt-on-error main.tex
```

You can also build with Tectonic using `tectonic main.tex`.
The IEEEtran package in your TeX distribution provides `IEEEtran.bst`.

## Before submission

The 15 references demonstrate different citation roles: background survey,
application motivation, foundational and alternative methods, hybrid approaches,
representations, optimization, software, datasets, metrics, baselines,
reproducibility, ablation design, robustness, and limitations.
They are integrated into the Introduction, Related Work, Method, Experiments,
and Discussion. Every bibliography entry is explicitly fictional; none is
intended as evidence or a real publication recommendation.

The `flafter` package prevents figures from appearing before their declaration.
With the current dummy content, Fig. 1 appears at the top right of page one, and Fig. 2 spans both columns at the top of page two.
Substantial changes to text or figure sizes may change LaTeX's automatic placement, so check the final PDF.

- Replace the title, name, and affiliation. Remove all instructional text and occurrences of `DUMMY`, `Placeholder`, and `[replace]`.
- Connect the research question, gap in prior work, proposed method, evaluation, and conclusion.
- Replace the figures and tables with your own material and reference them in the text. A `---` table entry means unmeasured, not zero.
- Remove fictional references and cite only real sources you have checked.
- Do not invent experimental results. If the work is a proposal, clearly label the evaluation as a plan.
- Check citations, equations, figures, tables, and text overflow in the final PDF.
- Follow your course announcement for page limits, deadlines, deliverables, and grading criteria. This template does not prescribe those requirements.

## Class file notice

Only the `ieeeconf.cls` file needed to preserve the layout was retained from the source template, without modification.
Its copyright, contributor, and Perl Artistic License notices are preserved.
All other template files were newly written for classroom use.
