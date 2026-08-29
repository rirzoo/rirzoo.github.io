# Romir @TheLanding

Personal site — books read (Marginalia), things built (Projects), topics
learned toward explaining unaided (Primers), and unstructured thinking
(Ramblings). Built with [Zola](https://www.getzola.org/) on the
[Apollo](https://github.com/not-matthias/apollo) theme, vendored into
`themes/apollo/` and used as shipped — default palette, default fonts,
no restyling. Requires Zola 0.23+ (this machine's `zola` is 0.23.4).

Only these are site-specific; everything else in `themes/apollo/` is the
theme unmodified:

- `config.toml` — content, nav menu, social links, `extra.theme = "dark"`
  (the theme's own built-in dark-only mode, not a custom override)
- `content/` — all the writing
- `templates/landing.html` — new file: homepage bio blurb plus a "Latest"
  feed pulling the 2 most recent entries from each section (Apollo's
  default homepage is just a static blurb with no content list)
- `templates/marginalia_section.html` — new file (extends the theme's own
  `section.html`) implementing the one custom behavior Marginalia needs:
  a book's title links to its review only when one exists

## Local preview

```
zola serve
```

Opens at `http://127.0.0.1:1111` with live reload.

```
zola build
```

Builds the site into `public/` (gitignored — CI does its own build on
deploy, this is just for local sanity-checking).

## Adding content

- **Marginalia** (`content/marginalia/`): set `extra.reviewed = true` and
  write the review as the file body, or `extra.reviewed = false` and
  leave the body empty for a book with no review yet — it still appears
  in the list, just as plain text instead of a link. `description` is
  used as the byline (e.g. `"by Author Name"`).
- **Projects** (`content/projects/`): set `weight` to control display
  order (lower first).
- **Primers** / **Ramblings**: `title` + `date` (+ optional
  `description` for the listing blurb), sorted newest first
  automatically.

Delete the `example-*` files in each section once you have real entries.

## Deploying

Push to `main` — `.github/workflows/deploy.yml` builds with Zola 0.23.4
and publishes to GitHub Pages automatically. One-time setup required in
the GitHub UI: **Settings → Pages → Build and deployment → Source =
"GitHub Actions."**
