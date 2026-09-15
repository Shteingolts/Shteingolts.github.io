# shteingolts.github.io

Personal academic page (CV, publications, about) for Sergey A. Shteingolts, built on the
[al-folio](https://github.com/alshedivat/al-folio) Jekyll theme and hosted on GitHub Pages.

## Structure

- `_pages/about.md` — home page bio.
- `_bibliography/papers.bib` — publication list. Add a new paper by appending a BibTeX entry
  (Google Scholar's "Export BibTeX citation" works well). Mark an entry `selected = {true}` to
  also feature it on the home page. `abbr = {...}` shows a small venue badge — see `_data/venues.yml`.
- `_data/cv.yml` — CV content, in [RenderCV](https://docs.rendercv.com/) format. Editing this file
  and pushing auto-renders a PDF via `.github/workflows/render-cv.yml`, linked from the CV page and
  from `_data/socials.yml`'s `cv_pdf`.
- `_data/socials.yml` — contact email, GitHub/ORCID/Google Scholar links, CV PDF path.

The about page currently has no profile photo (the `profile:` block was removed from
`_pages/about.md`). To add one back, drop an image in `assets/img/` and add a `profile:` block
with `image: your-file.jpg` — see the [al-folio about-page docs](https://github.com/alshedivat/al-folio/blob/master/docs/CUSTOMIZE.md).

## Publishing

Push to `main` and `.github/workflows/deploy.yml` builds the site with Jekyll and deploys it to
the `gh-pages` branch. In the repo's Settings → Pages, set the source to the `gh-pages` branch
(first push only).

## Local preview (optional)

Not required to publish — GitHub Actions builds the site for you. If you want to preview changes
locally before pushing, either install Ruby + Bundler and run:

```bash
bundle install
bundle exec jekyll serve
```

or use Docker/Podman:

```bash
docker compose up
```

## Theme docs

For anything beyond what's covered above (more collections, comments, analytics, etc.), see the
upstream [al-folio documentation](https://github.com/alshedivat/al-folio/tree/master/docs) and
[`_config.yml`](_config.yml), which is heavily commented.
