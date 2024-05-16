\<line-style\>
==============

The `<line-style>`
[enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
value type represents keyword values that define the style of a line, or
the lack of a line. The `<line-style>` keyword values are used in the
following longhand and shorthand [border](css_backgrounds_and_borders.md)
and [column](css_multicol_layout.md) properties:

- [`border`](border.md), [`border-style`](border-style.md)
- [`border-block`](border-block.md),
    [`border-block-style`](border-block-style.md)
- [`border-block-end`](border-block-end.md),
    [`border-block-end-style`](border-block-end-style.md)
- [`border-block-start`](border-block-start.md),
    [`border-block-start-style`](border-block-start-style.md)
- [`border-bottom`](border-bottom.md),
    [`border-bottom-style`](border-bottom-style.md)
- [`border-inline`](border-inline.md),
    [`border-inline-style`](border-inline-style.md)
- [`border-inline-end`](border-inline-end.md),
    [`border-inline-end-style`](border-inline-end-style.md)
- [`border-inline-start`](border-inline-start.md),
    [`border-inline-start-style`](border-inline-start-style.md)
- [`border-left`](border-left.md),
    [`border-left-style`](border-left-style.md)
- [`border-right`](border-right.md),
    [`border-right-style`](border-right-style.md)
- [`border-top`](border-top.md), [`border-top-style`](border-top-style.md)
- [`column-rule`](column-rule.md),
    [`column-rule-style`](column-rule-style.md)

Syntax
------

[css]

```css
<line-style> = none | hidden | dotted | dashed | solid | double | groove | ridge | inset | outset
```

### Values

The `<line-style>` enumerated type is specified using one of the values
listed below:

[`none`](#none)

:   Displays no line. The computed value of the line width is `0` even
    if a width value is specified. In the case of table cell and border
    collapsing, the `none` value has the *lowest* priority. If any other
    conflicting border is set, it will be displayed. The `none` value is
    similar to `hidden`.

[`hidden`](#hidden)

:   Displays no line. The computed width of the line is `0` even if a
    width value is specified. In the case of table cell and border
    collapsing, the `hidden` value has the *highest* priority. If any
    other conflicting border is set, it won\'t be displayed. The
    `hidden` value is similar to `none`, but `hidden` is not a valid
    value for outline styles.

[`dotted`](#dotted)

:   Displays a series of round dots. The radius of the dots is half the
    computed value of the line\'s width. The spacing of the dots is not
    defined by the specification and is implementation-specific.

[`dashed`](#dashed)

:   Displays a series of short square-ended dashes or line segments. The
    exact size and length of the segments are not defined by the
    specification and are implementation-specific.

[`solid`](#solid)

:   Displays a single, straight solid line.

[`double`](#double)

:   Displays two straight lines with some space between them. The length
    of the lines adds up to the pixel size defined by the line\'s width.

[`groove`](#groove)

:   Displays a border with a carved appearance. This value is the
    opposite of `ridge`.

[`ridge`](#ridge)

:   Displays a border with an extruded appearance. This value is the
    opposite of `groove`.

[`inset`](#inset)

:   Displays a border that makes the element appear embedded. This value
    is the opposite of `outset`. When applied to a table cell border and
    [`border-collapse`](border-collapse.md) is set to `collapsed`, this
    value behaves like `groove`.

[`outset`](#outset)

:   Displays a border that makes the element appear embossed. This value
    is the opposite of `inset`. When applied to a table cell with
    [`border-collapse`](border-collapse.md) set to `collapsed`, this value
    behaves like `ridge`.

**Note:** When `<outline-style>` is used as the value type for
[`outline`](outline.md) and [`outline-style`](outline-style.md) properties, it
is similar to `<line-style>`, but does not support `hidden` and includes
the `auto` value. When `auto` is set, the user-agent defined
`<line-style>` value is used.

Examples
--------

The first example demonstrates all the `<line-style>` keyword values.
The second example demonstrates how some line style colors may display
in unexpected ways.

### Defining line styles

This example shows all the `<line-style>` values as values for the CSS
[`border-style`](border-style.md) and
[`column-rule-style`](column-rule-style.md) properties.

#### HTML

This example uses multiple
[`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
elements, each with a class representing the `<line-style>` value that
is being demonstrated.

[html]

```html
<div class="<line-style>">
  <p><line-style></p>
  <p>a b c d e f g h i j k l m n o p q r s t u v w x y z</p>
</div>
```

#### CSS

In the CSS for this example, the border and the column-rule for all the
`<p>` elements is defined to have a width of `7px` and the style value
of `double`. For each paragraph, the `double` value is then overridden
by specifying a different `<line-style>` value for the `border-style`
and `column-rule-style` properties.

[css]

```css
p {
  padding: 5px;
  border: double 7px #bada55;
}
p + p {
  columns: 3;
  column-gap: 20px;
  column-rule: double 7px;
  border-color: #000000;
}
.none p {
  border-style: none;
  column-rule-style: none;
}
.hidden p {
  border-style: hidden;
  column-rule-style: hidden;
}
.dotted p {
  border-style: dotted;
  column-rule-style: dotted;
}
.dashed p {
  border-style: dashed;
  column-rule-style: dashed;
}
.solid p {
  border-style: solid;
  column-rule-style: solid;
}
.double p {
  border-style: double;
  column-rule-style: double;
}
.groove p {
  border-style: groove;
  column-rule-style: groove;
}
.ridge p {
  border-style: ridge;
  column-rule-style: ridge;
}
.inset p {
  border-style: inset;
  column-rule-style: inset;
}
.outset p {
  border-style: outset;
  column-rule-style: outset;
}
```

#### Result

Notice that the black border is not always black.

### Defining line styles and colors

This example demonstrates line-style and color choice. With some
`<line-style>` keyword values, the color of the line may not be what you
expect. To create the required \"3D\" effect of `groove,` `ridge`,
`inset`, and `outset` styles when displaying these values in black or
white, user agents use different color calculations than any other
color-line combinations.

#### HTML

This example uses multiple
[`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
elements, each with a different `border-color` set as an inline
[`style`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/style).

[html]

```html
<div style="border-color: #000000"></div>
```

#### CSS

The four sides of each `<div>` have a different `<line-style>` value,
and each list item has a different [`<color>`](color_value.md) value. We
use [generated content](content.md) to display the CSS declared inline.

[css]

```css
div {
  border-width: 10px;
  border-style: inset groove ridge outset;
  padding: 5px;
}
div::before {
  content: attr(style);
}
```

#### Result

Notice that the almost-black color of `#000001` may be different from
the actual black, and the contrast between the dark and light edges is
more noticeable when using lighter colors.

Specifications
--------------

  --------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  typedef-line-style]](https://drafts.csswg.org/css-backgrounds/#typedef-line-style)

  --------------------------------------------------------------------------------------------

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

`line-style`

1

12

1

4

3.5

1

3

18

4

14

3

1.0

See also
--------

- [CSS backgrounds and borders](css_backgrounds_and_borders.md) module
- [CSS basic user interface](css_basic_user_interface.md) module
- [CSS multi-column layout](css_multicol_layout.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/line-style>
