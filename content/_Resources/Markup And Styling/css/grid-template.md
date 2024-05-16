grid-template
=============

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `grid-template` CSS property is a [](shorthand_properties.md) for defining [grid
columns](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Column),
[grid rows](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Row),
and [grid
areas](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Areas).

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`grid-template-areas`](grid-template-areas.md)
- [`grid-template-columns`](grid-template-columns.md)
- [`grid-template-rows`](grid-template-rows.md)

Syntax
------

[css]

```css
/* Keyword value */
grid-template: none;

/* grid-template-rows / grid-template-columns values */
grid-template: 100px 1fr / 50px 1fr;
grid-template: auto 1fr / auto 1fr auto;
grid-template: [linename] 100px / [columnname1] 30% [columnname2] 70%;
grid-template: fit-content(100px) / fit-content(40%);

/* grid-template-areas grid-template-rows / grid-template-column values */
grid-template:
  "a a a"
  "b b b";
grid-template:
  "a a a" 20%
  "b b b" auto;
grid-template:
  [header-top] "a a a" [header-bottom]
  [main-top] "b b b" 1fr [main-bottom]
  / auto 1fr auto;

/* Global values */
grid-template: inherit;
grid-template: initial;
grid-template: revert;
grid-template: revert-layer;
grid-template: unset;
```

### Values

[`none`](#none)

:   Is a keyword that sets all three longhand properties to `none`,
    meaning there is no explicit grid. There are no named grid areas.
    Rows and columns will be implicitly generated; their size will be
    determined by the [`grid-auto-rows`](grid-auto-rows.md) and
    [`grid-auto-columns`](grid-auto-columns.md) properties.

[`<'grid-template-rows'> / <'grid-template-columns'>`](#grid-template-rows_grid-template-columns)

:   Sets [`grid-template-rows`](grid-template-rows.md) and
    [`grid-template-columns`](grid-template-columns.md) to the specified
    values, and sets [`grid-template-areas`](grid-template-areas.md) to
    `none`.

[`[ <line-names>? <string> <track-size>? <line-names>? ]+ [ / <explicit-track-list> ]?`](#_line-names_string_track-size_line-names_explicit-track-list_)

:   Sets [`grid-template-areas`](grid-template-areas.md) to the strings
    listed, [`grid-template-rows`](grid-template-rows.md) to the track
    sizes following each string (filling in `auto` for any missing
    sizes), and splicing in the named lines defined before/after each
    size, and [`grid-template-columns`](grid-template-columns.md) to the
    track listing specified after the slash (or `none`, if not
    specified).

    **Note:** The [`repeat()`](repeat) function isn\'t allowed in these
    track listings, as the tracks are intended to visually line up
    one-to-one with the rows/columns in the \"ASCII art\".

**Note:** The [`grid`](_Resources/Markup%20And%20Styling/css/grid.md) shorthand accepts the same syntax, but also
resets the implicit grid properties to their initial values. Use `grid`
(as opposed to `grid-template`) to prevent these values from cascading
in separately.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](grid-template-columns.md): |
|                                   |     `none`                        |
|                                   | -   [](grid-template-rows.md): |
|                                   |     `none`                        |
|                                   | -   [](grid-template-areas.md): |
|                                   |     `none`                        |
+-----------------------------------+-----------------------------------+
| Applies to                        | grid containers                   |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| Percentages                       | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](grid-template-columns.md): |
|                                   |     refer to corresponding        |
|                                   |     dimension of the content area |
|                                   | -   [](grid-template-rows.md): |
|                                   |     refer to corresponding        |
|                                   |     dimension of the content area |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](grid-template-columns.md): |
|                                   |     as specified, but with        |
|                                   |     relative lengths converted    |
|                                   |     into absolute lengths         |
|                                   | -   [](grid-template-rows.md): |
|                                   |     as specified, but with        |
|                                   |     relative lengths converted    |
|                                   |     into absolute lengths         |
|                                   | -   [](grid-template-areas.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](grid-template-columns.md): |
|                                   |     simple list of length,        |
|                                   |     percentage, or calc, provided |
|                                   |     the only differences are in   |
|                                   |     the values of the length,     |
|                                   |     percentage, or calc           |
|                                   |     components in the list        |
|                                   | -   [](grid-template-rows.md): |
|                                   |     simple list of length,        |
|                                   |     percentage, or calc, provided |
|                                   |     the only differences are in   |
|                                   |     the values of the length,     |
|                                   |     percentage, or calc           |
|                                   |     components in the list        |
|                                   | -   [](grid-template-areas.md): |
|                                   |     discrete                      |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
grid-template = 
  none                                                |
  [ <'grid-template-rows'> / <'grid-template-columns'> ]  |
  [ <line-names>? <string> <track-size>? <line-names>? ]+ [ / <explicit-track-list> ]?  

<line-names> = 
  '[' <custom-ident>* ']'  

<track-size> = 
  <track-breadth>                                   |
  minmax( <inflexible-breadth> , <track-breadth> )  |
  fit-content( <length-percentage> )                

<explicit-track-list> = 
  [ <line-names>? <track-size> ]+ <line-names>?  

<track-breadth> = 
  <length-percentage>  |
  <flex>               |
  min-content          |
  max-content          |
  auto                 

<inflexible-breadth> = 
  <length-percentage>  |
  min-content          |
  max-content          |
  auto                 

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Defining a grid template

#### CSS

[css]

```css
#page {
  display: grid;
  width: 100%;
  height: 200px;
  grid-template:
    [header-left] "head head" 30px [header-right]
    [main-left] "nav  main" 1fr [main-right]
    [footer-left] "nav  foot" 30px [footer-right]
    / 120px 1fr;
}

header {
  background-color: lime;
  grid-area: head;
}

nav {
  background-color: lightblue;
  grid-area: nav;
}

main {
  background-color: yellow;
  grid-area: main;
}

footer {
  background-color: red;
  grid-area: foot;
}
```

#### HTML

[html]

```html
<section id="page">
  <header>Header</header>
  <nav>Navigation</nav>
  <main>Main area</main>
  <footer>Footer</footer>
</section>
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------

  [CSS Grid Layout Module Level 2\
  [\#
  explicit-grid-shorthand]](https://drafts.csswg.org/css-grid/#explicit-grid-shorthand)

  -----------------------------------------------------------------------------------------------

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`grid-template`

57

16

52

No

44

10.1

57

57

52

43

10.3

6.0

See also
--------

- Related CSS properties: [`grid-template-rows`](grid-template-rows.md),
    [`grid-template-columns`](grid-template-columns.md),
    [`grid-template-areas`](grid-template-areas.md)
- Grid Layout Guide: *[](grid_layout_using_line-based_placement.md)*
- Grid Layout Guide: *[](grid_template_areas.md#grid_definition_shorthands)*
- Video tutorial: *[Grid Template
    shorthand](https://gridbyexample.com/video/grid-template-shorthand/)*

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template>
