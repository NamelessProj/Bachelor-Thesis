# Bachelor Thesis | NamelessStory

LaTeX source for my Bachelor of Science (Web) thesis, submitted to [SAE Institute Genève](https://www.sae.edu/) in July 2026.

The thesis documents the design, implementation, and evaluation of **[NamelessStory](https://github.com/NamelessProj/NamelessStory)**, a web-based Visual Novel engine driven entirely by a declarative JSON script, built to let non-developer authors create and publish interactive fiction without installing or compiling anything.

> **Research question:** To what extent does a web Visual Novel engine architecture, based on a declarative script format, allow non-developer authors to create and deploy interactive content?

## Versions

| Language | Branch | Status |
|---|---|---|
| 🇫🇷 French | [`main`](../../tree/main) | Original, as submitted to SAE Genève |
| 🇬🇧 English | [`english-version`](../../tree/english-version) | Translation for personal usage, not a formal academic submission |

Compiled PDFs for both versions are attached to the [Releases](../../releases) page.

## Structure

```
chapters/       thesis chapters (front matter + 6 chapters + bibliography)
img/            figures
glossary.tex    glossary and acronym definitions
references.bib  bibliography (Harvard style, biblatex)
main.tex        document entry point
```

## Building locally

Requires a LaTeX distribution (TeX Live or MiKTeX) with:
- `biber` for the bibliography
- `makeglossaries` for the glossary/acronyms (on Windows/MiKTeX without Perl, use `makeglossaries-lite` instead)
- Python + [Pygments](https://pygments.org/) for code listings (`minted`)

```bash
pdflatex -shell-escape main.tex
biber main
makeglossaries main
pdflatex -shell-escape main.tex
pdflatex -shell-escape main.tex
```

`-shell-escape` is required by the `minted` package to call Pygments for syntax highlighting. A full rebuild needs two `pdflatex` passes at the end so cross-references, citations, and glossary links resolve correctly.

## License

The thesis text, figures, and diagrams in this repository are licensed under [**CC BY-NC-ND 4.0**](https://creativecommons.org/licenses/by-nc-nd/4.0/) (Attribution–NonCommercial–NoDerivatives) — see [`LICENSE`](LICENSE).

This does **not** cover:
- Cited excerpts and quotations, which remain under their original authors' rights (see in-text citations and [`references.bib`](references.bib)).
- The `Higurashi When They Cry Hou` screenshot ([`img/higurashi_dialogue.png`](img/higurashi_dialogue.png)), used for illustration under fair-use/citation, © 07th Expansion.
- Code excerpts from **NamelessStory**, governed by that project's own repository.

## Author

**Da Silva Pinto Kevin** — [GitHub](https://github.com/NamelessProj)
