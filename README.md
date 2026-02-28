# Trento Local Minimum — TLM

Website for the TLM ML Journal Club, built with Jekyll and the [SexyJekyll theme](https://github.com/amargiovanni/sexyjekyll-theme). Hosted on GitHub Pages.

## 🌐 Live site

[contessid.github.io/tlm-site](https://contessid.github.io/tlm-site)

---

## ✏️ How to update content quickly

### Add/edit upcoming sessions
Edit `_data/upcoming.yml` directly on GitHub (pencil icon). The table on the homepage updates automatically.

### Add a past speaker
Edit `_data/people.yml` and add an entry under `speakers:`.

### Write a session post
Create a new file in `_posts/` named `YYYY-MM-DD-session-title.md`. Copy the format from `_posts/2025-03-01-session-template.md`.

### Update surveys
Edit `_pages/surveys.md` and paste your Google Form embed codes where indicated.

### Add the Trento photo
Put your image file at `assets/img/trento.jpg`. Recommended size: at least 1200×400px.

---

## 🚀 Local development

```bash
bundle install
bundle exec jekyll serve
```

Open [http://localhost:4000/tlm-site](http://localhost:4000/tlm-site).

---

## 📁 Structure

```
_config.yml          ← site settings
_data/
  upcoming.yml       ← homepage schedule table (edit this often)
  people.yml         ← organizers and speakers
_pages/
  about.md
  people.md
  labs.md
  surveys.md
_posts/              ← one post per session
assets/
  img/trento.jpg     ← add your Trento photo here
  css/tlm-custom.css ← custom styles
```
