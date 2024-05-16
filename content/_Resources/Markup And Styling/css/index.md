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
[guide on CSS Selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors).
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

- [[--|--*]]
- [[-webkit-line-clamp]]

### A

- [[abs]]
- [[accent-color]]
- [[acos]]
- [[active|:active]]
- [[additive-symbols]]
- [[after|::after]]
- [[align-content]]
- [[align-items]]
- [[align-self]]
- [[align-tracks]]
- [[all]]
- `<an-plus-b>`
- [[angle]]
- [[angle-percentage]]
- [[animation]]
- [[animation-composition]]
- [[animation-delay]]
- [[animation-direction]]
- [[animation-duration]]
- [[animation-fill-mode]]
- [[animation-iteration-count]]
- [[animation-name]]
- [[animation-play-state]]
- [[animation-range]]
- [[animation-range-end]]
- [[animation-range-start]]
- [[animation-timeline]]
- [[animation-timing-function]]
- [[@font-feature-values#@annotation|@annotation]]
- [[font-variant-alternates#annotation()|annotation()]]
- [[any-link|:any-link]]
- [[appearance]]
- [[ascent-override]]
- [[asin]]
- [[_Resources/Markup And Styling/css/aspect-ratio]]
- [[atan]]
- [[atan2]]
- [[attr]]

### B

- [[backdrop|::backdrop]]
- [[backdrop-filter]]
- [[backface-visibility]]
- [[background]]
- [[background-attachment]]
- [[background-blend-mode]]
- [[background-clip]]
- [[background-color]]
- [[background-image]]
- [[background-origin]]
- [[background-position]]
- [[background-position-x]]
- [[background-position-y]]
- [[background-repeat]]
- [[background-size]]
- [[base-palette]]
- [[basic-shape]]
- [[before|::before]]
- [[blank|:blank]]
- `bleed (@page)`
- [[blend-mode]]
- `block-overflow`
- [[block-size]]
- [[blur]]
- [[border]]
- [[border-block]]
- [[border-block-color]]
- [[border-block-end]]
- [[border-block-end-color]]
- [[border-block-end-style]]
- [[border-block-end-width]]
- [[border-block-start]]
- [[border-block-start-color]]
- [[border-block-start-style]]
- [[border-block-start-width]]
- [[border-block-style]]
- [[border-block-width]]
- [[border-bottom]]
- [[border-bottom-color]]
- [[border-bottom-left-radius]]
- [[border-bottom-right-radius]]
- [[border-bottom-style]]
- [[border-bottom-width]]
- [[border-collapse]]
- [[border-color]]
- [[border-end-end-radius]]
- [[border-end-start-radius]]
- [[border-image]]
- [[border-image-outset]]
- [[border-image-repeat]]
- [[border-image-slice]]
- [[border-image-source]]
- [[border-image-width]]
- [[border-inline]]
- [[border-inline-color]]
- [[border-inline-end]]
- [[border-inline-end-color]]
- [[border-inline-end-style]]
- [[border-inline-end-width]]
- [[border-inline-start]]
- [[border-inline-start-color]]
- [[border-inline-start-style]]
- [[border-inline-start-width]]
- [[border-inline-style]]
- [[border-inline-width]]
- [[border-left]]
- [[border-left-color]]
- [[border-left-style]]
- [[border-left-width]]
- [[border-radius]]
- [[border-right]]
- [[border-right-color]]
- [[border-right-style]]
- [[border-right-width]]
- [[border-spacing]]
- [[border-start-end-radius]]
- [[border-start-start-radius]]
- [[border-style]]
- [[border-top]]
- [[border-top-color]]
- [[border-top-left-radius]]
- [[border-top-right-radius]]
- [[border-top-style]]
- [[border-top-width]]
- [[border-width]]
- [[bottom]]
- [[@page#page-margin-box-type]]
- [[box-decoration-break]]
- [[box-shadow]]
- [[box-sizing]]
- [[break-after]]
- [[break-before]]
- [[break-inside]]
- [[brightness]]

### C

- [[calc]]
- [[caption-side]]
- `caret`
- [[caret-color]]
- `caret-shape`
- [[@font-feature-values#@character-variant|@character-variant]]
- [[font-variant-alternates#character-variant()|character-variant()]]
- [[@charset]]
- [[checked|:checked]]
- [[basic-shape#circle()|circle()]]
- [[clamp]]
- [[clear]]
- [[clip]]
- [[clip-path]]
- [[color_value]]
- [[_Resources/Markup And Styling/css/color]]
- [[color-scheme]]
- [[column-count]]
- [[column-fill]]
- [[column-gap]]
- [[column-rule]]
- [[column-rule-color]]
- [[column-rule-style]]
- [[column-rule-width]]
- [[column-span]]
- [[column-width]]
- [[columns]]
- [[conic-gradient]]
- [[contain]]
- [[contain-intrinsic-block-size]]
- [[contain-intrinsic-height]]
- [[contain-intrinsic-inline-size]]
- [[contain-intrinsic-size]]
- [[contain-intrinsic-width]]
- [[container]]
- [[container-name]]
- [[container-type]]
- [[content]]
- [[content-visibility]]
- [[contrast]]
- [[cos]]
- [[counter]]
- [[counter-increment]]
- [[counter-reset]]
- [[counter-set]]
- [[@counter-style]]
- [[counters]]
- [[cross-fade]]
- [[easing-function#Cubic Bézier easing function|cubic-bezier]]
- [[cue|::cue]]
- [[cue-region|::cue-region]]
- [[current|:current]]
- [[cursor]]
- [[custom-ident]]
- [[length#cap]]
- [[length#ch]]
- [[length#cm]]

### D

- [[angle#deg]]
- [[dashed-ident]]
- [[default|:default]]
- [[defined|:defined]]
- [[descent-override]]
- [[dimension]]
- [[dir|:dir]]
- [[direction]]
- [[disabled|:disabled]]
- [[display]]
- [[display-box]]
- [[display-inside]]
- [[display-internal]]
- [[display-legacy]]
- [[display-listitem]]
- [[display-outside]]
- [[drop-shadow]]
- [[_Resources/Markup And Styling/css/resolution#dpcm]]
- [[_Resources/Markup And Styling/css/resolution#dpi]]
- [[_Resources/Markup And Styling/css/resolution#dppx]]

### E

- [[element()]]
- [[basic-shape#`ellipse()`|ellipse()]]
- [[empty|:empty]]
- [[empty-cells]]
- [[enabled|:enabled]]
- [[env]]
- [[exp]]
- [[length#em]]
- [[length#ex]]

### F

- [[fallback]]
- [[filter]]
- [[filter-function]]
- [[first|:first]]
- [[first-child|:first-child]]
- [[first-letter|::first-letter]]
- [[first-line|::first-line]]
- [[first-of-type|:first-of-type]]
- [[fit-content]]
- [[flex_value]]
- [[flex]]
- [[flex-basis]]
- [[flex-direction]]
- [[flex-flow]]
- [[flex-grow]]
- [[flex-shrink]]
- [[flex-wrap]]
- [[flex_value#fr]]
- [[float]]
- [[focus|:focus]]
- [[focus-visible|:focus-visible]]
- [[focus-within|:focus-within]]
- [[font]]
- [[_Resources/Markup And Styling/css/@font-face/font-display]]
- [[@font-face]]
- [[_Resources/Markup And Styling/css/font-family]]
- [[_Resources/Markup And Styling/css/@font-face/font-family]]
- [[_Resources/Markup And Styling/css/@font-palette-values/font-family]]
- [[_Resources/Markup And Styling/css/font-feature-settings]]
- [[_Resources/Markup And Styling/css/@font-face/font-feature-settings]]
- [[@font-feature-values]]
- [[font-kerning]]
- [[font-language-override]]
- [[font-optical-sizing]]
- [[font-palette]]
- [[@font-palette-values]]
- [[font-size]]
- [[font-size-adjust]]
- [[_Resources/Markup And Styling/css/font-stretch]]
- [[_Resources/Markup And Styling/css/@font-face/font-stretch]]
- [[_Resources/Markup And Styling/css/font-style]]
- [[_Resources/Markup And Styling/css/@font-face/font-style]]
- [[font-synthesis]]
- [[font-synthesis-small-caps]]
- [[font-synthesis-style]]
- [[font-synthesis-weight]]
- [[font-variant]]
- [[@font-face]]
- [[font-variant-alternates]]
- [[font-variant-caps]]
- [[font-variant-east-asian]]
- [[font-variant-emoji]]
- [[font-variant-ligatures]]
- [[font-variant-numeric]]
- [[font-variant-position]]
- [[_Resources/Markup And Styling/css/font-variation-settings]]
- [[_Resources/Markup And Styling/css/@font-face/font-variation-settings]]
- [[_Resources/Markup And Styling/css/font-weight]]
- [[_Resources/Markup And Styling/css/@font-face/font-weight]]
- [[forced-color-adjust]]
- [[@font-face/src#format[[]]]]
- [[frequency]]
- [[frequency-percentage]]
- [[fullscreen|:fullscreen]]
- [[future|:future]]

### G

- [[angle#grad|grad]]
- [[gap]]
- [[gradient]]
- [[grammar-error|::grammar-error]]
- [[grayscale]]
- [[_Resources/Markup And Styling/css/grid]]
- [[grid-area]]
- [[grid-auto-columns]]
- [[grid-auto-flow]]
- [[grid-auto-rows]]
- [[grid-column]]
- [[grid-column-end]]
- [[grid-column-start]]
- [[grid-row]]
- [[grid-row-end]]
- [[grid-row-start]]
- [[grid-template]]
- [[grid-template-areas]]
- [[grid-template-columns]]
- [[grid-template-rows]]

### H

- [[frequency#Hz]]
- [[hanging-punctuation]]
- [[has|:has]]
- [[_Resources/Markup And Styling/css/height]]
- [`height (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- `@historical-forms`
- [[host_function|:host_function]]
- `:host-context()`
- [[hover|:hover]]
- [[hsl|hsl()]]
- [[hsl#Legacy syntax hsla()|hsla()]]
- [[hue-rotate|hue-rotate()]]
- `hwb()`
- [[hyphenate-character]]
- [[hyphenate-limit-chars]]
- [[hyphens]]
- [[hypot]]

### I

- [[ident]]
- [[_Resources/Markup And Styling/css/image]]
- [[_Resources/Markup And Styling/css/image#Formal syntax|image Syntax]]
- [[image-orientation]]
- [[image-rendering]]
- [[image-resolution]]
- [[image-set]]
- [[@import]]
- [[in-range|:in-range]]
- [[indeterminate|:indeterminate]]
- [[inherit]]
- [[inherits]]
- [[initial]]
- [[initial-letter]]
- [[initial-letter-align]]
- [[initial-value]]
- [[inline-size]]
- `input-security`
- [[_Resources/Markup And Styling/css/inset]]
- [[basic-shape#`inset()`|inset()]]
- [[inset-block]]
- [[inset-block-end]]
- [[inset-block-start]]
- [[inset-inline]]
- [[inset-inline-end]]
- [[inset-inline-start]]
- [[integer]]
- [[invalid|:invalid]]
- [[invert]]
- [[is|:is]]
- [[isolation]]
- [[length#ic]]
- [[length#in]]

### J

- [[justify-content]]
- [[justify-items]]
- [[justify-self]]
- [[justify-tracks]]

### K

- [[frequency#khz]]
- [[@keyframes]]

### L

- [[lab]]
- [[lang|:lang]]
- [[last-child|:last-child]]
- [[last-of-type|:last-of-type]]
- [[@layer]]
- `layer()`
- `layer() (@import)`
- `lch()`
- `leader()`
- [[left|:left]]
- [[left]]
- [[@page#page-margin-box-type]]
- [[length]]
- [[length-percentage]]
- [[letter-spacing]]
- [[line-break]]
- `line-clamp`
- [[line-gap-override]]
- [[line-height]]
- [[line-height-step]]
- [[line-style]]
- [[linear-gradient]]
- [[link|:link]]
- [[list-style]]
- [[list-style-image]]
- [[list-style-position]]
- [[list-style-type]]
- [[src#local(font-face-name)|local()]]
- [[local-link|:local-link]]
- [[log]]

### M

- [[length#mm]]
- [[margin]]
- [[margin-block]]
- [[margin-block-end]]
- [[margin-block-start]]
- [[margin-bottom]]
- [[margin-inline]]
- [[margin-inline-end]]
- [[margin-inline-start]]
- [[margin-left]]
- [[margin-right]]
- [[margin-top]]
- [[margin-trim]]
- [[marker|::marker]]
- `marks (@page)`
- [[mask]]
- [[mask-border]]
- [[mask-border-mode]]
- [[mask-border-outset]]
- [[mask-border-repeat]]
- [[mask-border-slice]]
- [[mask-border-source]]
- [[mask-border-width]]
- [[mask-clip]]
- [[mask-composite]]
- [[mask-image]]
- [[mask-mode]]
- [[mask-origin]]
- [[mask-position]]
- [[mask-repeat]]
- [[mask-size]]
- [[mask-type]]
- [[masonry-auto-flow]]
- [[math-depth]]
- [[math-shift]]
- [[math-style]]
- [[matrix]]
- [[matrix3d]]
- [[max]]
- [[max-block-size]]
- [[max-height]]
- [`max-height (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [[max-inline-size]]
- `max-lines`
- [[max-width]]
- [`max-width (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [`max-zoom (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [[@media]]
- [[min]]
- [[min-block-size]]
- [[min-height]]
- [`min-height (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [[min-inline-size]]
- [[min-width]]
- [`min-width (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [`min-zoom (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [[minmax]]
- [[mix-blend-mode]]
- [[mod]]
- [[time#ms]]

### N

- [[@namespace]]
- [[negative]]
- [[not|:not]]
- [[nth-child|:nth-child]]
- [[nth-of-type|:nth-of-type]]
- [[nth-last-child|:nth-last-child]]
- [[nth-last-of-type|:nth-last-of-type]]
- [[nth-last-of-type|:nth-last-of-type]]
- [[nth-of-type|:nth-of-type]]
- [[number]]

### O

- [[object-fit]]
- [[object-position]]
- [[offset]]
- [[offset-anchor]]
- [[offset-distance]]
- [[offset-path]]
- [[offset-position]]
- [[offset-rotate]]
- [[only-child|:only-child]]
- [[only-of-type|:only-of-type]]
- [[_Resources/Markup And Styling/css/opacity]]
- [[_Resources/Markup And Styling/css/filter-function/opacity]]
- [[optional|:optional]]
- [[order]]
- [`orientation (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [[@font-feature-values#@ornaments|@ornaments]]
- [[font-variant#Values|ornaments()]]
- [[orphans]]
- [[out-of-range|:out-of-range]]
- [[outline]]
- [[outline-color]]
- [[outline-offset]]
- [[outline-style]]
- [[outline-width]]
- [[overflow]]
- [[overflow-anchor]]
- [[_Resources/Markup And Styling/css/overflow-block]]
- [[overflow-clip-margin]]
- [[_Resources/Markup And Styling/css/overflow-inline]]
- [[overflow-wrap]]
- [[overflow-x]]
- [[overflow-y]]
- [[override-colors|override-colors]]
- [[overscroll-behavior]]
- [[overscroll-behavior-block]]
- [[overscroll-behavior-inline]]
- [[overscroll-behavior-x]]
- [[overscroll-behavior-y]]

### P

- [[pseudo-classes]]
- [[pseudo-elements]]
- [[length#pc]]
- [[length#pt]]
- [[length#px]]
- [[pad|pad]]
- [[padding]]
- [[padding-block]]
- [[padding-block-end]]
- [[padding-block-start]]
- [[padding-bottom]]
- [[padding-inline]]
- [[padding-inline-end]]
- [[padding-inline-start]]
- [[padding-left]]
- [[padding-right]]
- [[padding-top]]
- [[@page]]
- [[page]]
- [[page-break-after]]
- [[page-break-before]]
- [[page-break-inside]]
- [[page-orientation]]
- [[paint]]
- [[paint-order]]
- [[part|::part]]
- [[past|:past]]
- [[path]]
- [[paused|:paused]]
- [[percentage]]
- [[_Resources/Markup And Styling/css/perspective]]
- [[_Resources/Markup And Styling/css/transform-function/perspective]]
- [[perspective-origin]]
- [[picture-in-picture|:picture-in-picture]]
- [[place-content]]
- [[place-items]]
- [[place-self]]
- [[placeholder|::placeholder]]
- [[placeholder-shown|:placeholder-shown]]
- [[playing|:playing]]
- [[pointer-events]]
- [[basic-shape#`polygon()`|polygon()]]
- [[position_value|<position>]]
- [[position]]
- [[pow|pow()]]
- [[prefix|prefix (@counter-style)]]
- [[print-color-adjust|print-color-adjust]]
- [[@property]]

### Q

- [[length#Q]]
- [[quotes]]

### R

- [[angle#rad]]
- [[length#rem]]
- [[radial-gradient]]
- [[range]]
- [[ratio]]
- [[ray]]
- [[read-only|:read-only]]
- [[read-write|:read-write]]
- [[shape#Syntax|shape#rect]]
- [[rem]]
- [[repeat]]
- [[repeating-conic-gradient]]
- [[repeating-linear-gradient]]
- [[repeating-radial-gradient]]
- [[required|:required]]
- [[resize]]
- [[_Resources/Markup And Styling/css/resolution]]
- `reversed()`
- [[revert]]
- [[color_value#Formal syntax|color_value#rgb]]
- [[color_value#Formal syntax|color_value#rgba]]
- [[right|:right]]
- [[right]]
- [[@page#page-margin-box-type]]
- [[root|:root]]
- [[_Resources/Markup And Styling/css/rotate]]
- [[_Resources/Markup And Styling/css/transform-function/rotate]]
- [[rotate3d]]
- [[rotatex]]
- [[rotatey]]
- [[rotatez]]
- [[round]]
- [[row-gap]]
- [[ruby-align]]
- `ruby-merge`
- [[ruby-position]]

### S

- [[saturate]]
- [[_Resources/Markup And Styling/css/scale]]
- [[_Resources/Markup And Styling/css/transform-function/scale]]
- [[scale3d]]
- [[scalex]]
- [[scaley]]
- [[scalez]]
- [[scope|:scope]]
- [[overflow]]
- [[scroll-behavior]]
- [[scroll-margin]]
- [[scroll-margin-block]]
- [[scroll-margin-block-end]]
- [[scroll-margin-block-start]]
- [[scroll-margin-bottom]]
- [[scroll-margin-inline]]
- [[scroll-margin-inline-end]]
- [[scroll-margin-inline-start]]
- [[scroll-margin-left]]
- [[scroll-margin-right]]
- [[scroll-margin-top]]
- [[scroll-padding]]
- [[scroll-padding-block]]
- [[scroll-padding-block-end]]
- [[scroll-padding-block-start]]
- [[scroll-padding-bottom]]
- [[scroll-padding-inline]]
- [[scroll-padding-inline-end]]
- [[scroll-padding-inline-start]]
- [[scroll-padding-left]]
- [[scroll-padding-right]]
- [[scroll-padding-top]]
- [[scroll-snap-align]]
- [[scroll-snap-stop]]
- [[scroll-snap-type]]
- [[scroll-timeline]]
- [[scroll-timeline]]
- [[scroll-timeline-axis]]
- [[scroll-timeline-name]]
- [[scrollbar-color]]
- [[scrollbar-gutter]]
- [[scrollbar-width]]
- [[selection|::selection]]
- `selector()`
- [[sepia]]
- [[shape]]
- [[shape-image-threshold]]
- [[shape-margin]]
- [[shape-outside]]
- [[sign]]
- [[sin]]
- [[size]]
- [[size-adjust]]
- [[skew]]
- [[skewx]]
- [[skewy]]
- [[slotted|::slotted]]
- [[speak-as]]
- [[spelling-error|::spelling-error]]
- [[sqrt]]
- [[src|src (@font-face)]]
- [[easing-function#Steps easing function|steps()]]
- [[string]]
- [[@font-feature-values#Using @styleset in a @font-feature-values rule|@styleset]]
- [[font-variant-alternates#styleset()|styleset()]]
- [[@font-feature-values#@stylistic|@stylistic]]
- [[font-variant-alternates#stylistic()|stylistic()]]
- [[suffix]]
- [[@supports]]
- `supports() (@import)`
- [[@font-feature-values#@swash|@swash]]
- [[font-variant-alternates#swash()|swash()]]
- [[symbols|symbols (@counter-style)]]
- [[symbols|symbols()]]
- [[_Resources/Markup And Styling/css/@property/syntax|syntax (@property)]]
- [[system|system (@counter-style)]]
- [[time#s]]

### T

- [[angle#turn]]
- [[tab-size]]
- [[table-layout]]
- [[tan]]
- [[target|:target]]
- `target-counter()`
- `target-counters()`
- [[target-text|::target-text]]
- `target-text()`
- [[target-within|:target-within]]
- [[text-align]]
- [[text-align-last]]
- [[text-combine-upright]]
- [[text-decoration]]
- [[text-decoration-color]]
- [[text-decoration-line]]
- [[text-decoration-skip]]
- [[text-decoration-skip-ink]]
- [[text-decoration-style]]
- [[text-decoration-thickness]]
- [[text-emphasis]]
- [[text-emphasis-color]]
- [[text-emphasis-position]]
- [[text-emphasis-style]]
- [[text-indent]]
- [[text-justify]]
- [[text-orientation]]
- [[text-overflow]]
- [[text-rendering]]
- [[text-shadow]]
- [[text-size-adjust]]
- [[text-transform]]
- [[text-underline-offset]]
- [[text-underline-position]]
- [[text-wrap]]
- [[time]]
- [[time-percentage]]
- [[timeline-scope]]
- [[easing-function]]
- [[top]]
- [[@page#Margin at-rules|@top-center]]
- [[touch-action]]
- [[transform]]
- [[transform-box]]
- [[transform-function]]
- [[transform-origin]]
- [[transform-style]]
- [[transition]]
- [[transition-delay]]
- [[transition-duration]]
- [[transition-property]]
- [[transition-timing-function]]
- [[_Resources/Markup And Styling/css/translate]]
- [[_Resources/Markup And Styling/css/transform-function/translate]]
- [[translate3d]]
- [[translatex]]
- [[translatey]]
- [[translatez]]
- `type()`

### U

- [[unicode-bidi]]
- [[unicode-range]]
- [[unset]]
- [[url|url()]]
- [[user-invalid|:user-invalid]]
- [[user-select]]
- [[user-valid|:user-valid]]
- [`user-zoom (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)

### V

- [[length#vh]]
- [[length#vmax]]
- [[length#vmin]]
- [[length#vw]]
- [[valid|:valid]]
- [[var()]]
- [[vertical-align]]
- `view()`
- [[view-timeline]]
- [[view-timeline-axis]]
- [[view-timeline-inset]]
- [[view-timeline-name]]
- [[view-transition|::view-transition]]
- [[view-transition-group|::view-transition-group]]
- [[view-transition-image-pair|::view-transition-image-pair]]
- [[view-transition-name]]
- [[view-transition-new|::view-transition-new]]
- [[view-transition-old|::view-transition-old]]
- [`@viewport`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [`viewport-fit (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [[visibility]]
- [[visited|:visited]]

### W

- [[where|:where]]
- [[white-space]]
- [[white-space-collapse]]
- `white-space-trim`
- [[widows]]
- [[_Resources/Markup And Styling/css/width]]
- [`width (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [[will-change]]
- [[word-break]]
- [[word-spacing]]
- [[overflow-wrap]]
- [[writing-mode]]

### X

- [[_Resources/Markup And Styling/css/resolution#x]]

### Z

- [[z-index]]
- [`zoom (@viewport)`](https://developer.mozilla.org/en-US/docs/Web/CSS)

### Others

- [[--|--*]]

Selectors
---------

The following are the various [selectors](css_selectors.md), which allow styles to be conditional based on various features of elements within the DOM.

### Basic selectors

**Basic selectors** are fundamental selectors; these are the most basic selectors that are frequently combined to create other, more complex selectors.

- [[universal_selectors|Universal selector]] `*`
- [[type_selectors|Type selector]] `elementname`
- [[class_selectors|Class selector]] `.classname`
- [[id_selectors|ID selector]] `#idname`
- [[attribute_selectors|Attribute selector]] `[attr=value]`

### Grouping selectors

[[selector_list|Selector list]] `A, B`

:   Specifies that both `A` and `B` elements are selected. This is a grouping method to select several matching elements.

### Combinators

Combinators are selectors that establish a relationship between two or more simple selectors, such as \"`A` is a child of `B`\" or \"`A` is adjacent to `B`\", creating a complex selector.

[Next-sibling combinator](next-sibling_combinator.md) `A + B`

:   Specifies that the elements selected by both `A` and `B` have the same parent and that the element selected by `B` immediately follows the element selected by `A` horizontally.

[Subsequent-sibling combinator](subsequent-sibling_combinator.md) `A ~ B`

:   Specifies that the elements selected by both `A` and `B` share the same parent and that the element selected by `A` comes before---but not necessarily immediately before---the element selected by `B`.

[Child combinator](child_combinator.md) `A > B`

:   Specifies that the element selected by `B` is the direct child of the element selected by `A`.

[Descendant combinator](descendant_combinator.md) `A B`

:   Specifies that the element selected by `B` is a descendant of the element selected by `A`, but is not necessarily a direct child.

[Column combinator](column_combinator.md) `A || B` [Experimental]

:   Specifies that the element selected by `B` is located within the table column specified by `A`. Elements which span multiple columns are considered to be a member of all of those columns.

### Pseudo

[Pseudo classes](pseudo-classes.md) `:`

:   Specifies a special state of the selected element(s).

[Pseudo elements](pseudo-elements.md) `::`

:   Represents entities that are not included in HTML.

See also [selectors in the Selectors specification](https://drafts.csswg.org/selectors/) and the [pseudo-element specification](https://drafts.csswg.org/css-pseudo/).

Concepts
--------

### Syntax and semantics

- [[_Resources/Markup And Styling/css/syntax|CSS syntax]]
- [[at-rule|At-rules]]
- [[cascade|Cascade]]
- [[comments|Comments]]
- [Descriptor](https://developer.mozilla.org/en-US/docs/Glossary/CSS_Descriptor)
- [[inheritance|Inheritance]]
- [[shorthand_properties|Shorthand properties]]
- [[specificity|Specificity]]
- [[value_definition_syntax|Value definition syntax]]
- [[css_values_and_units|CSS unit and value types]]
- [[css_functions|CSS functional notations]]

### Values

- [[actual_value|Actual value]]
- [[computed_value|Computed value]]
- [[initial_value|Initial value]]
- [[resolved_value|Resolved value]]
- [[specified_value|Specified value]]
- [[used_value|Used value]]

### Layout

- [Block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)
- [[introduction_to_the_css_box_model|Box model]]
- [[containing_block|Containing block]]
- [[layout_mode|Layout mode]]
- [[mastering_margin_collapsing|Margin collapsing]]
- [[replaced_element|Replaced elements]]
- [[stacking_context|Stacking context]]
- [[visual_formatting_model|Visual formatting model]]

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

- [Mozilla CSS extensions](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions) (prefixed with `-moz-`)
- [WebKit CSS extensions](https://developer.mozilla.org/en-US/docs/Web/CSS/WebKit_Extensions) (mostly prefixed with `-webkit-`)

External Links
--------------

- [CSS Indices (w3.org)](https://www.w3.org/TR/CSS/#indices)


---
© 2005--2023 MDN contributors.
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.

https://developer.mozilla.org/en-US/docs/Web/CSS/Reference
