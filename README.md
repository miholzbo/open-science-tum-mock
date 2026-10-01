# Open Science @ TUM — mock site

A [Zensical](https://zensical.org) skeleton that imitates the look of
<https://www.ub.tum.de/en/open-access>. It is **not an official TUM website**; a banner at
the top of every page says so.

The final site will be a single page serving as central entry point for Open Science
support at TUM. The mock contains two copies of that page, one per layout variant under
discussion:

| Page | Purpose |
| --- | --- |
| `docs/index.md` | Variant A |
| `docs/variant-b.md` | Variant B |

Both share the intro and the draft policy; the content below the
`<!-- Layout variant … -->` marker is where the variants differ.

## Run

```bash
zensical serve -o        # preview on http://localhost:8000
zensical build           # output to site/
```

## Where things live

| Path | Purpose |
| --- | --- |
| `zensical.toml` | site config: navigation, theme features, TUM quicklinks, social links |
| `overrides/main.html` | mock disclaimer banner + dark navy TUM service bar above the header |
| `overrides/partials/header.html` | white TUM branding band (logo, site name, subtitle, search) |
| `overrides/partials/logo.html` | plain-text "TUM" used instead of a logo |
| `overrides/partials/footer.html` | navy TUM service footer (link row + social icons) |
| `docs/stylesheets/tum.css` | all TUM styling, in numbered sections |

## Colour tokens

Taken from `ub.tum.de/themes/custom/barrio_subtheme/css/tum/variables.css`:

| Token | Value | Used for |
| --- | --- | --- |
| `--tum-primary` | `#072140` | service bar, footer, menu level 0 |
| `--tum-secondary` | `#3070b3` | menu level 1, accents, rules, card tops |
| `--tum-blue-mid` | `#14519a` | menu level 2 |
| `--tum-blue-open` | `#0e396e` | active menu item |
| `--tum-link` / `--tum-link-hover` | `#0071b3` / `#018fe2` | body links |
| `--tum-info` | `#f0f5fa` | info box |
| `--tum-contact` | `#dde2e6` | contact box ("Kontaktbox") |

## Content building blocks

The TUM box types map onto admonitions:

| Markdown | Renders as |
| --- | --- |
| `!!! note` | light blue info box |
| `!!! info` | heavy blue-bordered box ("Störer") |
| `!!! tip` | grey-outlined contact box |
| `!!! danger` | solid navy "important" box |

Teaser cards use the `grid cards` block; the "About X ›" links use `{ .tum-more }`.

## Known limitations

- The TUM logo and Neue Helvetica are not included; the site uses Roboto and the plain
  letters "TUM".
- Quicklinks, service menu, language switch and footer links are dummies (`#`).
- Zensical has one navigation sidebar, so the TUM mega-menu / A–Z index is not reproduced.
