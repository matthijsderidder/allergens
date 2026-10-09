# Allergens

**Read this in other languages:** [Nederlands](README.nl.md)

CSS library with 14 icons for the allergens that must be declared on food under Annex II of Regulation (EU) No 1169/2011. The icons are two webfonts (plain and circled) and are applied with SCSS classes. Each allergen has a fixed color.

Author: M. de Ridder
License: MIT
Repository: https://github.com/matthijsderidder/allergens

## Usage

Include the bundled stylesheet. Font files are loaded relatively from `dist/fonts/`, so keep `dist/css` and `dist/fonts` together.

```html
<link rel="stylesheet" href="dist/css/allergens.min.css">
```

jsDelivr can serve the same files from the public GitHub repository. Relative font URLs are rewritten by the CDN.

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/matthijsderidder/allergens@v1.0.0/dist/css/allergens.min.css">
```

Omit the path to load the default file from `package.json` (`jsdelivr`: `dist/css/allergens.min.css`):

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/matthijsderidder/allergens@v1.0.0">
```

The package is also published on [npm](https://www.npmjs.com/package/allergens). jsDelivr serves that copy as well:

```bash
npm install allergens
```

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/allergens@1.0.1">
```

`allergens.css` is the same bundle without minification. Icons, colors, and form styles are combined in it.

### Icons

The class `ai-{allergen}` uses the plain font (`allergen-icons-plain`). `ai-{allergen}-circle` uses the circled font (`allergen-icons-circle`).

```html
<i class="ai-gluten"></i>
<i class="ai-gluten-circle"></i>
<i class="ai-milk-circle ac-milk"></i>
```

### Colors

`ac-{allergen}` sets `color` to that allergen's color.

```html
<span class="ac-fish">Fish</span>
```

### Forms

Put `allergen-{allergen}` on a checkbox immediately before its label. The label gets the circled icon; when checked, that icon uses the allergen color.

```html
<input class="form-check-input allergen-peanuts" type="checkbox" id="peanuts">
<label class="form-check-label" for="peanuts">Peanuts</label>
```

## The 14 allergens

Order and glyphs follow Annex II. Glyphs A–N are in both fonts.

| # | Class | Allergen | Color | Glyph |
| --- | --- | --- | --- | --- |
| 1 | `gluten` | Cereals containing gluten | `#bf9e57` | A |
| 2 | `crustaceans` | Crustaceans | `#e53d6b` | B |
| 3 | `eggs` | Eggs | `#f79a37` | C |
| 4 | `fish` | Fish | `#2887c7` | D |
| 5 | `peanuts` | Peanuts | `#cd6e43` | E |
| 6 | `soybeans` | Soybeans | `#7aac47` | F |
| 7 | `milk` | Milk | `#73c6ee` | G |
| 8 | `nuts` | Nuts | `#855433` | H |
| 9 | `celery` | Celery | `#28a069` | I |
| 10 | `mustard` | Mustard | `#d99539` | J |
| 11 | `sesame` | Sesame seeds | `#dcb579` | K |
| 12 | `sulphites` | Sulphur dioxide and sulphites | `#8767a6` | L |
| 13 | `lupin` | Lupin | `#c57d99` | M |
| 14 | `molluscs` | Molluscs | `#a89a90` | N |

Class names stay English, whatever language the page is in.

## Examples

The `examples/` directory shows how to use the library. Each page loads `../dist/css/allergens.min.css` and Bootstrap 5.3.8. English is the default; the Dutch page uses the `.nl` suffix.

- [examples/forms.html](examples/forms.html), [forms.nl.html](examples/forms.nl.html) — checkboxes with the circled icons
- [examples/allergens.html](examples/allergens.html), [allergens.nl.html](examples/allergens.nl.html) — cards and an accordion with the names and descriptions from Annex II
- [examples/dish.html](examples/dish.html), [dish.nl.html](examples/dish.nl.html) — menu dish form with the allergen checkboxes

## Layout

```text
src/                  source
  icons/              14 SVG icons, 16×16, fill currentColor
  allergen-icons.svg  icon collection
  scss/               SCSS entrypoint and partials
dist/                 published output
  css/                css and min.css
  fonts/              woff2, woff, and the otf/ttf collection
examples/             HTML that points at dist/css
```

`src/scss/allergens.scss` is the entrypoint and loads variables, icons, colors, and form styles. Font URLs in the CSS are relative (`../fonts/`), resolved from `dist/css/`.

## License

MIT. See [LICENSE](LICENSE).
