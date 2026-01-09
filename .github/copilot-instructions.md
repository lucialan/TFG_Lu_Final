# AI Coding Agent Instructions - TFG LaTeX Project

## Project Overview
This is a LaTeX document for a Spanish university thesis (TFG - Trabajo de Fin de Grado) in Chemistry, focused on the crystallographic study of lanthanide orthophosphates and related structures (Zircon, Xenotime, Monazite, Churchite, Rhabdophane).

## Document Structure

### Main Document: `main.tex`
- **Language**: Mixed English (Introduction chapters) and Spanish (Objectives, Results, Conclusions)
- **Required Font**: Times New Roman (files in `/fonts/` directory: TIMES.TTF, TIMESBD.TTF, TIMESI.TTF, TIMESBI.TTF)
- **Compilation**: Requires LuaLaTeX or XeLaTeX (uses `fontspec` and `polyglossia`)
- **Bibliography**: Uses BibLaTeX with APA style + numeric citations (`\cite{}` → `[1]`)

### Formatting Requirements (FCQ - Faculty of Chemical Sciences)
- **Margins**: 2.5 cm on all sides
- **Line spacing**: 1.5 lines (`\onehalfspacing`)
- **Paragraphs**: No indentation (`\parindent=0pt`), vertical spacing between paragraphs
- **Chapter titles**: No "Capítulo" prefix, no extra spacing (`titlesec` custom format)
- **Figures**: Numbered consecutively without chapter prefix (Figure 1, 2, 3... not Figure 1.1)
- **Tables**: Same as figures (Tabla 1, 2, 3... not Tabla 1.1)

## Image Organization Pattern

Images are organized by mineral structure in `Imagenes/` with consistent subdirectories:
```
Imagenes/
  X_STRUCTURE_NAME/
    ATOMS/          # Ball-and-stick representations (projections along a, b, c axes)
    POLYHEDRA/      # Polyhedral representations showing coordination environments
    UC_POL/         # Unit cell with polyhedra
    UC_WIRE/        # Unit cell in wireframe mode
    WIREFRAME/      # Wireframe structures
```

**Important**: RHABDOFANO has typo in subdirectory names (`UD_POL/`, `UD_WIRE/` instead of `UC_POL/`, `UC_WIRE/`)

### Naming Convention for Images
- Projections: `STRUCTURE_a.png`, `STRUCTURE_b.png`, `STRUCTURE_c.png` (for views along a, b, c axes)
- Polyhedra: `STRUCTURE_Td.png` (tetrahedral), `STRUCTURE_Dode.png` (dodecahedral)
- Connection patterns: `STRUCTURE_pol_conex.png`

## Language Switching
The document switches between English and Spanish:
- Use `\setmainlanguage{english}` and `\captionsetup[figure]{name=Figure}` for English sections
- Use `\setmainlanguage{spanish}` and `\captionsetup[figure]{name=Figura}` for Spanish sections
- Default table caption is "Tabla" (Spanish); change to "Table" in English sections

## Chemical Notation
- Use `\ce{}` from `mhchem` package for chemical formulas: `\ce{LnPO4}`, `\ce{ZrSiO4}`
- For section titles with chemicals, use `\texorpdfstring{\ce{LnPO4}}{LnPO4}` to avoid PDF bookmark issues

## Bibliography Management
- All references in `Bibliografia.bib` (BibTeX format)
- Cite with `\cite{key}` → renders as `[1]`
- Style: APA format but with numeric citations (hybrid approach)
- No hanging indent (`\bibhang=0pt`)
- 1.5 baseline spacing between entries

## Figure and Table Placement
- All use `[H]` placement (requires `float` package) for exact positioning
- Standard width: `width=0.5\textwidth` to `width=0.7\textwidth` for full-width images
- Multi-panel figures use `subcaption` environment with `\linewidth` for individual subfigures

## Build Commands
```bash
lualatex main.tex
biber main
lualatex main.tex
lualatex main.tex
```
Or use latexmk if configured for LuaLaTeX.

## Common Patterns When Adding Content

### Adding a new mineral structure section
1. Create new subsection under "Resultados y Discusión"
2. Use pattern from existing sections (Zircón, Xenótimo, etc.)
3. Include: crystal system, space group, Hermann-Mauguin notation explanation, Z value
4. Table with atomic coordinates (use template from existing structures)
5. Multi-panel figure showing projections along a, b, c axes
6. Polyhedral representations with coordination analysis
7. Unit cell visualization

### Adding figures
- Reference images from `Imagenes/X_STRUCTURE/` subdirectories
- Use relative paths: `Imagenes/1_ZIRCON/ATOMS/ZIRCON_a.png`
- Always include `\caption{}` and `\label{fig:...}`
- Cross-reference with `\ref{fig:...}`

### When editing bibliography
- Add entries to `Bibliografia.bib` following existing format
- Rerun `biber main` after changes
- Verify citation keys match usage in text
