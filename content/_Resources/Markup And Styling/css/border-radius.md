border-radius
=============

The `border-radius`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property rounds
the corners of an element\'s outer border edge. You can set a single
radius to make circular corners, or two radii to make elliptical
corners.

Try it
------

The radius applies to the whole [`background`](background.md), even if the
element has no border; the exact position of the clipping is defined by
the [`background-clip`](background-clip.md) property.

The `border-radius` property does not apply to table elements when
[`border-collapse`](border-collapse.md) is `collapse`.

**Note:** As with any shorthand property, individual sub-properties
cannot inherit, such as in `border-radius:0 0 inherit inherit`, which
would partially override existing definitions. Instead, the individual
longhand properties have to be used.

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`border-top-left-radius`](border-top-left-radius.md)
- [`border-top-right-radius`](border-top-right-radius.md)
- [`border-bottom-right-radius`](border-bottom-right-radius.md)
- [`border-bottom-left-radius`](border-bottom-left-radius.md)

Syntax
------

[css]

```css
/* The syntax of the first radius allows one to four values */
/* Radius is set for all 4 sides */
border-radius: 10px;

/* top-left-and-bottom-right | top-right-and-bottom-left */
border-radius: 10px 5%;

/* top-left | top-right-and-bottom-left | bottom-right */
border-radius: 2px 4px 2px;

/* top-left | top-right | bottom-right | bottom-left */
border-radius: 1px 0 3px 4px;

/* The syntax of the second radius allows one to four values */
/* (first radius values) / radius */
border-radius: 10px / 20px;

/* (first radius values) / top-left-and-bottom-right | top-right-and-bottom-left */
border-radius: 10px 5% / 20px 30px;

/* (first radius values) / top-left | top-right-and-bottom-left | bottom-right */
border-radius: 10px 5px 2em / 20px 25px 30%;

/* (first radius values) / top-left | top-right | bottom-right | bottom-left */
border-radius: 10px 5% / 20px 25em 30px 35em;

/* Global values */
border-radius: inherit;
border-radius: initial;
border-radius: revert;
border-radius: revert-layer;
border-radius: unset;
```

The `border-radius` property is specified as:

- one, two, three, or four [`<length>`](length.md) or
    [`<percentage>`](percentage.md) values. This is used to set a single
    radius for the corners.
- followed optionally by \"/\" and one, two, three, or four `<length>`
    or `<percentage>` values. This is used to set an additional radius,
    so you can have elliptical corners.

### Values

![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEUAAAA8BAMAAADCjmoTAAAAG1BMVEX////P5+YAAACAgIDQ6Obs7OxZWVnB2ddpaWkCF9iNAAAAcUlEQVRIx2NgUAIDBiwAIQNhGWMB6GoEsQC4GlZCahSIVqMoiBMIKamNqiGohoGAGlA4MzAL4gMiBgyjakbVjKoZSWrwly3iRJTPo2qIVIOrHhSC1YMMxKvBVncboanB1gZggqtRSwOCJKxqOkCAOHMAP4+YU9vmCzcAAAAASUVORK5CYII=)

[`<length>`](length.md)

:   Denotes the size of the circle radius, or the semi-major and
    semi-minor axes of the ellipse, using length values. Negative values
    are invalid.

[`<percentage>`](percentage.md)

:   Denotes the size of the circle radius, or the semi-major and
    semi-minor axes of the ellipse, using percentage values. Percentages
    for the horizontal axis refer to the width of the box; percentages
    for the vertical axis refer to the height of the box. Negative
    values are invalid.

For example:

[css]

```css
border-radius: 1em/5em;

/* It is equivalent to: */
border-top-left-radius: 1em 5em;
border-top-right-radius: 1em 5em;
border-bottom-right-radius: 1em 5em;
border-bottom-left-radius: 1em 5em;
```

[css]

```css
border-radius: 4px 3px 6px / 2px 4px;

/* It is equivalent to: */
border-top-left-radius: 4px 2px;
border-top-right-radius: 3px 4px;
border-bottom-right-radius: 6px 2px;
border-bottom-left-radius: 3px 4px;
```

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-top-left-radius.md): |
|                                   |     `0`                           |
|                                   | -   [](border-top-right-radius.md): |
|                                   |     `0`                           |
|                                   | -   [](border-bottom-right-radius.md): |
|                                   |     `0`                           |
|                                   | -   [](border-bottom-left-radius.md): |
|                                   |     `0`                           |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements; but User Agents are |
|                                   | not required to apply to `table`  |
|                                   | and `inline-table` elements when  |
|                                   | [](border-collapse.md) |
|                                   | is `collapse`. The behavior on    |
|                                   | internal table elements is        |
|                                   | undefined for the moment.. It     |
|                                   | also applies to                   |
|                                   | [`|
|                                   | ::first-letter`](::first-letter). |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| Percentages                       | refer to the corresponding        |
|                                   | dimension of the border box       |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-bottom-left-radius.md): |
|                                   |     two absolute                  |
|                                   |     [`<length>`](length.md)s or      |
|                                   |     [`<percentage>`](percentage.md)s |
|                                   | -   [](border-bottom-right-radius.md): |
|                                   |     two absolute                  |
|                                   |     [`<length>`](length.md)s or      |
|                                   |     [`<percentage>`](percentage.md)s |
|                                   | -   [](border-top-left-radius.md): |
|                                   |     two absolute                  |
|                                   |     [`<length>`](length.md)s or      |
|                                   |     [`<percentage>`](percentage.md)s |
|                                   | -   [](border-top-right-radius.md): |
|                                   |     two absolute                  |
|                                   |     [`<length>`](length.md)s or      |
|                                   |     [`<percentage>`](percentage.md)s |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-top-left-radius.md): |
|                                   |     a                             |
|                                   |                                   |
|                                   |   [length](length.md#interpolation), |
|                                   |     [](percentage.md#interpolation) |
|                                   |     or calc();                    |
|                                   | -   [](border-top-right-radius.md): |
|                                   |     a                             |
|                                   |                                   |
|                                   |   [length](length.md#interpolation), |
|                                   |     [](percentage.md#interpolation) |
|                                   |     or calc();                    |
|                                   | -   [](border-bottom-right-radius.md): |
|                                   |     a                             |
|                                   |                                   |
|                                   |   [length](length.md#interpolation), |
|                                   |     [](percentage.md#interpolation) |
|                                   |     or calc();                    |
|                                   | -   [](border-bottom-left-radius.md): |
|                                   |     a                             |
|                                   |                                   |
|                                   |   [length](length.md#interpolation), |
|                                   |     [](percentage.md#interpolation) |
|                                   |     or calc();                    |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
border-radius = 
  <length-percentage [0,∞]> ]?  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Live Samples

- Sample 1 : https://jsfiddle.net/Tripad/qnGKj/2/>
- Sample 2 : https://jsfiddle.net/Tripad/qnGKj/3/>
- Sample 3 : https://jsfiddle.net/Tripad/qnGKj/4/>
- Sample 4 : https://jsfiddle.net/Tripad/qnGKj/5/>
- Sample 5 : https://jsfiddle.net/Tripad/qnGKj/6/>

Specifications
--------------

  ----------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  border-radius]](https://drafts.csswg.org/css-backgrounds/#border-radius)

  ----------------------------------------------------------------------------------

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

`4_values_for_4_corners`

4

12

4

9

10.5

5

≤37

18

4

11

4.2

1.0

`border-radius`

4Chrome ignores `border-radius` on `<select>` elements unless
`-webkit-appearance` is overridden to an appropriate value.

1

1212

4\[\"Before Firefox 50, border styles of rounded corners (with
`border-radius`) were always rendered as if `border-style` was `solid`.
This has been fixed in Firefox 50.\", \"To conform to the CSS3 standard,
Firefox 4 changes the handling of
[`<percentage>`](https://developer.mozilla.org/docs/Web/CSS/percentage)
values to match the specification. You can specify an ellipse as a
border on an arbitrary sized element with `border-radius: 50%;`. Firefox
4 also makes rounded corners clip content and images if
[`overflow`](https://developer.mozilla.org/docs/Web/CSS/overflow)`: visible`
is not set.\"\]

1--12

9

10.5Before Opera 11.60, replaced elements with `border-radius` do not
have rounded corners.

5Safari ignores `border-radius` on `<select>` elements unless
`-webkit-appearance` is overridden to an appropriate value.

3

≤372

18

4Before Firefox 50, border styles of rounded corners (with
`border-radius`) were always rendered as if `border-style` was `solid`.
This has been fixed in Firefox 50.

4--14

11

4.2Safari ignores `border-radius` on `<select>` elements unless
`-webkit-appearance` is overridden to an appropriate value.

1

1.0

`elliptical_borders`

1Before Chrome 4, the slash `/` notation is unsupported. If two values
are specified, then an elliptical border is drawn on all four corners.
`-webkit-border-radius: 40px 10px;` is equivalent to
`border-radius: 40px / 10px;`.

12

4

9

10.5

3Before Safari 5, the slash `/` notation is unsupported. If two values
are specified, then an elliptical border is drawn on all four corners.
`-webkit-border-radius: 40px 10px;` is equivalent to
`border-radius: 40px / 10px;`.

≤37

18

4

11

4.2

1.0

`percentages`

8

12

4Before Firefox 4, `<percentage>` values are implemented in a
non-standard way. Both horizontal and vertical radii were relative to
the width of the border box.

9

11.5Before Opera 11.5, the implementation of `<percentage>` values was
buggy.

5.1

≤37

18

4

11.5

5

1.0

See also
--------

- Border-radius-related CSS properties:
    [`border-top-left-radius`](border-top-left-radius.md),
    [`border-top-right-radius`](border-top-right-radius.md),
    [`border-bottom-right-radius`](border-bottom-right-radius.md),
    [`border-bottom-left-radius`](border-bottom-left-radius.md),
    [`border-start-start-radius`](border-start-start-radius.md),
    [`border-start-end-radius`](border-start-end-radius.md),
    [`border-end-start-radius`](border-end-start-radius.md),
    [`border-end-end-radius`](border-end-end-radius.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius>
