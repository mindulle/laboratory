-webkit-text-stroke
===================

The `-webkit-text-stroke`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies the [width](length.md) and [color](color_value.md) of strokes for
text characters. This is a shorthand property for the longhand
properties [`-webkit-text-stroke-width`](-webkit-text-stroke-width.md) and
[`-webkit-text-stroke-color`](-webkit-text-stroke-color.md).

[css]

```css
/* Width and color values */
-webkit-text-stroke: 4px navy;
text-stroke: 4px navy;

/* Global values */
-webkit-text-stroke: inherit;
-webkit-text-stroke: initial;
-webkit-text-stroke: revert;
-webkit-text-stroke: revert-layer;
-webkit-text-stroke: unset;
```

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`-webkit-text-stroke-color`](-webkit-text-stroke-color.md)
- [`-webkit-text-stroke-width`](-webkit-text-stroke-width.md)

Syntax
------

### Values

[`<length>`](length.md)

:   The width of the stroke.

[`<color>`](color_value.md)

:   The color of the stroke.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](-webkit-text-stroke-width.md): |
|                                   |     `0`                           |
|                                   | -   [](-webkit-text-stroke-color.md): |
|                                   |     `currentcolor`                |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements                      |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | yes                               |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](-webkit-text-stroke-width.md): |
|                                   |     absolute [`<length>`](length.md) |
|                                   | -   [](-webkit-text-stroke-color.md): |
|                                   |     computed color                |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](-webkit-text-stroke-width.md): |
|                                   |     discrete                      |
|                                   | -   [](-webkit-text-stroke-color.md): |
|                                   |     a                             |
|                                   |     [](color_value.md#interpolation) |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
-webkit-text-stroke = 
  <line-width>  ||
  <color>       

<line-width> = 
  <length [0,∞]>  |
  thin            |
  medium          |
  thick           
```

Examples
--------

### Adding a red text stroke

#### HTML

[html]

```html
<p id="example">The stroke of this text is red.</p>
```

#### CSS

[css]

```css
#example {
  font-size: 3em;
  margin: 0;
  -webkit-text-stroke: 2px red;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------

  [Compatibility Standard\
  [\#
  the-webkit-text-stroke]](https://compat.spec.whatwg.org/#the-webkit-text-stroke)

  ------------------------------------------------------------------------------------------

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

`-webkit-text-stroke`

4

15

49

No

15

3

4

18

49

14

2

1.0

See also
--------

- [Surfin\' Safari blog post announcing this
    feature](https://webkit.org/blog/85/introducing-text-stroke/)
- [CSS-Tricks article explaining this
    feature](https://css-tricks.com/adding-stroke-to-web-text/)
- [`-webkit-text-stroke-width`](-webkit-text-stroke-width.md)
- [`-webkit-text-stroke-color`](-webkit-text-stroke-color.md)
- [`-webkit-text-fill-color`](-webkit-text-fill-color.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-stroke>
