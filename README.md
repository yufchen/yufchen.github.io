# Yufeng Chen — personal website and CV

This repository keeps the source for [yufchen.github.io](https://yufchen.github.io/) and the LaTeX CV in one Git history.

## What to edit

- Website profile and links: `_config.yml`
- Homepage: `_pages/about.md`
- Research: `_pages/research.md`
- Publications: `_pages/publications.md`
- Teaching: `_pages/teaching.md`
- CV source: `files/cv/resume.tex`

## Typical workflow

```powershell
git pull
git switch -c update/site-or-resume
# edit the website or CV
git status
git add _pages files/cv/resume.tex
git commit -m "Update website and CV"
git push -u origin update/site-or-resume
```

Merge the branch into `master` when the update is ready. GitHub Actions compiles the LaTeX CV, builds the Jekyll site, and deploys both to GitHub Pages.

## Build the CV locally

With a LaTeX distribution installed:

```powershell
latexmk -pdf -output-directory=files/cv files/cv/resume.tex
```

The deployed PDF uses the stable path `files/cv/yfchen_cv.pdf`.

## Preview the website locally

With Ruby and Bundler installed:

```powershell
bundle install
bundle exec jekyll serve --config _config.yml,_config.dev.yml
```

Then open `http://localhost:4000`.
