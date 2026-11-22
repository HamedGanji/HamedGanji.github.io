# Hamed F. Ganji

Personal website covering research, engineering, projects, publications and professional experience.

**Website:** [hamedganji.github.io](https://hamedganji.github.io/)

## Development

Built with [Quarto](https://quarto.org/). From the repository root:

```sh
quarto preview
quarto render . --to html
quarto render cv.qmd --to typst
```

The HTML and PDF CV share [cv.qmd](cv.qmd) as their source. Generated files are written to `_site/`.

## Deployment

Pushes to `main` trigger the [GitHub Actions workflow](.github/workflows/deploy.yml), which builds the site and CV PDF and deploys them to GitHub Pages.
