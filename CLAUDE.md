# TLM — Trento Local Minimum

ML Journal Club website built with Jekyll + GitHub Pages.

## Tech Stack

- **Jekyll 4.3** with the [SexyJekyll](https://github.com/amargiovanni/sexyjekyll-theme) remote theme
- GitHub Pages deployment via Actions (`.github/workflows/deploy.yml`)
- Ruby 3.2, Bundler

## Project Structure

```
_config.yml            # Site settings, theme, hero, navigation
_data/
  upcoming.yml         # Homepage schedule table (most frequently edited file)
  people.yml           # Organizers and past speakers
_pages/
  about.md             # About the club
  people.md            # People listing (reads from people.yml)
  labs.md              # Lab descriptions and past labs table
  surveys.md           # Google Form embeds (vote, propose, feedback)
_posts/                # One post per session (YYYY-MM-DD-session-title.md)
assets/
  css/tlm-custom.css   # Custom styles overriding the theme
  img/                 # Images (trento.jpg banner)
index.md               # Homepage: banner + upcoming sessions table
```

## Key Conventions

- **Session posts** go in `_posts/` as `YYYY-MM-DD-session-title.md` with front matter: `layout: post`, `title`, `subtitle`, `date`, `categories: session`, `tags: [...]`, `toc: true`. Follow the format in `_posts/2025-03-01-session-template.md`.
- **Pages** in `_pages/` use `layout: default` with a `permalink`.
- **Upcoming sessions** are edited in `_data/upcoming.yml`. Each entry has `date`, `type` (talk/lab), `title`, and optional `speaker`, `paper`, `paper_url`, `repo_url`, `notes`.
- **Speakers** are added to `_data/people.yml` under `speakers:` with `name`, `affiliation`, `talk`, `date`, `slides_url`, `session_url`.
- HTML is used inline in Markdown files for structured sections (tables, cards, embeds) with Liquid `{% %}` templating.
- CSS uses `var(--color-*)` custom properties from the theme with fallbacks. Dark mode via `prefers-color-scheme: dark`.

## Local Development

```bash
bundle install
bundle exec jekyll serve
# → http://localhost:4000/tlm-site
```

## Deployment

Push to `main` triggers the GitHub Actions workflow which builds and deploys to GitHub Pages at `contessid.github.io/tlm-site`.

## When Editing

- Content changes (sessions, people, schedule): edit YAML data files or Markdown pages directly.
- Style changes: edit `assets/css/tlm-custom.css`. Use the theme's CSS variables where possible.
- Do not modify the theme itself — override via `tlm-custom.css` or `_config.yml`.
- Keep `_config.yml` `exclude:` list updated if adding non-site files to the repo.
