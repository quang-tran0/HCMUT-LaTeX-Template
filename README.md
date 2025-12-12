# LaTeX Template

A structured LaTeX template for reports/books with reusable components, consistent styling, and a clear layout. The template separates content, layout, headers, styles, and reusable boxes to keep documents maintainable and easy to extend.

<img src="cover-preview.png" alt="Cover Preview" width="100%">

## Quick Start (Windows)
- Prerequisites: Install MiKTeX, Strawberry Perl. For auto-builds, install LaTeX Workshop extension in VS Code.

- The main entry point is `main.tex`. Generated PDFs and auxiliary files will be created alongside it.

## Project Structure
- `main.tex`: Top-level document that assembles layout and sections.
- `Layout/`: Page layout, cover, table of contents, references, and the custom class.
	- `main-layout.cls`: Main class that defines page geometry, fonts, headers/footers.
	- `cover.tex`: Cover page content.
	- `table-of-content.tex`: Table of contents configuration.
	- `reference.tex`: References or bibliography section.
	- `contribution.tex`: Author contributions or acknowledgements.
- `Headers/`: Shared header macros and package setup.
	- `lib.tex`: Common packages, commands, and input paths.
- `Sections/`: Your document content, split into logical parts.
	- `main.tex`: Assembles `section1.tex`, `Section2.tex`, etc.
	- `section1.tex`, `Section2.tex`: Example section files.
- `Styles/`: Global styles and custom commands.
	- `global.sty`: Styling for headings, colors, environments.
- `Templates/`: Reusable component templates.
	- `question-box.tex`: A ready-to-use box environment for Q&A or exercises.
- `Graphics/`: Images and figures.

## How It All Connects
`main.tex` loads shared libraries and layout, then includes section files. Typical top-level flow:

```latex
% main.tex (excerpt)
\documentclass{Layout/main-layout}
\input{Headers/lib}
\begin{document}
	\input{Layout/cover}
	\input{Layout/table-of-content}
	\input{Sections/main}
	\input{Layout/reference}
	\input{Layout/contribution}
\end{document}
```

Adjust paths as needed to match your current file names.

## Writing Content
- Put most content in `Sections/sectionX.tex` files.
- Keep reusable macros in `Styles/global.sty` or `Headers/lib.tex`.
- Include images from `Graphics/` using `\includegraphics{Graphics/your-image}`.

### Include Sections in Order
In `Sections/main.tex`, list your sections in the desired order:

```latex
% Sections/main.tex
\input{Sections/section1}
\input{Sections/Section2}
```

## Reusable Components (Copy & Paste)
The template includes pre-written components in the `Templates/` folder you can drop into any section.
