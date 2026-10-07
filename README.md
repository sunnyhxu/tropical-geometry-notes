# Tropical geometry notes

This project contains two collections:

- `drp/`: theoretical tropical geometry notes from the directed reading
  program.
- `auction/`: applications of tropical geometry to auction theory.

## Add a dated note

1. Choose either `drp/` or `auction/`.
2. Create a folder in that collection named using `MM-DD-YY`.
3. Copy the collection's `template.tex` into the new folder as `main.tex`.
4. Add `\subfile{COLLECTION/MM-DD-YY/main}` to the corresponding root file,
   either `drp.tex` or `auction.tex`.

For example, to add auction notes for October 8, 2026:

```powershell
New-Item -ItemType Directory auction/10-08-26
Copy-Item auction/template.tex auction/10-08-26/main.tex
```

Then add this line to `auction.tex`:

```tex
\subfile{auction/10-08-26/main}
```

Keep dated folders exactly one level below their collection. This ensures that
the template's `../../main.tex` path continues to point to the combined root
document.

## Build

Run one of these commands from the repository root:

```console
latexmk -pdf main.tex
latexmk -pdf drp.tex
latexmk -pdf auction.tex
```

If `latexmk` is unavailable, run `pdflatex` twice on the desired entry point so
its table of contents is updated.

