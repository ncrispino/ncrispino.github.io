# Project Notes

## Local Development

This is a Jekyll site (GitHub Pages). To serve locally:

```
eval "$(rbenv init -)" && bundle exec jekyll serve
```

The system Ruby (2.6) is too old — must use rbenv to get Ruby 3.3+ with bundler 2.7.2.

Site will be at http://localhost:4000.

## Structure

- `_posts/` — research publications (category: research) and other posts
- `_layouts/default.html` — main template
- `pdfs/cv.pdf` — CV download
- Posts are sorted by date (newest first)
- Venue field should include the year (no separate year appended by template)
