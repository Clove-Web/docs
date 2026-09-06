---
order: 60
label: CSS reference
---

Custom CSS lets you style your pages by hand, from **Advanced CSS** in your system's management pages.

It is not quite the CSS you are used to. pkviewer does not serve what you type — it reads your stylesheet, keeps the parts it recognises, and writes out its own version. Anything it does not recognise is skipped and listed back to you with the line number, so a rule that was dropped never looks like a rule that did nothing.

!!!secondary
Nothing here can break your page permanently. Clear the box, save, and you are back to your theme.
!!!

### Selectors are scoped for you

Write `.card`, not `#pkv-user .card`. Every selector is rewritten to apply only inside your page's content, so you cannot accidentally restyle the rest of the site.

```css
.card { border-radius: 18px; }
.identity h1 { letter-spacing: -0.02em; }
```

`html`, `body` and `:root` are refused rather than silently doing nothing — they are where you would reach for a page background, and the [variables below](#variables) are how you set that instead.

### What you can target

These are the parts of a public page:

| Class | What it is |
|---|---|
| `.page` | The whole content column |
| `.identity` | Avatar, name and the details beside them |
| `.avatar`, `.banner` | The images at the top |
| `.meta-list` | ID, pronouns, tag, member count |
| `.prose` | The description |
| `.socials` | Your links |
| `.directory` | The member grid |
| `.member-card` | One member in the grid |
| `.member-card .name` | A member's name |
| `.card-blurb` | A member's short description |
| `.muted` | Secondary text anywhere |

Ordinary element selectors work too: `h1`, `h2`, `p`, `a`, `ul`, `li`, `img`.

### Variables { #variables }

Your theme's settings are available as CSS variables, so you can build on your theme rather than fighting it. Change the colour in **Appearance** and CSS that reads these follows along.

| Variable | What it holds |
|---|---|
| `--pkv-color-page` | Page background |
| `--pkv-color-surface` | Card background |
| `--pkv-color-text` | Text |
| `--pkv-color-muted` | Secondary text |
| `--pkv-color-accent` | Accent |
| `--pkv-color-border` | Lines and borders |
| `--pkv-font-body` | Body typeface |
| `--pkv-font-heading` | Heading typeface |
| `--pkv-font-size` | Base text size |
| `--pkv-radius` | Corner rounding |
| `--pkv-density` | Spacing multiplier |
| `--pkv-avatar-size` | Avatar size |
| `--pkv-avatar-radius` | Avatar corner rounding |
| `--pkv-surface-bg` | Card background, after card style |
| `--pkv-surface-border` | Card border, after card style |

```css
.member-card {
  border: 2px solid var(--pkv-color-accent);
  border-radius: calc(var(--pkv-radius) * 2);
}
```

Spacing steps `--sp-1` through `--sp-12` are also available, and scale with your density setting.

### What is not available

Four things are refused. Each one is a specific problem rather than a general caution.

==- `url()` — no external resources
Stylesheets make no network requests at all.

A background image is a request, and a request tells whoever hosts it the address of everyone who looked at your page. It is also how CSS is used to *read* a page: a selector that matches only certain content, paired with a request, reports back one character at a time.

Use colours, borders and gradients — `linear-gradient()` works fine.
==- `position: absolute` and `fixed`
Only `static` and `relative` are available.

Taking an element out of the flow lets it be laid on top of the page, and a convincing fake sign-in box on a real pkviewer address is the thing this prevents. Use flexbox and grid for layout; both are fully available.
==- `!important`
It is reserved for the rules that keep badges and the site notice in place.

If author CSS could use it, those would become a specificity race that the page eventually loses.
==- Badges and the site notice
Selectors naming `.pkvb` or `.site-footer` are refused.

A [badge](/projects/pkviewer/badges) is pkviewer's statement about a system, and the notice is what stops a third-party site reading as an official one. Neither is part of your page's appearance. See [why badges cannot be faked](/projects/pkviewer/badges).
===

`@media` and `@supports` both work. `@import`, `@font-face` and `@keyframes` do not — the first would pull in a stylesheet nobody checked, and the other two are on the list to look at later.

Anything else not on the supported property list is skipped and reported, rather than applied.

### Fonts

`font-family` accepts any name, but pkviewer only *loads* the typefaces in [Appearance](/projects/pkviewer/appearance). Naming a font that a visitor does not already have falls back to their default, so pick your typeface in Appearance and let CSS use `var(--pkv-font-body)`.

### A worked example

```css
/* Softer cards with an accent edge */
.member-card {
  background-color: var(--pkv-color-surface);
  border: 1px solid var(--pkv-color-border);
  border-left: 3px solid var(--pkv-color-accent);
  border-radius: 4px;
  transition: border-color 150ms ease;
}

.member-card:hover {
  border-color: var(--pkv-color-accent);
}

/* Tighter headings */
.identity h1 {
  font-size: 2.2rem;
  letter-spacing: -0.02em;
  line-height: 1.1;
}

/* Two columns on wide screens */
@media (min-width: 60em) {
  .directory {
    grid-template-columns: repeat(2, 1fr);
  }
}
```

### If something does not apply

The editor lists every skipped line underneath your stylesheet, with the reason. The commonest causes:

- a property that is not on the supported list
- `url()` anywhere in a value
- `!important`
- a selector naming a badge or the site notice
- `html`, `body` or `:root`

A stylesheet with problems still saves, and the rules that are fine still apply. You lose the line, not the page.
