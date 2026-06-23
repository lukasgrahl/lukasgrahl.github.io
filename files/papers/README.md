# Research PDFs

Place public research files in this folder.

Recommended filenames use lower-case letters and hyphens, for example:

- `ambiguity-retail-trading.pdf`
- `ambiguity-retail-trading-appendix.pdf`
- `ambiguity-retail-trading-slides.pdf`

Link to them from `research.qmd` using a path relative to the project root:

```markdown
[Download paper (PDF)](files/papers/ambiguity-retail-trading.pdf){.button}
```

Quarto copies everything in `files/` into the published website because that folder is declared as a project resource in `_quarto.yml`.
