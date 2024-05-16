outline-style
=============

The `outline-style`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the style of an element\'s outline. An outline is a line that is drawn
around an element, outside the [`border`](border.md).

Try it
------

It is often more convenient to use the shorthand property
[`outline`](outline.md) when defining the appearance of an outline.

Syntax
------

[css]

```css
/* Keyword values */
outline-style: auto;
outline-style: none;
outline-style: dotted;
outline-style: dashed;
outline-style: solid;
outline-style: double;
outline-style: groove;
outline-style: ridge;
outline-style: inset;
outline-style: outset;

/* Global values */
outline-style: inherit;
outline-style: initial;
outline-style: revert;
outline-style: revert-layer;
outline-style: unset;
```

The `outline-style` property is specified as any one of the values
listed below.

### Values

[`auto`](#auto)

:   Permits the user agent to render a custom outline style.

[`none`](#none)

:   No outline is used. The [`outline-width`](outline-width.md) is `0`.

[`dotted`](#dotted)

:   The outline is a series of dots.

[`dashed`](#dashed)

:   The outline is a series of short line segments.

[`solid`](#solid)

:   The outline is a single line.

[`double`](#double)

:   The outline is two single lines. The
    [`outline-width`](outline-width.md) is the sum of the two lines and the
    space between them.

[`groove`](#groove)

:   The outline looks as though it were carved into the page.

[`ridge`](#ridge)

:   The opposite of `groove`: the outline looks as though it were
    extruded from the page.

[`inset`](#inset)

:   The outline makes the box look as though it were embedded in the
    page.

[`outset`](#outset)

:   The opposite of `inset`: the outline makes the box look as though it
    were coming out of the page.

Formal definition
-----------------

  ---------------------------------- ------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     by computed value type
  ---------------------------------- ------------------------

Formal syntax
-------------

```
outline-style = 
  auto                  |
  <outline-line-style>  
```

Examples
--------

### Setting outline style to auto

The `auto` value indicates a custom outline style, described in [the
specification](https://www.w3.org/TR/css-ui-3/#outline-style) as
\"typically a style \[that\] is either a user interface default for the
platform, or perhaps a style that is richer than can be described in
detail in CSS, e.g. a rounded edge outline with semi-translucent outer
pixels that appears to glow\".

#### HTML

[html]

```html
<div>
  <p class="auto">Outline Demo</p>
</div>
```

#### CSS

[css]

```css
.auto {
  outline-style: auto; /* same result as "outline: auto" */
}

/* To make the Demo clearer */
* {
  outline-width: 10px;
  padding: 15px;
}
```

#### Result

### Setting outline style to dashed and dotted

#### HTML

[html]

```html
<div>
  <div class="dotted">
    <p class="dashed">Outline Demo</p>
  </div>
</div>
```

#### CSS

[css]

```css
.dotted {
  outline-style: dotted; /* same result as "outline: dotted" */
}
.dashed {
  outline-style: dashed;
}

/* To make the Demo clearer */
* {
  outline-width: 10px;
  padding: 15px;
}
```

#### Result

### Setting outline style to solid and double

#### HTML

[html]

```html
<div>
  <div class="solid">
    <p class="double">Outline Demo</p>
  </div>
</div>
```

#### CSS

[css]

```css
.solid {
  outline-style: solid;
}
.double {
  outline-style: double;
}

/* To make the Demo clearer */
* {
  outline-width: 10px;
  padding: 15px;
}
```

#### Result

### Setting outline style to groove and ridge

#### HTML

[html]

```html
<div>
  <div class="groove">
    <p class="ridge">Outline Demo</p>
  </div>
</div>
```

#### CSS

[css]

```css
.groove {
  outline-style: groove;
}
.ridge {
  outline-style: ridge;
}

/* To make the Demo clearer */
* {
  outline-width: 10px;
  padding: 15px;
}
```

#### Result

### Setting outline style to inset and outset

#### HTML

[html]

```html
<div>
  <div class="inset">
    <p class="outset">Outline Demo</p>
  </div>
</div>
```

#### CSS

[css]

```css
.inset {
  outline-style: inset;
}
.outset {
  outline-style: outset;
}

/* To make the Demo clearer */
* {
  outline-width: 10px;
  padding: 15px;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------

  [CSS Basic User Interface Module Level 4\
  [\#
  outline-style]](https://drafts.csswg.org/css-ui/#outline-style)

  -------------------------------------------------------------------------

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

`outline-style`

1

12

1.5Before Firefox 88, an outline does not follow the shape of
`border-radius`.

1--3.6

8

7

1.2

2

18

4Before Firefox 88, an outline does not follow the shape of
`border-radius`.

10.1

1

1.0

`auto`

1

79

1.5

No

15

1.2

≤37

18

4

14

1

1.0

See also
--------

- [`outline`](outline.md)
- [`outline-color`](outline-color.md)
- [`outline-width`](outline-width.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/outline-style>
