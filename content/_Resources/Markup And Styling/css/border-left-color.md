border-left-color
=================

The `border-left-color` CSS property sets the color of an element\'s
left [border](border.md). It can also be set with the shorthand CSS
properties [`border-color`](border-color.md) or
[`border-left`](border-left.md).

Try it
------

Syntax
------

[css]

```css
/* <color> values */
border-left-color: red;
border-left-color: #ffbb00;
border-left-color: rgb(255 0 0);
border-left-color: hsl(100deg 50% 25% / 0.75);
border-left-color: currentcolor;
border-left-color: transparent;

/* Global values */
border-left-color: inherit;
border-left-color: initial;
border-left-color: revert;
border-left-color: revert-layer;
border-left-color: unset;
```

The `border-left-color` property is specified as a single value.

### Values

[`<color>`](color_value.md)

:   The color of the left border.

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
border-left-color = 
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
  border-left-color: red;
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

`border-left-color`

1

12

1Firefox also supports the non-standard `-moz-border-left-colors` CSS
property that sets the bottom border to multiple colors.

4

3.5

1

4.4

18

4Firefox also supports the non-standard `-moz-border-left-colors` CSS
property that sets the bottom border to multiple colors.

10.1

1

1.0

See also
--------

- The border-related CSS shorthand properties: [`border`](border.md),
    [`border-left`](border-left.md), and [`border-color`](border-color.md).
- The color-related CSS properties for the other borders:
    [`border-right-color`](border-right-color.md),
    [`border-bottom-color`](border-bottom-color.md), and
    [`border-top-color`](border-top-color.md).
- The other border-related CSS properties applying to the same border:
    [`border-left-style`](border-left-style.md) and
    [`border-left-width`](border-left-width.md).
- The default [`currentcolor`](color_value.md#currentcolor_keyword) color
    value.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-left-color>
