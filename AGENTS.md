# Quarto website

- Keep `cv.qmd` as the single source for the full CV in HTML and Typst PDF. Keep `nl/cv.qmd` linked to the full CV and the shared `/cv.pdf`.
- Preserve English and Dutch navigation, existing publication links, and unrelated changes.
- Keep generated output such as `_site/` out of commits. Preview changes locally and report results before committing, pushing, or publishing.

## Validate changes

- Run `quarto render . --to html` from the repository root.
- For changes affecting the CV or deployment, follow with `quarto render cv.qmd --to typst`. Confirm `_site/cv.pdf` exists and is nonempty.
- For CV changes, verify both rendered CV pages link to that PDF. If content or layout changed, inspect the PDF for complete content, readable pagination, and working links.
- Report commands, failures, warnings, and checks you could not run.

## Quarto Reviewer

- In Codex, ask it to delegate a review to `quarto_reviewer`.
- In GitHub Copilot, select **Quarto Reviewer** from the agent picker.
