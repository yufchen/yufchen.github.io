# Yufeng Chen — personal website

This directory contains the Jekyll source for [yufchen.github.io](https://yufchen.github.io/).

## What to edit

- Website profile and links: `_config.yml`
- Homepage: `_pages/about.md`
- Research: `_pages/research.md`
- Publications: `_pages/publications.md`
- Teaching: `_pages/teaching.md`
- Published English CV: `files/cv/yufeng-chen-resume-en.pdf`
- Published Chinese CV (with photo): `files/cv/yufeng-chen-resume-zh-photo.pdf`

## Typical workflow

```powershell
git pull
git switch -c update/site
# edit the website
git status
git add website
git commit -m "Update personal website"
git push -u origin update/site
```

Merge the branch into `master` when the update is ready. GitHub Actions builds this directory and deploys it to GitHub Pages.

The deployed PDFs use stable paths under `files/cv/`. Replace the corresponding English or Chinese PDF when publishing an update.

## Preview the website locally

With Ruby and Bundler installed, run from this directory:

```powershell
bundle install
bundle exec jekyll serve --config _config.yml,_config.dev.yml
```

Then open `http://localhost:4000`.
