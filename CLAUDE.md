# microplastic-food.org

Public website of the CORNET research projects "microplastic@food" (MP1) and its follow-up "MICROPLEXFOOD" (MP2, finished June 2026), run by ecoplus (Lebensmittel Cluster Niederösterreich).
Hosted on GitHub Pages (`ecoplus-noe/microplastic-food.org`, branch `master`, custom domain via `CNAME`). Pushing to `master` publishes.

## Workflow: edit the HTML here directly

Plain static HTML, no build step. Edit the pages in this repo.

The sibling `../microplastic-food.dev` (React/Markdown generator, 2021 toolchain) is **archived** since 2026-11. Do not use it; its content is out of date.

Shared markup (nav, header, photo credit `<small>`) is repeated in every page. A change to it must be made in all 14 page files.

## Languages

- German is the default and sits at the root: `/index.html`, `/forschung.html`, ...
- English sits under `/en/` with the **same German file names**: `/en/forschung.html`, `/en/aktuelles.html`
- Pages: `index`, `forschung`, `arbeitsplan`, `partner`, `literatur`, `aktuelles`, `impressum`
- Every content change goes into both the DE and the EN file. Afterwards compare the pair (e.g. `diff literatur.html en/literatur.html` must only show translated text).

## Conventions

- Links are root-absolute (`/docs/...`, `/images/...`); no `<base>` tag. External links use `target="_blank"` (text) or `target="extern"` (logos).
- Downloads (PDFs) go in `docs/`, named `YYYY-MM-DD_Title-<lang>.pdf`. Rename instead of overwriting when a file changes, because the old file stays in browser and CDN caches. The guidelines are password-protected PDFs.
- Logos: partners in `images/logos/`, funders in `images/funders/`. Home page partner logos are in `.logos`, funder logos in `section.side`.
- News entries (`aktuelles`) are `<section>` blocks with an `<h4>d.m.yyyy</h4>` date, newest first.
- Literature entries are `<p>YEAR <a ...>Title</a></p>`, grouped by `<h3>` category, newest first; title and link only, no author list.
- CSS: edit `css/styles.scss` and mirror the change by hand in `css/styles.css` (both committed). Recompiling with `sass` works but reformats the whole file.
- Indentation and line wrapping follow prettier's HTML style (2 spaces, `</a\n>` breaks).

## Check a change locally

`python -m http.server 8765` in the repo root, then open http://127.0.0.1:8765/. Headless screenshots: `chrome --headless=new --screenshot=out.png --window-size=1100,2400 <url>`.

## Related repos

`../microplastic-food.com`, `.eu`, `.net` only redirect to microplastic-food.org (keeping the path). They rarely need changes.

## Input material

`issues/` (untracked) holds material from the product owner (docx with text changes, logos, PDFs). It is input, not site content; do not commit or publish it as is.
