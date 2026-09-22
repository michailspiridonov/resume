# Resume

**[Read the current resume (PDF)](https://michailspiridonov.github.io/resume/resume.pdf)**

LaTeX sources for my resume, built on the
[TLCresume](https://github.com/liantze/AltaCV) style. The PDF is not committed
to this repository - it is compiled by GitHub Actions on every push to `main`
and published to GitHub Pages, so the link above always tracks the sources here.

## Layout

| Path | Purpose |
| --- | --- |
| `resume.tex` | Entry point: contact details, job title, section order |
| `_header.tex` | Page header (contact block, name, role) |
| `TLCresume.sty` | Style package: fonts, colours, spacing, custom commands |
| `sections/` | One file per section, each standalone-compilable |

Contact details and the job title are `\def`s at the top of `resume.tex`.

## Building locally

Requires a LaTeX distribution with `sourcesans`, `titlesec`, `moresize`,
`enumitem`, `csquotes`, `standalone`, `blindtext` and `fancyhdr`. On MiKTeX
the Source Sans package is named `sourcesans`, not `sourcesanspro`.

```sh
pdflatex resume.tex   # run twice so hyperref resolves its outlines
```

Or with `latexmk`, which handles the rerun loop:

```sh
latexmk -pdf resume.tex
```
