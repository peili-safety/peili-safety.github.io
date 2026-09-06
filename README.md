# Pei Li research group website

Jekyll website using the Blotter template from https://github.com/blab/blotter.
The design uses Blotter's Bootstrap grid, navigation, typography, and open lists.
The site's existing Jekyll/GitHub Pages dependencies and public URLs are retained.
See THIRD_PARTY.md for template provenance and license notices.

## Edit content

- `_pages/about.md`: homepage.
- `_data/publications.json`: bibliography, newest first; feeds the homepage, paper index, and individual paper pages.
- `_papers/`: page wrappers that match each publication's `slug` using `paper_id`.
- `_layouts/paper.html`: paper detail layout with citation, abstract or labeled summary, figure, and available resource links.
- `images/papers/`: paper figures; `SOURCES.md` records their provenance.
- `_data/news.json`: announcements, newest first; month-level dates are intentional.
- `_pages/news.html` and `_pages/news-index.html`: full news timeline and compact index, both generated from the same announcements. Existing news anchors remain valid.
- `_data/research.yml`: themes, selected work, projects, and sponsor links.
- `_data/people.yml`: team details. A missing photo uses initials.
- `_pages/pei-li.md`: faculty biography.
- `_pages/lab.md`: team, recruitment, and awards.
- `_posts/`: existing blog tutorials.

Original URLs `/publications/`, `/portfolio/`, `/lab/`, and `/year-archive/` remain canonical.
Blotter-style `/papers/`, `/projects/`, `/team/`, and `/blog/` redirect to them.
Individual publications use `/papers/<slug>/`.

To add a paper, add its bibliography record with a unique `slug`, `page_url`,
and `short_citation`, then copy an existing `_papers/` wrapper and update its
title, `paper_id`, and permalink. Optional fields include `figure`, `figure_alt`,
`figure_caption`, `figure_source`, `abstract`, `abstract_source`, `pdf_url`,
`doi`, `preprint_url`, and `github`. Use `abstract_heading: "Summary"` for editorial
summaries; identify manuscript/preprint abstracts with `abstract_heading` and
`abstract_note`. Keep established slugs stable when updating publication metadata.
Link public PDFs directly; local draft PDFs are not included in the website.

## Add a funded project page

1. Add the project metadata to `_data/research.yml` under `projects`, including a
   unique `id` and a `url` such as `/projects/wisconsin-highway-delay/`. Keep the
   existing period, status, description, sponsor, logo, and optional report fields.
2. Copy `_portfolio/wisconsin-highway-delay.md` to a new Markdown file in
   `_portfolio/`. Set `layout: project`, update `title`, set `project_id` to the
   matching metadata `id`, and set `permalink` to the metadata `url`. Write the
   abstract and any additional sections below the closing `---`.
3. The Research page automatically links the project title and “Project details”
   to its `url`. To link an announcement there too, set that news item's `url` in
   `_data/news.json` to the same project URL.

Project pages use `_layouts/project.html`. Metadata stays in `research.yml`;
the longer project description lives in its Markdown file.

## Build and preview

With the Ruby version supported by Gemfile.lock:

```sh
bundle install
bundle exec jekyll serve
```

CSS is precompiled and tracked, so GitHub Pages does not require Node.
Typography uses locally hosted Lato (regular, italic, bold, and bold italic),
with regular-weight headings for clear rendering. Bedford's original Museo Sans
and Facit Web are Adobe-hosted fonts and are not bundled with the template.
After changing `_blotter/style.scss` or `_blotter/_lab.scss`:

```sh
npm ci
npm run build:css
bundle exec jekyll build --destination /tmp/peili-research-preview
git diff --check
```

Legacy theme sources are retained for reference, but the active layouts load only
`css/style.css` and `js/bootstrap.bundle.min.js`. The prior `assets/css/main.scss`
is excluded from the build. Do not edit it for the new design.
