# Allergenen

**Lees dit in andere talen:** [English](README.md)

CSS-library met 14 pictogrammen voor de allergenen die volgens bijlage II van Verordening (EU) nr. 1169/2011 op levensmiddelen vermeld moeten worden. De pictogrammen zitten in twee webfonts (vlak en in een cirkel) en worden aangestuurd via SCSS-klassen. Elke allergeen heeft een vaste kleur.

Auteur: M. de Ridder
Licentie: MIT
Repository: https://github.com/matthijsderidder/allergens

## Gebruik

Neem het gebundelde stylesheet op. De fontbestanden worden relatief geladen vanuit `dist/fonts/`, dus laat `dist/css` en `dist/fonts` bij elkaar staan.

```html
<link rel="stylesheet" href="dist/css/allergens.min.css">
```

jsDelivr kan dezelfde bestanden serveren vanuit de publieke GitHub-repository. Relatieve font-URL's worden door de CDN herschreven.

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/matthijsderidder/allergens@v1.0.0/dist/css/allergens.min.css">
```

Laat het pad weg om het standaardbestand uit `package.json` te laden (`jsdelivr`: `dist/css/allergens.min.css`):

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/matthijsderidder/allergens@v1.0.0">
```

`allergens.css` is dezelfde bundel zonder minificatie. Iconen, kleuren en formulierstyles zitten er samen in.

### Pictogrammen

De klasse `ai-{allergeen}` gebruikt het vlakke font (`allergen-icons-plain`). `ai-{allergeen}-circle` gebruikt het cirkelfont (`allergen-icons-circle`).

```html
<i class="ai-gluten"></i>
<i class="ai-gluten-circle"></i>
<i class="ai-milk-circle ac-milk"></i>
```

### Kleuren

`ac-{allergeen}` zet `color` op de kleur van die allergeen.

```html
<span class="ac-fish">Vis</span>
```

### Formulier

Zet `allergen-{allergeen}` op een checkbox direct vóór het label. Het label krijgt het cirkelpictogram; aangevinkt krijgt dat pictogram de allergeenkleur.

```html
<input class="form-check-input allergen-peanuts" type="checkbox" id="peanuts">
<label class="form-check-label" for="peanuts">Pinda's</label>
```

## De 14 allergenen

Volgorde en glyphs komen overeen met bijlage II. Glyphs A–N staan in beide fonts.

| # | Klasse | Allergeen | Kleur | Glyph |
| --- | --- | --- | --- | --- |
| 1 | `gluten` | Glutenbevattende granen | `#bf9e57` | A |
| 2 | `crustaceans` | Schaaldieren | `#e53d6b` | B |
| 3 | `eggs` | Eieren | `#f79a37` | C |
| 4 | `fish` | Vis | `#2887c7` | D |
| 5 | `peanuts` | Pinda's | `#cd6e43` | E |
| 6 | `soybeans` | Soja | `#7aac47` | F |
| 7 | `milk` | Melk | `#73c6ee` | G |
| 8 | `nuts` | Noten | `#855433` | H |
| 9 | `celery` | Selderij | `#28a069` | I |
| 10 | `mustard` | Mosterd | `#d99539` | J |
| 11 | `sesame` | Sesamzaad | `#dcb579` | K |
| 12 | `sulphites` | Zwaveldioxide en sulfieten | `#8767a6` | L |
| 13 | `lupin` | Lupine | `#c57d99` | M |
| 14 | `molluscs` | Weekdieren | `#a89a90` | N |

Klassen blijven Engels, ongeacht de taal van de pagina.

## Voorbeelden

De map `examples/` laat het gebruik zien. Elke pagina laadt `../dist/css/allergens.min.css` en Bootstrap 5.3.8. Engels is de standaard; de Nederlandse pagina heeft het achtervoegsel `.nl`.

- `examples/forms.html`, `forms.nl.html` — checkboxes met de cirkelpictogrammen
- `examples/allergens.html`, `allergens.nl.html` — kaarten en een accordion met de namen en omschrijvingen uit bijlage II
- `examples/dish.html` — formulier voor een gerecht, met de allergeen-checkboxes

## Indeling

```text
src/                  bron
  icons/              14 SVG-pictogrammen, 16×16, fill currentColor
  allergen-icons.svg  verzameling van de pictogrammen
  scss/               SCSS-entrypoint en partials
dist/                 publiceerbare output
  css/                css en min.css
  fonts/              woff2, woff, en de otf/ttf-collectie
examples/             HTML die naar dist/css verwijst
```

`src/scss/allergens.scss` is het entrypoint en importeert variabelen, iconen, kleuren en formulierstyles. Font-URL's in de CSS zijn relatief (`../fonts/`), gerekend vanaf `dist/css/`.

## Licentie

MIT. Zie [LICENSE](LICENSE).
