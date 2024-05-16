CSS reference
=============

Use this **CSS reference** to browse an [alphabetical index](#index) of
all of the standard
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) properties,
[pseudo-classes](pseudo-classes.md), [pseudo-elements](pseudo-elements.md),
[data types](css_types.md), [functional notations](css_functions.md) and
[at-rules](at-rule.md). You can also browse [key CSS concepts](#concepts)
and a list of [selectors organized by type](#selectors). Also included
is a brief [DOM-CSS / CSSOM reference](#dom-css_cssom).

Basic rule syntax
-----------------

### Style rule syntax

[css]

```css
style-rule ::=
    selectors-list {
      properties-list
    }
```

Where:

[css]

```css
selectors-list ::=
    selector[:pseudo-class] [::pseudo-element]
    [, selectors-list]

properties-list ::=
    [property : value] [; properties-list]
```

See the index of [*selectors*](#selectors), [*pseudo-classes*](#pseudo),
and *[pseudo-elements](#pseudo)* below. The syntax for each specified
*value* depends on the data type defined for each specified *property*.

#### Style rule examples

[css]

```css
strong {
  color: red;
}

div.menu-bar li:hover > ul {
  display: block;
}
```

For a beginner-level introduction to the syntax of selectors, see our
[guide on CSS
Selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors).
Be aware that any [syntax](_Resources/Markup%20And%20Styling/css/syntax.md) error in a rule definition
invalidates the entire rule. Invalid rules are ignored by the browser.
Note that CSS rule definitions are entirely
([ASCII](https://developer.mozilla.org/en-US/docs/Glossary/ASCII))
[text-based](https://www.w3.org/TR/css-syntax-3/#intro), whereas DOM-CSS
/ CSSOM (the rule management system) is
[object-based](https://www.w3.org/TR/cssom/#introduction).

### At-rule syntax

As the structure of at-rules varies widely, please see
[At-rule](at-rule.md) to find the syntax of the specific one you want.

Index
-----

**Note:** This index does not include SVG-exclusive [presentation
attributes](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/Presentation),
which can be used as CSS properties on
[SVG](https://developer.mozilla.org/en-US/docs/Web/SVG) elements.

**Note:** The property names in this index do **not** include the
JavaScript names which do differ from the CSS standard names.

### -

- [`--*`](--*)
- [`-webkit-line-clamp`](-webkit-line-clamp.md)

### A

- [`abs()`](abs.md)
- [[abs|abs()]]
- [`accent-color`](accent-color.md)
- [`acos()`](acos.md)
- [`:active`](:active) [[active]]
- [`additive-symbols (@counter-style)`](additive-symbols.md)
- [`::after (:after)`](::after)
- [`align-content`](align-content.md)
- [`align-items`](align-items.md)
- [`align-self`](align-self.md)
- [`align-tracks`](align-tracks.md)
- [`all`](all.md)
- [`<an-plus-b>`]
- [`<angle>`](angle.md)
- [`<angle-percentage>`](angle-percentage.md)
- [`animation`](animation.md)
- [`animation-composition`](animation-composition.md)
- [`animation-delay`](animation-delay.md)
- [`animation-direction`](animation-direction.md)
- [`animation-duration`](animation-duration.md)
- [`animation-fill-mode`](animation-fill-mode.md)
- [`animation-iteration-count`](animation-iteration-count.md)
- [`animation-name`](animation-name.md)
- [`animation-play-state`](animation-play-state.md)
- [`animation-range`](animation-range.md)
- [`animation-range-end`](animation-range-end.md)
- [`animation-range-start`](animation-range-start.md)
- [`animation-timeline`](animation-timeline.md)
- [`animation-timing-function`](animation-timing-function.md)
- [`@annotation`](@font-feature-values.md#@annotation)
- [`annotation()`](font-variant-alternates.md#annotation())
- [`:any-link`](:any-link)
- [`appearance`](appearance.md)
- [`ascent-override (@font-face)`](ascent-override.md)
- [`asin()`](asin.md)
- [`aspect-ratio`](_Resources/Markup%20And%20Styling/css/aspect-ratio.md)
- [`atan()`](atan.md)
- [`atan2()`](atan2.md)
- [`attr()`](attr.md)

### B

- [`::backdrop`](::backdrop)
- [`backdrop-filter`](backdrop-filter.md)
- [`backface-visibility`](backface-visibility.md)
- [`background`](background.md)
- [`background-attachment`](background-attachment.md)
- [`background-blend-mode`](background-blend-mode.md)
- [`background-clip`](background-clip.md)
- [`background-color`](background-color.md)
- [`background-image`](background-image.md)
- [`background-origin`](background-origin.md)
- [`background-position`](background-position.md)
- [`background-position-x`](background-position-x.md)
- [`background-position-y`](background-position-y.md)
- [`background-repeat`](background-repeat.md)
- [`background-size`](background-size.md)
- [`base-palette (@font-palette-values)`](base-palette.md)
- [`<basic-shape>`](basic-shape.md)
- [`::before (:before)`](::before)
- [`:blank`](:blank)
- [`bleed (@page)`]
- [`<blend-mode>`](blend-mode.md)
- [`block-overflow`]
- [`block-size`](block-size.md)
- [`blur()`](blur.md)
- [`border`](border.md)
- [`border-block`](border-block.md)
- [`border-block-color`](border-block-color.md)
- [`border-block-end`](border-block-end.md)
- [`border-block-end-color`](border-block-end-color.md)
- [`border-block-end-style`](border-block-end-style.md)
- [`border-block-end-width`](border-block-end-width.md)
- [`border-block-start`](border-block-start.md)
- [`border-block-start-color`](border-block-start-color.md)
- [`border-block-start-style`](border-block-start-style.md)
- [`border-block-start-width`](border-block-start-width.md)
- [`border-block-style`](border-block-style.md)
- [`border-block-width`](border-block-width.md)
- [`border-bottom`](border-bottom.md)
- [`border-bottom-color`](border-bottom-color.md)
- [`border-bottom-left-radius`](border-bottom-left-radius.md)
- [`border-bottom-right-radius`](border-bottom-right-radius.md)
- [`border-bottom-style`](border-bottom-style.md)
- [`border-bottom-width`](border-bottom-width.md)
- [`border-collapse`](border-collapse.md)
- [`border-color`](border-color.md)
- [`border-end-end-radius`](border-end-end-radius.md)
- [`border-end-start-radius`](border-end-start-radius.md)
- [`border-image`](border-image.md)
- [`border-image-outset`](border-image-outset.md)
- [`border-image-repeat`](border-image-repeat.md)
- [`border-image-slice`](border-image-slice.md)
- [`border-image-source`](border-image-source.md)
- [`border-image-width`](border-image-width.md)
- [`border-inline`](border-inline.md)
- [`border-inline-color`](border-inline-color.md)
- [`border-inline-end`](border-inline-end.md)
- [`border-inline-end-color`](border-inline-end-color.md)
- [`border-inline-end-style`](border-inline-end-style.md)
- [`border-inline-end-width`](border-inline-end-width.md)
- [`border-inline-start`](border-inline-start.md)
- [`border-inline-start-color`](border-inline-start-color.md)
- [`border-inline-start-style`](border-inline-start-style.md)
- [`border-inline-start-width`](border-inline-start-width.md)
- [`border-inline-style`](border-inline-style.md)
- [`border-inline-width`](border-inline-width.md)
- [`border-left`](border-left.md)
- [`border-left-color`](border-left-color.md)
- [`border-left-style`](border-left-style.md)
- [`border-left-width`](border-left-width.md)
- [`border-radius`](border-radius.md)
- [`border-right`](border-right.md)
- [`border-right-color`](border-right-color.md)
- [`border-right-style`](border-right-style.md)
- [`border-right-width`](border-right-width.md)
- [`border-spacing`](border-spacing.md)
- [`border-start-end-radius`](border-start-end-radius.md)
- [`border-start-start-radius`](border-start-start-radius.md)
- [`border-style`](border-style.md)
- [`border-top`](border-top.md)
- [`border-top-color`](border-top-color.md)
- [`border-top-left-radius`](border-top-left-radius.md)
- [`border-top-right-radius`](border-top-right-radius.md)
- [`border-top-style`](border-top-style.md)
- [`border-top-width`](border-top-width.md)
- [`border-width`](border-width.md)
- [`bottom`](bottom.md)
- [`@bottom-center`](@page.md#page-margin-box-type)
- [`box-decoration-break`](box-decoration-break.md)
- [`box-shadow`](box-shadow.md)
- [`box-sizing`](box-sizing.md)
- [`break-after`](break-after.md)
- [`break-before`](break-before.md)
- [`break-inside`](break-inside.md)
- [`brightness()`](brightness.md)

### C

- [`calc()`](calc.md)
- [`caption-side`](caption-side.md)
- [`caret`]
- [`caret-color`](caret-color.md)
- [`caret-shape`]
- [`@character-variant`](@font-feature-values.md#@character-variant)
- [`character-variant()`](font-variant-alternates.md#character-variant())
- [`@charset`](@charset.md)
- [`:checked`](:checked)
- [`circle()`](basic-shape.md#circle())
- [`clamp()`](clamp.md)
- [`clear`](clear.md)
- [`clip`](clip.md)
- [`clip-path`](clip-path.md)
- [`<color>`](color_value.md)
- [`color`](_Resources/Markup%20And%20Styling/css/color.md)
- [`color-scheme`](color-scheme.md)
- [`column-count`](column-count.md)
- [`column-fill`](column-fill.md)
- [`column-gap`](column-gap.md)
- [`column-rule`](column-rule.md)
- [`column-rule-color`](column-rule-color.md)
- [`column-rule-style`](column-rule-style.md)
- [`column-rule-width`](column-rule-width.md)
- [`column-span`](column-span.md)
- [`column-width`](column-width.md)
- [`columns`](columns.md)
- [`conic-gradient()`](conic-gradient.md)
- [`contain`](contain.md)
- [`contain-intrinsic-block-size`](contain-intrinsic-block-size.md)
- [`contain-intrinsic-height`](contain-intrinsic-height.md)
- [`contain-intrinsic-inline-size`](contain-intrinsic-inline-size.md)
- [`contain-intrinsic-size`](contain-intrinsic-size.md)
- [`contain-intrinsic-width`](contain-intrinsic-width.md)
- [`container`](container.md)
- [`container-name`](container-name.md)
- [`container-type`](container-type.md)
- [`content`](content.md)
- [`content-visibility`](content-visibility.md)
- [`contrast()`](contrast.md)
- [`cos()`](cos.md)
- [`<counter>`](counter.md)
- [`counter-increment`](counter-increment.md)
- [`counter-reset`](counter-reset.md)
- [`counter-set`](counter-set.md)
- [`@counter-style`](@counter-style.md)
- [`counters()`](counters.md)
- [`cross-fade()`](cross-fade.md)
- [`cubic-bezier()`](easing-function.md#cubic-bezier())
- [`::cue`](::cue)
- [`::cue-region`](::cue-region)
- [`:current`](:current)
- [`cursor`](cursor.md)
- [`<custom-ident>`](custom-ident.md)
- [`length#cap`](length.md#cap)
- [`length#ch`](length.md#ch)
- [`length#cm`](length.md#cm)

### D

- [`angle#deg`](angle.md#deg)
- [`<dashed-ident>`](dashed-ident.md)
- [`:default`](:default)
- [`:defined`](:defined)
- [`descent-override (@font-face)`](descent-override.md)
- [`<dimension>`](dimension.md)
- [`:dir`](:dir)
- [`direction`](direction.md)
- [`:disabled`](:disabled)
- [`display`](display.md)
- [`<display-box>`](display-box.md)
- [`<display-inside>`](display-inside.md)
- [`<display-internal>`](display-internal.md)
- [`<display-legacy>`](display-legacy.md)
- [`<display-listitem>`](display-listitem.md)
- [`<display-outside>`](display-outside.md)
- [`drop-shadow()`](drop-shadow.md)
- [`resolution#dpcm`](_Resources/Markup%20And%20Styling/css/resolution.md#dpcm)
- [`resolution#dpi`](_Resources/Markup%20And%20Styling/css/resolution.md#dpi)
- [`resolution#dppx`](_Resources/Markup%20And%20Styling/css/resolution.md#dppx)

### E

- [`element()`](element().md)
- [`ellipse()`](basic-shape.md#ellipse())
- [`:empty`](:empty)
- [`empty-cells`](empty-cells.md)
- [`:enabled`](:enabled)
- [`env()`](env.md)
- [`exp()`](exp.md)
- [`length#em`](length.md#em)
- [`length#ex`](length.md#ex)

### F

- [`fallback (@counter-style)`](fallback.md)
- [`filter`](filter.md)
- [`<filter-function>`](filter-function.md)
- [`:first`](:first)
- [`:first-child`](:first-child)
- [`::first-letter (:first-letter)`](::first-letter)
- [`::first-line (:first-line)`](::first-line)
- [`:first-of-type`](:first-of-type)
- [`fit-content()`](fit-content.md)
- [`<flex>`](flex_value.md)
- [`flex`](flex.md)
- [`flex-basis`](flex-basis.md)
- [`flex-direction`](flex-direction.md)
- [`flex-flow`](flex-flow.md)
- [`flex-grow`](flex-grow.md)
- [`flex-shrink`](flex-shrink.md)
- [`flex-wrap`](flex-wrap.md)
- [`flex_value#fr`](flex_value.md#fr)
- [`float`](float.md)
- [`:focus`](:focus)
- [`:focus-visible`](:focus-visible)
- [`:focus-within`](:focus-within)
- [`font`](font.md)
- [`font-display (@font-face)`](_Resources/Markup%20And%20Styling/css/@font-face/font-display.md)
- [`@font-face`](@font-face.md)
- [`font-family`](_Resources/Markup%20And%20Styling/css/font-family.md)
- [`font-family (@font-face)`](_Resources/Markup%20And%20Styling/css/@font-face/font-family.md)
- [`font-family (@font-palette-values)`](_Resources/Markup%20And%20Styling/css/@font-palette-values/font-family.md)
- [`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md)
- [`font-feature-settings (@font-face)`](_Resources/Markup%20And%20Styling/css/@font-face/font-feature-settings.md)
- [`@font-feature-values`](@font-feature-values.md)
- [`font-kerning`](font-kerning.md)
- [`font-language-override`](font-language-override.md)
- [`font-optical-sizing`](font-optical-sizing.md)
- [`font-palette`](font-palette.md)
- [`@font-palette-values`](@font-palette-values.md)
- [`font-size`](font-size.md)
- [`font-size-adjust`](font-size-adjust.md)
- [`font-stretch`](_Resources/Markup%20And%20Styling/css/font-stretch.md)
- [`font-stretch (@font-face)`](_Resources/Markup%20And%20Styling/css/@font-face/font-stretch.md)
- [`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md)
- [`font-style (@font-face)`](_Resources/Markup%20And%20Styling/css/@font-face/font-style.md)
- [`font-synthesis`](font-synthesis.md)
- [`font-synthesis-small-caps`](font-synthesis-small-caps.md)
- [`font-synthesis-style`](font-synthesis-style.md)
- [`font-synthesis-weight`](font-synthesis-weight.md)
- [`font-variant`](font-variant.md)
- [`font-variant (@font-face)`](@font-face.md)
- [`font-variant-alternates`](font-variant-alternates.md)
- [`font-variant-caps`](font-variant-caps.md)
- [`font-variant-east-asian`](font-variant-east-asian.md)
- [`font-variant-emoji`](font-variant-emoji.md)
- [`font-variant-ligatures`](font-variant-ligatures.md)
- [`font-variant-numeric`](font-variant-numeric.md)
- [`font-variant-position`](font-variant-position.md)
- [`font-variation-settings`](_Resources/Markup%20And%20Styling/css/font-variation-settings.md)
- [`font-variation-settings (@font-face)`](_Resources/Markup%20And%20Styling/css/@font-face/font-variation-settings.md)
- [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md)
- [`font-weight (@font-face)`](_Resources/Markup%20And%20Styling/css/@font-face/font-weight.md)
- [`forced-color-adjust`](forced-color-adjust.md)
- [`format()`](src.md#format())
- [`<frequency>`](frequency.md)
- [`<frequency-percentage>`](frequency-percentage.md)
- [`:fullscreen`](:fullscreen)
- [`:future`](:future)

### G

- [`angle#grad`](angle.md#grad)
- [`gap`](gap.md)
- [`<gradient>`](gradient.md)
- [`::grammar-error`](::grammar-error)
- [`grayscale()`](grayscale.md)
- [`grid`](_Resources/Markup%20And%20Styling/css/grid.md)
- [`grid-area`](grid-area.md)
- [`grid-auto-columns`](grid-auto-columns.md)
- [`grid-auto-flow`](grid-auto-flow.md)
- [`grid-auto-rows`](grid-auto-rows.md)
- [`grid-column`](grid-column.md)
- [`grid-column-end`](grid-column-end.md)
- [`grid-column-start`](grid-column-start.md)
- [`grid-row`](grid-row.md)
- [`grid-row-end`](grid-row-end.md)
- [`grid-row-start`](grid-row-start.md)
- [`grid-template`](grid-template.md)
- [`grid-template-areas`](grid-template-areas.md)
- [`grid-template-columns`](grid-template-columns.md)
- [`grid-template-rows`](grid-template-rows.md)

### H

- [`frequency#Hz`](frequency.md#hz)
- [`hanging-punctuation`](hanging-punctuation.md)
- [`:has`](:has)
- [`height`](_Resources/Markup%20And%20Styling/css/height.md)
- [`height (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [`@historical-forms`]
- [`:host()`](:host_function)
- [`:host-context()`]
- [`:hover`](:hover)
- [`hsl()`](color_value.md#hsl())
- [`hsla()`](color_value.md#hsla())
- [`hue-rotate()`](hue-rotate.md)
- [`hwb()`]
- [`hyphenate-character`](hyphenate-character.md)
- [`hyphenate-limit-chars`](hyphenate-limit-chars.md)
- [`hyphens`](hyphens.md)
- [`hypot()`](hypot.md)

### I

- [`<ident>`](ident.md)
- [`<image>`](_Resources/Markup%20And%20Styling/css/image.md)
- [`image()`](_Resources/Markup%20And%20Styling/css/image.md#the_image()_functional_notation)
- [`image-orientation`](image-orientation.md)
- [`image-rendering`](image-rendering.md)
- [`image-resolution`](image-resolution.md)
- [`image-set()`](image-set.md)
- [`@import`](@import.md)
- [`:in-range`](:in-range)
- [`:indeterminate`](:indeterminate)
- [`inherit`](inherit.md)
- [`inherits (@property)`](inherits.md)
- [`initial`](initial.md)
- [`initial-letter`](initial-letter.md)
- [`initial-letter-align`](initial-letter-align.md)
- [`initial-value (@property)`](initial-value.md)
- [`inline-size`](inline-size.md)
- [`input-security`]
- [`inset`](_Resources/Markup%20And%20Styling/css/inset.md)
- [`inset()`](basic-shape.md#inset())
- [`inset-block`](inset-block.md)
- [`inset-block-end`](inset-block-end.md)
- [`inset-block-start`](inset-block-start.md)
- [`inset-inline`](inset-inline.md)
- [`inset-inline-end`](inset-inline-end.md)
- [`inset-inline-start`](inset-inline-start.md)
- [`<integer>`](integer.md)
- [`:invalid`](:invalid)
- [`invert()`](invert.md)
- [`:is`](:is)
- [`isolation`](isolation.md)
- [`length#ic`](length.md#ic)
- [`length#in`](length.md#in)

### J

- [`justify-content`](justify-content.md)
- [`justify-items`](justify-items.md)
- [`justify-self`](justify-self.md)
- [`justify-tracks`](justify-tracks.md)

### K

- [`frequency#kHz`](frequency.md#khz)
- [`@keyframes`](@keyframes.md)

### L

- [`lab()`]
- [`:lang`](:lang)
- [`:last-child`](:last-child)
- [`:last-of-type`](:last-of-type)
- [`@layer`](@layer.md)
- [`layer()`]
- [`layer() (@import)`]
- [`lch()`]
- [`leader()`]
- [`:left`](:left)
- [`left`](left.md)
- [`@left-bottom`](@page.md#page-margin-box-type)
- [`<length>`](length.md)
- [`<length-percentage>`](length-percentage.md)
- [`letter-spacing`](letter-spacing.md)
- [`line-break`](line-break.md)
- [`line-clamp`]
- [`line-gap-override (@font-face)`](line-gap-override.md)
- [`line-height`](line-height.md)
- [`line-height-step`](line-height-step.md)
- [`<line-style>`](line-style.md)
- [`linear-gradient()`](linear-gradient.md)
- [`:link`](:link)
- [`list-style`](list-style.md)
- [`list-style-image`](list-style-image.md)
- [`list-style-position`](list-style-position.md)
- [`list-style-type`](list-style-type.md)
- [`local()`](src.md#local())
- [`:local-link`](:local-link)
- [`log()`](log.md)

### M

- [`length#mm`](length.md#mm)
- [`margin`](margin.md)
- [`margin-block`](margin-block.md)
- [`margin-block-end`](margin-block-end.md)
- [`margin-block-start`](margin-block-start.md)
- [`margin-bottom`](margin-bottom.md)
- [`margin-inline`](margin-inline.md)
- [`margin-inline-end`](margin-inline-end.md)
- [`margin-inline-start`](margin-inline-start.md)
- [`margin-left`](margin-left.md)
- [`margin-right`](margin-right.md)
- [`margin-top`](margin-top.md)
- [`margin-trim`](margin-trim.md)
- [`::marker`](::marker)
- [`marks (@page)`]
- [`mask`](mask.md)
- [`mask-border`](mask-border.md)
- [`mask-border-mode`](mask-border-mode.md)
- [`mask-border-outset`](mask-border-outset.md)
- [`mask-border-repeat`](mask-border-repeat.md)
- [`mask-border-slice`](mask-border-slice.md)
- [`mask-border-source`](mask-border-source.md)
- [`mask-border-width`](mask-border-width.md)
- [`mask-clip`](mask-clip.md)
- [`mask-composite`](mask-composite.md)
- [`mask-image`](mask-image.md)
- [`mask-mode`](mask-mode.md)
- [`mask-origin`](mask-origin.md)
- [`mask-position`](mask-position.md)
- [`mask-repeat`](mask-repeat.md)
- [`mask-size`](mask-size.md)
- [`mask-type`](mask-type.md)
- [`masonry-auto-flow`](masonry-auto-flow.md)
- [`math-depth`](math-depth.md)
- [`math-shift`](math-shift.md)
- [`math-style`](math-style.md)
- [`matrix()`](matrix.md)
- [`matrix3d()`](matrix3d.md)
- [`max()`](max.md)
- [`max-block-size`](max-block-size.md)
- [`max-height`](max-height.md)
- [`max-height (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [`max-inline-size`](max-inline-size.md)
- [`max-lines`]
- [`max-width`](max-width.md)
- [`max-width (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [`max-zoom (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [`@media`](@media.md)
- [`min()`](min.md)
- [`min-block-size`](min-block-size.md)
- [`min-height`](min-height.md)
- [`min-height (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [`min-inline-size`](min-inline-size.md)
- [`min-width`](min-width.md)
- [`min-width (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [`min-zoom (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [`minmax()`](minmax.md)
- [`mix-blend-mode`](mix-blend-mode.md)
- [`mod()`](mod.md)
- [`time#ms`](time.md#ms)

### N

- [`@namespace`](@namespace.md)
- [`negative (@counter-style)`](negative.md)
- [`:not`](:not)
- [`:nth-child`](:nth-child)
- [`:nth-col`](:nth-of-type)
- [`:nth-last-child`](:nth-last-child)
- [`:nth-last-col`](:nth-last-of-type)
- [`:nth-last-of-type`](:nth-last-of-type)
- [`:nth-of-type`](:nth-of-type)
- [`<number>`](number.md)

### O

- [`object-fit`](object-fit.md)
- [`object-position`](object-position.md)
- [`offset`](offset.md)
- [`offset-anchor`](offset-anchor.md)
- [`offset-distance`](offset-distance.md)
- [`offset-path`](offset-path.md)
- [`offset-position`](offset-position.md)
- [`offset-rotate`](offset-rotate.md)
- [`:only-child`](:only-child)
- [`:only-of-type`](:only-of-type)
- [`opacity`](_Resources/Markup%20And%20Styling/css/opacity.md)
- [`opacity()`](_Resources/Markup%20And%20Styling/css/filter-function/opacity.md)
- [`:optional`](:optional)
- [`order`](order.md)
- [`orientation (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [`@ornaments`](@font-feature-values.md#@ornaments)
- [`ornaments()`](font-variant-alternates.md#ornaments())
- [`orphans`](orphans.md)
- [`:out-of-range`](:out-of-range)
- [`outline`](outline.md)
- [`outline-color`](outline-color.md)
- [`outline-offset`](outline-offset.md)
- [`outline-style`](outline-style.md)
- [`outline-width`](outline-width.md)
- [`<overflow>`](overflow.md)
- [`overflow-anchor`](overflow-anchor.md)
- [`overflow-block`](_Resources/Markup%20And%20Styling/css/overflow-block.md)
- [`overflow-clip-margin`](overflow-clip-margin.md)
- [`overflow-inline`](_Resources/Markup%20And%20Styling/css/overflow-inline.md)
- [`overflow-wrap`](overflow-wrap.md)
- [`overflow-x`](overflow-x.md)
- [`overflow-y`](overflow-y.md)
- [`override-colors (@font-palette-values)`](override-colors.md)
- [`overscroll-behavior`](overscroll-behavior.md)
- [`overscroll-behavior-block`](overscroll-behavior-block.md)
- [`overscroll-behavior-inline`](overscroll-behavior-inline.md)
- [`overscroll-behavior-x`](overscroll-behavior-x.md)
- [`overscroll-behavior-y`](overscroll-behavior-y.md)

### P

- [`Pseudo-classes`](pseudo-classes.md)
- [`Pseudo-elements`](pseudo-elements.md)
- [`length#pc`](length.md#pc)
- [`length#pt`](length.md#pt)
- [`length#px`](length.md#px)
- [`pad (@counter-style)`](pad.md)
- [`padding`](padding.md)
- [`padding-block`](padding-block.md)
- [`padding-block-end`](padding-block-end.md)
- [`padding-block-start`](padding-block-start.md)
- [`padding-bottom`](padding-bottom.md)
- [`padding-inline`](padding-inline.md)
- [`padding-inline-end`](padding-inline-end.md)
- [`padding-inline-start`](padding-inline-start.md)
- [`padding-left`](padding-left.md)
- [`padding-right`](padding-right.md)
- [`padding-top`](padding-top.md)
- [`@page`](@page.md)
- [`page`](page.md)
- [`page-break-after`](page-break-after.md)
- [`page-break-before`](page-break-before.md)
- [`page-break-inside`](page-break-inside.md)
- [`page-orientation (@page)`](page-orientation.md)
- [`paint()`](paint.md)
- [`paint-order`](paint-order.md)
- [`::part`](::part)
- [`:past`](:past)
- [`path()`](path.md)
- [`:paused`](:paused)
- [`<percentage>`](percentage.md)
- [`perspective`](_Resources/Markup%20And%20Styling/css/perspective.md)
- [`perspective()`](_Resources/Markup%20And%20Styling/css/transform-function/perspective.md)
- [`perspective-origin`](perspective-origin.md)
- [`:picture-in-picture`](:picture-in-picture)
- [`place-content`](place-content.md)
- [`place-items`](place-items.md)
- [`place-self`](place-self.md)
- [`::placeholder`](::placeholder)
- [`:placeholder-shown`](:placeholder-shown)
- [`:playing`](:playing)
- [`pointer-events`](pointer-events.md)
- [`polygon()`](basic-shape.md#polygon())
- [`<position>`](position_value.md)
- [`position`](position.md)
- [`pow()`](pow.md)
- [`prefix (@counter-style)`](prefix.md)
- [`print-color-adjust`](print-color-adjust.md)
- [`@property`](@property.md)

### Q

- [`length#Q`](length.md#q)
- [`quotes`](quotes.md)

### R

- [`angle#rad`](angle.md#rad)
- [`length#rem`](length.md#rem)
- [`radial-gradient()`](radial-gradient.md)
- [`range (@counter-style)`](range.md)
- [`<ratio>`](ratio.md)
- [`ray()`](ray.md)
- [`:read-only`](:read-only)
- [`:read-write`](:read-write)
- [`rect()`](shape.md#rect())
- [`rem()`](rem.md)
- [`repeat()`](repeat.md)
- [`repeating-conic-gradient()`](repeating-conic-gradient.md)
- [`repeating-linear-gradient()`](repeating-linear-gradient.md)
- [`repeating-radial-gradient()`](repeating-radial-gradient.md)
- [`:required`](:required)
- [`resize`](resize.md)
- [`<resolution>`](_Resources/Markup%20And%20Styling/css/resolution.md)
- [`reversed()`]
- [`revert`](revert.md)
- [`rgb()`](color_value.md#rgb())
- [`rgba()`](color_value.md#rgba())
- [`:right`](:right)
- [`right`](right.md)
- [`@right-bottom`](@page.md#page-margin-box-type)
- [`:root`](:root)
- [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md)
- [`rotate()`](_Resources/Markup%20And%20Styling/css/transform-function/rotate.md)
- [`rotate3d()`](rotate3d.md)
- [`rotateX()`](rotatex.md)
- [`rotateY()`](rotatey.md)
- [`rotateZ()`](rotatez.md)
- [`round()`](round.md)
- [`row-gap`](row-gap.md)
- [`ruby-align`](ruby-align.md)
- [`ruby-merge`]
- [`ruby-position`](ruby-position.md)

### S

- [`saturate()`](saturate.md)
- [`scale`](_Resources/Markup%20And%20Styling/css/scale.md)
- [`scale()`](_Resources/Markup%20And%20Styling/css/transform-function/scale.md)
- [`scale3d()`](scale3d.md)
- [`scaleX()`](scalex.md)
- [`scaleY()`](scaley.md)
- [`scaleZ()`](scalez.md)
- [`:scope`](:scope)
- [`scroll()`](overflow.md)
- [`scroll-behavior`](scroll-behavior.md)
- [`scroll-margin`](scroll-margin.md)
- [`scroll-margin-block`](scroll-margin-block.md)
- [`scroll-margin-block-end`](scroll-margin-block-end.md)
- [`scroll-margin-block-start`](scroll-margin-block-start.md)
- [`scroll-margin-bottom`](scroll-margin-bottom.md)
- [`scroll-margin-inline`](scroll-margin-inline.md)
- [`scroll-margin-inline-end`](scroll-margin-inline-end.md)
- [`scroll-margin-inline-start`](scroll-margin-inline-start.md)
- [`scroll-margin-left`](scroll-margin-left.md)
- [`scroll-margin-right`](scroll-margin-right.md)
- [`scroll-margin-top`](scroll-margin-top.md)
- [`scroll-padding`](scroll-padding.md)
- [`scroll-padding-block`](scroll-padding-block.md)
- [`scroll-padding-block-end`](scroll-padding-block-end.md)
- [`scroll-padding-block-start`](scroll-padding-block-start.md)
- [`scroll-padding-bottom`](scroll-padding-bottom.md)
- [`scroll-padding-inline`](scroll-padding-inline.md)
- [`scroll-padding-inline-end`](scroll-padding-inline-end.md)
- [`scroll-padding-inline-start`](scroll-padding-inline-start.md)
- [`scroll-padding-left`](scroll-padding-left.md)
- [`scroll-padding-right`](scroll-padding-right.md)
- [`scroll-padding-top`](scroll-padding-top.md)
- [`scroll-snap-align`](scroll-snap-align.md)
- [`scroll-snap-stop`](scroll-snap-stop.md)
- [`scroll-snap-type`](scroll-snap-type.md)
- [`@scroll-timeline`](scroll-timeline.md)
- [`scroll-timeline`](scroll-timeline.md)
- [`scroll-timeline-axis`](scroll-timeline-axis.md)
- [`scroll-timeline-name`](scroll-timeline-name.md)
- [`scrollbar-color`](scrollbar-color.md)
- [`scrollbar-gutter`](scrollbar-gutter.md)
- [`scrollbar-width`](scrollbar-width.md)
- [`::selection`](::selection)
- [`selector()`]
- [`sepia()`](sepia.md)
- [`<shape>`](shape.md)
- [`shape-image-threshold`](shape-image-threshold.md)
- [`shape-margin`](shape-margin.md)
- [`shape-outside`](shape-outside.md)
- [`sign()`](sign.md)
- [`sin()`](sin.md)
- [`size (@page)`](size.md)
- [`size-adjust (@font-face)`](size-adjust.md)
- [`skew()`](skew.md)
- [`skewX()`](skewx.md)
- [`skewY()`](skewy.md)
- [`::slotted`](::slotted)
- [`speak-as (@counter-style)`](speak-as.md)
- [`::spelling-error`](::spelling-error)
- [`sqrt()`](sqrt.md)
- [`src (@font-face)`](src.md)
- [`steps()`](easing-function.md#steps())
- [`<string>`](string.md)
- [`@styleset`](@font-feature-values.md#@styleset)
- [`styleset()`](font-variant-alternates.md#styleset())
- [`@stylistic`](@font-feature-values.md#@stylistic)
- [`stylistic()`](font-variant-alternates.md#stylistic())
- [`suffix (@counter-style)`](suffix.md)
- [`@supports`](@supports.md)
- [`supports() (@import)`]
- [`@swash`](@font-feature-values.md#@swash)
- [`swash()`](font-variant-alternates.md#swash())
- [`symbols (@counter-style)`](symbols.md)
- [`symbols()`](symbols.md)
- [`syntax (@property)`](_Resources/Markup%20And%20Styling/css/@property/syntax.md)
- [`system (@counter-style)`](system.md)
- [`time#s`](time.md#s)

### T

- [`angle#turn`](angle.md#turn)
- [`tab-size`](tab-size.md)
- [`table-layout`](table-layout.md)
- [`tan()`](tan.md)
- [`:target`](:target)
- [`target-counter()`]
- [`target-counters()`]
- [`::target-text`](::target-text)
- [`target-text()`]
- [`:target-within`](:target-within)
- [`text-align`](text-align.md)
- [`text-align-last`](text-align-last.md)
- [`text-combine-upright`](text-combine-upright.md)
- [`text-decoration`](text-decoration.md)
- [`text-decoration-color`](text-decoration-color.md)
- [`text-decoration-line`](text-decoration-line.md)
- [`text-decoration-skip`](text-decoration-skip.md)
- [`text-decoration-skip-ink`](text-decoration-skip-ink.md)
- [`text-decoration-style`](text-decoration-style.md)
- [`text-decoration-thickness`](text-decoration-thickness.md)
- [`text-emphasis`](text-emphasis.md)
- [`text-emphasis-color`](text-emphasis-color.md)
- [`text-emphasis-position`](text-emphasis-position.md)
- [`text-emphasis-style`](text-emphasis-style.md)
- [`text-indent`](text-indent.md)
- [`text-justify`](text-justify.md)
- [`text-orientation`](text-orientation.md)
- [`text-overflow`](text-overflow.md)
- [`text-rendering`](text-rendering.md)
- [`text-shadow`](text-shadow.md)
- [`text-size-adjust`](text-size-adjust.md)
- [`text-transform`](text-transform.md)
- [`text-underline-offset`](text-underline-offset.md)
- [`text-underline-position`](text-underline-position.md)
- [`text-wrap`](text-wrap.md)
- [`<time>`](time.md)
- [`<time-percentage>`](time-percentage.md)
- [`timeline-scope`](timeline-scope.md)
- [`<timing-function>`](easing-function.md)
- [`top`](top.md)
- [`@top-center`](@page.md#page-margin-box-type)
- [`touch-action`](touch-action.md)
- [`transform`](transform.md)
- [`transform-box`](transform-box.md)
- [`<transform-function>`](transform-function.md)
- [`transform-origin`](transform-origin.md)
- [`transform-style`](transform-style.md)
- [`transition`](transition.md)
- [`transition-delay`](transition-delay.md)
- [`transition-duration`](transition-duration.md)
- [`transition-property`](transition-property.md)
- [`transition-timing-function`](transition-timing-function.md)
- [`translate`](_Resources/Markup%20And%20Styling/css/translate.md)
- [`translate()`](_Resources/Markup%20And%20Styling/css/transform-function/translate.md)
- [`translate3d()`](translate3d.md)
- [`translateX()`](translatex.md)
- [`translateY()`](translatey.md)
- [`translateZ()`](translatez.md)
- [`type()`]

### U

- [`unicode-bidi`](unicode-bidi.md)
- [`unicode-range (@font-face)`](unicode-range.md)
- [`unset`](unset.md)
- [`<url>`](url.md)
- [`url()`](url.md#the_url()_functional_notation)
- [`:user-invalid`](:user-invalid)
- [`user-select`](user-select.md)
- [`:user-valid`](:user-valid)
- [`user-zoom (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)

### V

- [`length#vh`](length.md#vh)
- [`length#vmax`](length.md#vmax)
- [`length#vmin`](length.md#vmin)
- [`length#vw`](length.md#vw)
- [`:valid`](:valid)
- [`var()`](var().md)
- [`vertical-align`](vertical-align.md)
- [`view()`]
- [`view-timeline`](view-timeline.md)
- [`view-timeline-axis`](view-timeline-axis.md)
- [`view-timeline-inset`](view-timeline-inset.md)
- [`view-timeline-name`](view-timeline-name.md)
- [`::view-transition`](::view-transition)
- [`::view-transition-group`](::view-transition-group)
- [`::view-transition-image-pair`](::view-transition-image-pair)
- [`view-transition-name`](view-transition-name.md)
- [`::view-transition-new`](::view-transition-new)
- [`::view-transition-old`](::view-transition-old)
- [`@viewport`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [`viewport-fit (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [`visibility`](visibility.md)
- [`:visited`](:visited)

### W

- [`:where`](:where)
- [`white-space`](white-space.md)
- [`white-space-collapse`](white-space-collapse.md)
- [`white-space-trim`]
- [`widows`](widows.md)
- [`width`](_Resources/Markup%20And%20Styling/css/width.md)
- [`width (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [`will-change`](will-change.md)
- [`word-break`](word-break.md)
- [`word-spacing`](word-spacing.md)
- [`word-wrap`](overflow-wrap.md)
- [`writing-mode`](writing-mode.md)

### X

- [`resolution#x`](_Resources/Markup%20And%20Styling/css/resolution.md#x)

### Z

- [`z-index`](z-index.md)
- [`zoom (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)

### Others

- [`--*`](--*)

Selectors
---------

The following are the various [selectors](css_selectors.md), which allow
styles to be conditional based on various features of elements within
the DOM.

### Basic selectors

**Basic selectors** are fundamental selectors; these are the most basic
selectors that are frequently combined to create other, more complex
selectors.

- [Universal selector](universal_selectors.md) `*`
- [Type selector](type_selectors.md) `elementname`
- [Class selector](class_selectors.md) `.classname`
- [ID selector](id_selectors.md) `#idname`
- [Attribute selector](attribute_selectors.md) `[attr=value]`

### Grouping selectors

[Selector list](selector_list.md) `A, B`

:   Specifies that both `A` and `B` elements are selected. This is a
    grouping method to select several matching elements.

### Combinators

Combinators are selectors that establish a relationship between two or
more simple selectors, such as \"`A` is a child of `B`\" or \"`A` is
adjacent to `B`\", creating a complex selector.

[Next-sibling combinator](next-sibling_combinator.md) `A + B`

:   Specifies that the elements selected by both `A` and `B` have the
    same parent and that the element selected by `B` immediately follows
    the element selected by `A` horizontally.

[Subsequent-sibling combinator](subsequent-sibling_combinator.md) `A ~ B`

:   Specifies that the elements selected by both `A` and `B` share the
    same parent and that the element selected by `A` comes before---but
    not necessarily immediately before---the element selected by `B`.

[Child combinator](child_combinator.md) `A > B`

:   Specifies that the element selected by `B` is the direct child of
    the element selected by `A`.

[Descendant combinator](descendant_combinator.md) `A B`

:   Specifies that the element selected by `B` is a descendant of the
    element selected by `A`, but is not necessarily a direct child.

[Column combinator](column_combinator.md) `A || B` [Experimental]

:   Specifies that the element selected by `B` is located within the
    table column specified by `A`. Elements which span multiple columns
    are considered to be a member of all of those columns.

### Pseudo

[Pseudo classes](pseudo-classes.md) `:`

:   Specifies a special state of the selected element(s).

[Pseudo elements](pseudo-elements.md) `::`

:   Represents entities that are not included in HTML.

See also [selectors in the Selectors
specification](https://drafts.csswg.org/selectors/) and the
[pseudo-element specification](https://drafts.csswg.org/css-pseudo/).

Concepts
--------

### Syntax and semantics

- [CSS syntax](_Resources/Markup%20And%20Styling/css/syntax.md)
- [At-rules](at-rule.md)
- [Cascade](cascade.md)
- [Comments](comments.md)
- [Descriptor](https://developer.mozilla.org/en-US/docs/Glossary/CSS_Descriptor)
- [Inheritance](inheritance.md)
- [Shorthand properties](shorthand_properties.md)
- [Specificity](specificity.md)
- [Value definition syntax](value_definition_syntax.md)
- [CSS unit and value types](css_values_and_units.md)
- [CSS functional notations](css_functions.md)

### Values

- [Actual value](actual_value.md)
- [Computed value](computed_value.md)
- [Initial value](initial_value.md)
- [Resolved value](resolved_value.md)
- [Specified value](specified_value.md)
- [Used value](used_value.md)

### Layout

- [Block formatting
    context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)
- [Box model](introduction_to_the_css_box_model.md)
- [Containing block](containing_block.md)
- [Layout mode](layout_mode.md)
- [Margin collapsing](mastering_margin_collapsing.md)
- [Replaced elements](replaced_element.md)
- [](stacking_context.md)
- [Visual formatting model](visual_formatting_model.md)

DOM-CSS / CSSOM
---------------

### Major object types

- [`Document.styleSheets`](https://developer.mozilla.org/en-US/docs/Web/API/Document/styleSheets)
- `styleSheets[i].cssRules`
- `cssRules[i].cssText` (selector & style)
- `cssRules[i].selectorText`
- [`HTMLElement.style`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style)
- `HTMLElement.style.cssText` (just style)
- [`Element.className`](https://developer.mozilla.org/en-US/docs/Web/API/Element/className)
- [`Element.classList`](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)

### Important methods

- [`CSSStyleSheet.insertRule()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/insertRule)
- [`CSSStyleSheet.deleteRule()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/deleteRule)

See also
--------

- [Mozilla CSS
    extensions](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions)
    (prefixed with `-moz-`)
- [WebKit CSS
    extensions](https://developer.mozilla.org/en-US/docs/Web/CSS/WebKit_Extensions)
    (mostly prefixed with `-webkit-`)

External Links
--------------

- [CSS Indices (w3.org)](https://www.w3.org/TR/CSS/#indices)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Reference>
