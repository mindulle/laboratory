border-bottom-color
===================

The `border-bottom-color` CSS property sets the color of an element\'s
bottom [border](border.md). It can also be set with the shorthand CSS
properties [`border-color`](border-color.md) or
[`border-bottom`](border-bottom.md).

Try it
------

Syntax
------

[css]

```css
/* <color> values */
border-bottom-color: red;
border-bottom-color: #ffbb00;
border-bottom-color: rgb(255, 0, 0);
border-bottom-color: hsl(100deg 50% 25% / 0.75);
border-bottom-color: currentcolor;
border-bottom-color: transparent;

/* Global values */
border-bottom-color: inherit;
border-bottom-color: initial;
border-bottom-color: revert;
border-bottom-color: revert-layer;
border-bottom-color: unset;
```

The `border-bottom-color` property is specified as a single value.

### Values

[`<color>`](color_value.md)

:   The color of the bottom border.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------
  [Initial value](initial_value.md)     `currentcolor`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter).
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   computed color
  Animation type                     a [color](color_value.md#interpolation)
  ---------------------------------- ----------------------------------------------------------------------

Formal syntax
-------------

```
border-bottom-color = 
  <color>  
```

Examples
--------

### A simple div with a border

#### HTML

[html]

```html
<div class="mybox">
  <p>
    This is a box with a border around it. Note which side of the box is
    <span class="redtext">red</span>.
  </p>
</div>
```

#### CSS

[css]

```css
.mybox {
  border: solid 0.3em gold;
  border-bottom-color: red;
  width: auto;
}

.redtext {
  color: red;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  border-color]](https://drafts.csswg.org/css-backgrounds/#border-color)

  --------------------------------------------------------------------------------

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

`border-bottom-color`

1

12

1Firefox also supports the non-standard
[`-moz-border-bottom-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-bottom-colors)
CSS property that sets the bottom border to multiple colors.

4

3.5

1

4.4

18

4Firefox also supports the non-standard
[`-moz-border-bottom-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-bottom-colors)
CSS property that sets the bottom border to multiple colors.

10.1

1

1.0

See also
--------

- The border-related CSS shorthand properties: [`border`](border.md),
    [`border-bottom`](border-bottom.md), and
    [`border-color`](border-color.md).
- The color-related CSS properties for the other borders:
    [`border-right-color`](border-right-color.md),
    [`border-top-color`](border-top-color.md), and
    [`border-left-color`](border-left-color.md).
- The other border-related CSS properties applying to the same border:
    [`border-bottom-style`](border-bottom-style.md) and
    [`border-bottom-width`](border-bottom-width.md).
- The default [`currentcolor`](color_value.md#currentcolor_keyword) color
    value.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-color>
