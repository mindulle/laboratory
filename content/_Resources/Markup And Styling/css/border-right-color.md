border-right-color
==================

The `border-right-color` CSS property sets the color of an element\'s
right [border](border.md). It can also be set with the shorthand CSS
properties [`border-color`](border-color.md) or
[`border-right`](border-right.md).

Try it
------

Syntax
------

[css]

```css
/* <color> values */
border-right-color: red;
border-right-color: #ffbb00;
border-right-color: rgb(255 0 0);
border-right-color: hsl(100deg 50% 25% / 0.75);
border-right-color: currentcolor;
border-right-color: transparent;

/* Global values */
border-right-color: inherit;
border-right-color: initial;
border-right-color: revert;
border-right-color: revert-layer;
border-right-color: unset;
```

The `border-right-color` property is specified as a single value.

### Values

[`<color>`](color_value.md)

:   The color of the right border.

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
border-right-color = 
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
  border-right-color: red;
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

`border-right-color`

1

12

1Firefox also supports the non-standard
[`-moz-border-right-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-right-colors)
CSS property that sets the right border to multiple colors.

4

3.5

1

4.4

18

4Firefox also supports the non-standard
[`-moz-border-right-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-right-colors)
CSS property that sets the right border to multiple colors.

10.1

1

1.0

See also
--------

- The border-related CSS shorthand properties: [`border`](border.md),
    [`border-right`](border-right.md), and [`border-color`](border-color.md).
- The color-related CSS properties for the other borders:
    [`border-left-color`](border-left-color.md),
    [`border-bottom-color`](border-bottom-color.md), and
    [`border-top-color`](border-top-color.md).
- The other border-related CSS properties applying to the same border:
    [`border-right-style`](border-right-style.md) and
    [`border-right-width`](border-right-width.md).
- The default [`currentcolor`](color_value.md#currentcolor_keyword) color
    value.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-right-color>
