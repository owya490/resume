# LaTeX Resume Template

Academic-style resume with a maroon timeline layout, FontAwesome contact icons, and a profile photo slot.

## File structure

| File | Purpose |
|------|---------|
| `resume.tex` | Document wrapper — loads the template and your content |
| `template.sty` | Formatting, colors, and macros — **do not edit** unless changing layout |
| `content.tex` | **Your data only** — header, jobs, education, skills |
| `profile.jpg` | Optional profile photo (not included; see below) |

## Quick start

1. Edit `content.tex` with your information.
2. Optionally add a square photo named `profile.jpg` in this folder (or set `\renewcommand{\profilephoto}{your-file.jpg}` in `content.tex`).
3. Compile:

```bash
pdflatex resume.tex
```

If no photo is found, a placeholder silhouette is shown automatically.

## Add a work entry

Copy this block into the **Work Experience** section of `content.tex`:

```latex
\begin{WorkEntry}{Jan 2024 -- Present}{Company Name}{Job Title}{City, ST}
  \item First accomplishment or responsibility.
  \item Second bullet point.
  \item \textbf{Stack:} Languages, tools, frameworks
\end{WorkEntry}
```

Arguments: `{dates}{company}{title}{location}` — then add `\item` lines inside the environment.

## Add an education entry

```latex
\begin{EducationEntry}{May 2020}{University Name}{B.S. Major, GPA: 3.9/4.0}{City, ST}
  \item Honors, activities, or relevant coursework (optional)
\end{EducationEntry}
```

Omit the `\item` lines if you have no bullets.

## Add skills / certifications

Use `\SkillLine{Label}{content}` inside the existing `SkillsList` block:

```latex
\SkillLine{Certifications}{AWS Solutions Architect; CKA}
\SkillLine{Technologies}{Python, Go, Kubernetes}
```

## Profile photo

Place a square image (e.g. `profile.jpg`) in this directory. The template crops it to 3 cm × 3 cm with a light blue border. Without a photo, a vector placeholder is rendered instead.

## Requirements

- LaTeX distribution with `pdflatex` (TeX Live, MacTeX, or MiKTeX)
- Packages used: `geometry`, `fontawesome5`, `tikz`, `hyperref`, `enumitem`, and others (included in standard TeX Live installs)
