# Tropical geometry notes

Compile `main.tex` from the repository root to produce the complete notes.
The root document loads `header.tex`, builds the title and table of contents, and then includes each dated note in chronological order.

## Add a note

1. Copy an existing folder under `notes/` and rename it using `MM-DD-YY`.
2. Edit that folder's `main.tex`.
3. Add a corresponding `\input{notes/MM-DD-YY/main}` line to the dated-notes block in the root `main.tex`.

Each dated file is a document fragment, so it should not contain
`\documentclass`, `\begin{document}`, or `\end{document}`.

## Build

With `latexmk`:

```console
latexmk -pdf main.tex
```

Or run `pdflatex main.tex` twice so the table of contents is updated.
