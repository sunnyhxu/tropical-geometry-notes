# Tropical geometry notes

Each dated note is both an independently compilable document and a subfile of
the complete notes. The root `main.tex` loads `header.tex`, builds the title and
table of contents, and includes each dated note in chronological order.

## Add a note

1. Create a folder under `notes/` named using `MM-DD-YY`.
2. Copy `notes/template.tex` into it and rename the copy to `main.tex`.
3. Replace the section title and template content.
4. Add `\subfile{notes/MM-DD-YY/main}` to the dated-notes block in the root
   `main.tex`.

Keep each dated folder exactly one level below `notes/`. This makes the
template's `../../main.tex` path point to the root document.

## Build all notes

From the repository root, run:

```console
latexmk -pdf main.tex
```

Alternatively, run `pdflatex main.tex` twice so the table of contents is
updated.

