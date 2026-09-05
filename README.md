# PKU-PILLAR-Group.github.io

Source of the **PILLAR Group** homepage — an NLP research lab at Peking University. The site is built with [Jekyll](https://jekyllrb.com/) using the [al-folio](https://github.com/alshedivat/al-folio) theme and is deployed to GitHub Pages at <https://pku-pillar-group.github.io>.

**Note:** the site currently ships with placeholder content (people, papers, news). Replace it with real lab information before publicizing the site.

## Common tasks

### Add a publication

Edit [`_bibliography/papers.bib`](_bibliography/papers.bib) and add a BibTeX entry. Useful al-folio fields:

- `abbr={ACL}` — venue badge (colors/links are defined in [`_data/venues.yml`](_data/venues.yml))
- `pdf={https://arxiv.org/abs/...}` — PDF button
- `code={https://github.com/PKU-PILLAR-Group/...}` — code button
- `selected={true}` — show the paper in "selected publications" on the home page

The publications page regenerates automatically from the bib file.

### Add a news item

Create a small Markdown file in [`_news/`](_news/) with front matter like:

```yaml
---
layout: post
date: 2026-09-05 09:00:00+0800
inline: true
related_posts: false
---
```

The newest items appear on the home page and on the [news page](_pages/news.md).

### Edit people

Members are listed on the people page via [`_pages/profiles.md`](_pages/profiles.md). Each entry has a `name`, a `group` (entries sharing the same group appear together under that heading), an `image` in `assets/img/` (currently the template's `prof_pic.jpg` placeholder — replace with real photos), and a short `description` (Markdown supported). To add a member, copy an existing profile block in `profiles.md`.

### Edit other pages

Pages live in [`_pages/`](_pages/): `about.md` (home), `news.md`, `profiles.md` (people), `publications.md`, `join.md`. Site-wide settings (title, email, social links) are in [`_config.yml`](_config.yml).

## Build locally

You need Ruby (3.x recommended) and Bundler. Then:

```bash
bundle install
bundle exec jekyll serve
```

The site is served at <http://localhost:4000>.

Optional: `imagemagick` support (responsive WebP images) is disabled in `_config.yml` because it requires the ImageMagick binary. Install ImageMagick (`brew install imagemagick`) and set `imagemagick.enabled: true` to turn it back on.

## Deploy

Push to the default branch. The GitHub Actions workflow in [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml) builds the site and deploys it to GitHub Pages automatically.

## License

The al-folio theme is MIT-licensed; see [LICENSE](LICENSE).
