---
version: alpha
name: Romir @TheLanding
description: The design language of rirzoo.github.io, a dark, text-first personal log built on Zola's Apollo theme. Near-black canvas, light-grey type, one coral-red accent that marks headings, links and selection, and almost nothing else.

colors:
  primary: "#ef5350"
  on-primary: "#ffffff"
  canvas: "#121212"
  surface: "#1f1f1f"
  surface-raised: "#383838"
  hairline: "#383838"
  ink: "#f0f0f0"
  ink-muted: "#ababab"
  ink-faint: "#787878"
  meta: "#999999"
  quote: "#737373"
  table-rule: "#dfe2e5"
  code-highlight: "#2b3846"
  code-label: "#333333"

typography:
  page-header:
    fontFamily: ZedTextFtl
    fontSize: 40px
    fontWeight: 400
    lineHeight: 1.0
    letterSpacing: 0
  heading:
    fontFamily: ZedTextFtl
    fontSize: 19.2px
    fontWeight: 700
    lineHeight: 1.5
    letterSpacing: 0
  list-title:
    fontFamily: ZedTextFtl
    fontSize: 19.2px
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: 0
  site-title:
    fontFamily: ZedTextFtl
    fontSize: 24px
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: 0
  body-md:
    fontFamily: ZedTextFtl
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: 0
  date:
    fontFamily: Jetbrains Mono
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: 0
  code:
    fontFamily: Jetbrains Mono
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.4
    letterSpacing: 0
  code-label:
    fontFamily: ZedTextFtl
    fontSize: 12px
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: 0.4px
  small:
    fontFamily: ZedTextFtl
    fontSize: 12px
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: 0

rounded:
  xs: 4px
  sm: 5px
  md: 6px
  lg: 8px
  xl: 10px

spacing:
  xxs: 4px
  xs: 8px
  sm: 12px
  md: 16px
  lg: 24px
  xl: 32px
  xxl: 64px

components:
  nav-bar:
    backgroundColor: "{colors.canvas}"
    textColor: "{colors.ink}"
    typography: "{typography.body-md}"
    padding: 0
  page-header:
    textColor: "{colors.ink}"
    typography: "{typography.page-header}"
    margin: 64px 0 16px 0
  heading:
    textColor: "{colors.ink}"
    prefixColor: "{colors.primary}"
    typography: "{typography.heading}"
  link-inline:
    textColor: "{colors.ink}"
    underline: "2px solid {colors.primary}"
  link-inline-hover:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
  post-list-row:
    textColor: "{colors.ink}"
    dateTypography: "{typography.date}"
    dateColor: "{colors.ink-muted}"
    titleTypography: "{typography.list-title}"
    metaColor: "{colors.meta}"
    gap: "{spacing.md}"
  marginalia-row:
    textColor: "{colors.ink}"
    titleTypography: "{typography.list-title}"
    metaColor: "{colors.meta}"
  blockquote:
    textColor: "{colors.quote}"
    borderLeft: "3px solid {colors.primary}"
    padding: 0 0 0 16px
  code-inline:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.ink}"
    borderColor: "{colors.hairline}"
    typography: "{typography.code}"
    rounded: "{rounded.sm}"
    padding: 0.1em 0.2em
  code-block:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.ink}"
    borderColor: "{colors.hairline}"
    typography: "{typography.code}"
    rounded: "{rounded.sm}"
    padding: "{spacing.md}"
  code-label:
    backgroundColor: "{colors.code-label}"
    textColor: "#f0f0f0"
    typography: "{typography.code-label}"
    rounded: 0 0 4px 4px
  note:
    headerBackground: "{colors.surface-raised}"
    contentBackground: "{colors.surface}"
    textColor: "{colors.ink}"
    borderLeft: "3px solid {colors.primary}"
    rounded: "{rounded.xs}"
    padding: 10px 20px
  table-cell:
    borderColor: "{colors.table-rule}"
    padding: 6px 13px
  draft-label:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.xs}"
    padding: 2px 4px
  icon-button:
    backgroundColor: "{colors.surface-raised}"
    borderColor: "{colors.hairline}"
    typography: "{typography.small}"
    rounded: "{rounded.md}"
    padding: 4px 8px
  image:
    rounded: "{rounded.lg}"

---


## Overview

The site reads like a terminal that learned some manners. It sits on a flat near-black canvas, `{colors.canvas}` (#121212). There are no gradients, no shadows and no hero image. Body text is light grey `{colors.ink}` (#f0f0f0) in Zed's text face, and the page is held to a 920px column so long reading stays comfortable.

There is one colour that isn't grey: a coral red, `{colors.primary}` (#ef5350). It shows up as the Markdown-style `#` prefix on every heading, the 2px underline under links in body text, the full background when you hover a link, the left rule on blockquotes and notes, and the text-selection highlight. The heading prefix tells you what kind of site this is. Headings look like the Markdown they were written in.

Structure comes from type and whitespace alone. Lists are rows of date, title and a single meta line, with no boxes around them. The only bordered surfaces are code blocks, notes and tables, which are things you'd expect to look like objects.

**Key Characteristics:**
- Flat `{colors.canvas}` near-black, dark mode only
- A three-step grey ramp for text (`{colors.ink}`, `{colors.ink-muted}`, `{colors.ink-faint}`) and three for surfaces (`{colors.canvas}`, `{colors.surface}`, `{colors.surface-raised}`)
- A single accent, `{colors.primary}`, for headings, links, rules and selection
- Headings prefixed with literal `#`, `##`, `###` in the accent colour
- Monospace dates (`{typography.date}`) leading every list row
- No elevation of any kind; borders do all the separating

## Colors

> Source: `themes/apollo/sass/theme/dark.scss` (compiled values from `public/theme/dark.css`), plus hard-coded values in `themes/apollo/sass/parts/`. `config.toml` sets `theme = "dark"`, so the light palette never loads.

### Brand & Accent
- **Coral** (`{colors.primary}`, #ef5350): heading prefixes, inline-link underline, link hover fill, blockquote and note left rule, `<del>` strike line, text selection, draft label. Nothing else gets it.
- **White** (`{colors.on-primary}`, #ffffff): text on top of a coral fill (link hover, selection, draft label).

### Surface
- **Canvas** (`{colors.canvas}`, #121212): page background. `$bg-0` in the theme.
- **Surface** (`{colors.surface}`, #1f1f1f): code blocks, inline code, note body. `$bg-1`, which is canvas lightened 5%.
- **Surface Raised** (`{colors.surface-raised}`, #383838): note header, icon buttons. `$bg-2`, a further 10% lighter.
- **Hairline** (`{colors.hairline}`, #383838): 1px borders on code, `<hr>`. Same value as Surface Raised; the theme aliases `--border-color` to `--bg-2`.

### Text
- **Ink** (`{colors.ink}`, #f0f0f0): body copy, titles, headings.
- **Muted** (`{colors.ink-muted}`, #ababab): `<time>` elements, dates in lists.
- **Faint** (`{colors.ink-faint}`, #787878): defined as `--text-2`, currently unused by any rule on the site.
- **Meta** (`{colors.meta}`, #999999): descriptions under list titles, the "Posted on" line. Hard-coded in `_header.scss`, outside the ramp.
- **Quote** (`{colors.quote}`, #737373): blockquote text. Hard-coded in `_misc.scss`.

### Semantic
There is no success, warning or error palette. A blog doesn't need one. `{colors.code-highlight}` (#2b3846) is the only extra tint, used for highlighted lines in code blocks.

**Known off-palette value:** table borders use `{colors.table-rule}` (#dfe2e5), a light-theme grey that shows up as bright white lines on the dark canvas. If tables start appearing in posts, this is the first thing to override.

## Typography

### Font Family
- **ZedTextFtl** (Zed Text, Regular 400 and Bold 700, woff2): everything that isn't code or a date.
- **Jetbrains Mono** (Regular 400 and Bold 700 loaded, ttf): dates in lists, inline code, code blocks.
- **ZedDisplayFtl** (Zed Display Heavy) and **Space Grotesk** are loaded by `fonts.scss` but never actually render. See the note below.

Fonts are served from `themes/apollo/static/fonts/`; `use_cdn` is off.

### Hierarchy

| Token | Size | Weight | Line Height | Letter Spacing | Use |
|---|---|---|---|---|---|
| `{typography.page-header}` | 40px (2.5em) | 400 | 1.0 | 0 | Section and page titles, "Latest" on the landing page |
| `{typography.site-title}` | 24px (1.5rem) | 400 | 1.5 | 0 | "Romir @TheLanding" in the nav |
| `{typography.heading}` | 19.2px (1.2rem) | 700 | 1.5 | 0 | All of h1 to h6 in body content, all the same size |
| `{typography.list-title}` | 19.2px (1.2rem) | 400 | 1.5 | 0 | Titles in post-list and marginalia rows |
| `{typography.body-md}` | 16px | 400 | 1.5 | 0 | Body copy, nav links, meta lines |
| `{typography.date}` | 16px | 400 | 1.5 | 0 | `<time>` in list rows |
| `{typography.code}` | 16px | 400 | 1.4 (blocks) | 0 | Inline and block code |
| `{typography.code-label}` | 12px | 400 | 1.5 | 0.4px, uppercase | Language tag on code blocks |
| `{typography.small}` | 12px (0.75rem) | 400 | 1.5 | 0 | Icon buttons |

The whole scale shrinks with the viewport: html font size is 97% below 992px, 95% below 768px, 92% below 576px.

### Principles
Two sizes do almost all the work: 40px for the page title and 16px for everything else. Content headings are only 1.2rem. They're set apart by weight and the coral `#` prefix, and size barely changes, so a post never gets a wall of big headings. Monospace is kept for things that are literally code or data, meaning code and dates.

### Note on Font Substitutes
`--header-font` in `themes/apollo/sass/main.scss` is written as `"ZedDisplayFtl" "Space Grotesk", "Helvetica", sans-serif`, with a missing comma after the first family. Under the CSS spec that makes the value invalid wherever it's used, so `font-family` falls back to the inherited ZedTextFtl. In practice, headings and page titles render in Zed Text, not Zed Display. The tokens above describe what renders. To get Zed Display Heavy on headings, add the comma in an override; that would be a visible change to every page title.

If Zed fonts are unavailable, Inter is a close substitute for Zed Text, and any monospace with similar metrics (Fira Code, IBM Plex Mono) can stand in for Jetbrains Mono.

## Layout

### Spacing System
The theme doesn't define a spacing scale. The tokens above are the values that actually occur, rounded to the nearest step:
- `{spacing.xxs}` 4px: icon-button padding, gap between note title and icon
- `{spacing.xs}` 8px: list-row bottom margin (0.5rem), gap between social icons, nav link right margin
- `{spacing.sm}` 12px: gap between site title and socials
- `{spacing.md}` 16px: date-to-title gap in list rows, code-block padding, blockquote indent, page-header bottom margin
- `{spacing.lg}` 24px: bottom padding under the content column (1.5rem)
- `{spacing.xl}` 32px: heading top margin (2em of 16px)
- `{spacing.xxl}` 64px: page-header top margin (4rem)

### Grid & Container
`body` is a flex row with three columns. `.left-content` and `.right-content` flex equally on either side of `.content`, which is capped at `--page-width: 920px`. The side columns are empty on this site; they exist for Apollo's table of contents (`toc = false`). Body padding is 0.9rem (about 14px) on all sides.

### Whitespace Philosophy
Large gaps sit above page titles (64px) and above headings (2em). Inside lists, rows sit only 8px apart, so a list reads as one block of text. There are no section bands or dividers between parts of a page. A new `page-header` is the only thing that marks a new section.

### Responsive Strategy

#### Breakpoints

| Name | Width | What changes |
|---|---|---|
| Desktop | ≥ 992px | Three-column body; base font 16px |
| Laptop | < 992px | Single column; font 97% |
| Tablet | < 768px | Font 95% |
| List stack | < 640px | Post-list rows stack date above title, with 1.6rem vertical margin |
| Nav stack | < 600px | Nav switches to a column: title and socials above menu links |
| Phone | < 576px | Font 92% |

#### Touch Targets
Nav links and social icons are small (16px icons, text links with 0.5em spacing). That's acceptable for a reading site but under the usual 44px target. If interactive elements are added, give them more padding than the nav.

#### Collapsing Strategy
Nothing hides. The nav wraps and then stacks, list rows stack, and the type scales down a few percent. There is no hamburger menu.

#### Image Behavior
`img` is `max-width: 100%` with `{rounded.lg}` corners. Inside `figure`, images cap at 500px tall and get 40px horizontal padding above 600px.

## Elevation & Depth

| Level | Treatment | Use |
|---|---|---|
| 0 | Flat `{colors.canvas}`, no border | Page, lists, nav |
| 1 | `{colors.surface}` fill + 1px `{colors.hairline}` border | Code blocks, inline code |
| 2 | `{colors.surface-raised}` header over `{colors.surface}` body, 3px coral left rule | Notes |

There are no box-shadows anywhere in the theme. Depth only ever comes from one grey step lighter, plus a border.

### Decorative Depth
None. The coral `#` heading prefix and the coral link underline are the only decoration.

## Shapes

### Border Radius Scale

| Token | Value | Use |
|---|---|---|
| `{rounded.xs}` | 4px | Notes, draft label, code-label bottom corners |
| `{rounded.sm}` | 5px | Inline code, code blocks |
| `{rounded.md}` | 6px | Icon buttons |
| `{rounded.lg}` | 8px | Images (0.5rem) |
| `{rounded.xl}` | 10px | Apollo cards (not used on this site yet) |

Corners are small everywhere. Nothing is pill-shaped.

### Photography Geometry
No photography is in use yet. Images inherit `{rounded.lg}` and sit inline in the text column. A `figure` caption is an `h4` prefixed with `↳ `.

## Components

> Each component below points to where it's defined. Overrides belong in the site's own `templates/` (and a root `sass/` if one is added), never in `themes/apollo/`.

### Navigation

**`nav-bar`**: `themes/apollo/templates/partials/nav.html`, styled in `_header.scss`
- Left: site title as a plain link at `{typography.site-title}`, followed by 16px social icons (GitHub, email), inverted to white. Right: the four menu links from `config.toml` (Marginalia, Projects, Primers, Ramblings) at `{typography.body-md}`, 0.5em apart. No background or border. Links outside `main` have no underline and only show the coral fill on hover. The theme toggle and search button are both hidden because `theme = "dark"` and `build_search_index = false`.

### Text

**`page-header`**: `.page-header`, used through the `post.page_header` component
- `{typography.page-header}`, 64px above and 16px below. This is the title of every section and page, and the "Latest" label on the landing page. It has no `#` prefix because it's a `div`, not a heading.

**`heading`**: h1 to h6 inside content
- `{typography.heading}` with a literal prefix (`# `, `## `, `### `, and so on) in `{colors.primary}`, 2em top margin. Every level is the same size; only the number of `#` characters shows the level.

**`link-inline`** / **`link-inline-hover`**: `a` inside `main`
- Default: ink text with a 2px coral bottom border. Hover: coral background, white text. Links in `.meta`, cards and heading anchors drop the underline. Links outside `main` (nav, socials) never underline.

**`blockquote`**
- `{colors.quote}` text, 3px coral left border, 1em left padding, no background.

**`hr`**: 1.2rem vertical margin in the hairline colour.

### Lists

**`post-list-row`**: `.post-list .list-item`, via `post.list_post` or inlined in `templates/landing.html`
- A two-column grid: `<time>` in `{typography.date}` / `{colors.ink-muted}` on the left, then the title in `{typography.list-title}` with a meta description line in `{colors.meta}` on the right. 16px column gap, 8px between rows. Stacks below 640px. Projects with `extra.link_to` get a `↗` after the title and link off-site.

**`marginalia-row`**: `templates/marginalia_section.html`
- Same chrome as `post-list-row`, but books have no date, so the title takes the full row. The description holds "by Author", with "· reading now" appended when `extra.reading` is set. The title only becomes a link when `extra.reviewed = true`. Unreviewed books are plain text, so an underline means "there's a review here." Rows are sorted by description, which groups them by author.

**Landing "Latest" feed**: `templates/landing.html`
- The intro paragraph, then a "Latest" `page-header`, then up to two `post-list-row`s per section, each title prefixed with its section name ("Projects — Mus"). Marginalia only feeds reviewed books into this list.

### Code

**`code-inline`**: `{colors.surface}` fill, 1px hairline border, `{rounded.sm}`, Jetbrains Mono. Inside a hovered link it takes the coral fill and loses its border.

**`code-block`**: `pre`, with highlighting from Giallo (`github-dark`, class-based)
- `{colors.surface}` fill, 1px hairline border, `{rounded.sm}`, 1em padding, 1.4 line-height, horizontal scroll. `fancy_code = true` adds a copy button in the bottom-right corner and a **`code-label`** language tag in the top-right corner (12px uppercase, coloured per language; the full map is in `_code.scss`). Highlighted lines use `{colors.code-highlight}`.

### Callouts & Tables

**`note`**: `{% note(header="...") %}` shortcode, `themes/apollo/templates/components/note.html`
- A `{colors.surface-raised}` header row with a coral `✎` icon, over a `{colors.surface}` body. 3px coral left rule, `{rounded.xs}` corners. The `clickable` and `hidden` options turn it into a collapsible with a `▼` marker, but that needs `dynamic_note = true` in config, which is currently off.

**`table-cell`**: 6px by 13px padding, 1px `{colors.table-rule}` borders, `th` at `font-size: large`. See the off-palette note under Colors.

### Signature Components

**Markdown heading prefix**: the coral `#` in front of every heading. This is the most recognisable element of the site, and anything new should keep it.

**`draft-label`**: a small coral tag reading "DRAFT" beside the titles of draft posts. It appears only on `zola serve --drafts`.

**`icon-button`**: `.icon-button` in `_components.scss`. A 12px label with a 16px icon on `{colors.surface-raised}`, 1px border, `{rounded.md}`. Apollo uses it for card links. It's available here but unused.

## Where Things Live

| What | Path |
|---|---|
| Site config (menu, socials, theme mode) | `config.toml` |
| Site-specific templates | `templates/landing.html`, `templates/marginalia_section.html` |
| Theme templates (don't edit; override by copying to `templates/`) | `themes/apollo/templates/` |
| Colour tokens | `themes/apollo/sass/theme/dark.scss` |
| Fonts, page width, layout | `themes/apollo/sass/main.scss`, `fonts.scss` |
| Component styles | `themes/apollo/sass/parts/_*.scss` |
| Fonts and icons | `themes/apollo/static/fonts/`, `themes/apollo/static/icons/` |

To change a token, override it rather than editing the theme. Add a stylesheet under `static/` and list it in `config.toml` under `extra.stylesheets`. It loads after `main.css`, so a `:root.dark { --primary-color: … }` block there wins.

## Do's and Don'ts

### Do
- Keep `{colors.primary}` for headings' `#` prefix, inline links, rules and selection.
- Use the grey ramp for hierarchy: `{colors.ink}` for content, `{colors.ink-muted}` for dates, `{colors.meta}` for descriptions.
- Build new list pages from `post-list-row`: date (or nothing), then title, then one meta line.
- Make a title a link only when there's somewhere to go. Marginalia relies on this.
- Prefix list titles on the landing page with their section name.
- Override theme files from the site root (`templates/`, `extra.stylesheets`) so `themes/apollo` stays pristine.

### Don't
- Don't add a second accent colour. Language colours on code labels are the only exception.
- Don't add shadows, gradients or background bands. Separate things with a grey step and a hairline.
- Don't make content headings bigger to show hierarchy. The `#` count already does that.
- Don't box list rows in cards. Rows are plain text on the canvas.
- Don't use monospace for prose or labels. It's for code and dates.
- Don't put pill radii on anything. Corners stay between 4px and 10px.
