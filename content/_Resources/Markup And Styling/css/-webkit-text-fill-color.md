-webkit-text-fill-color
=======================

The `-webkit-text-fill-color` CSS property specifies the fill
[color](color_value.md) of characters of text. If this property is not set,
the value of the [`color`](_Resources/Markup%20And%20Styling/css/color.md) property is used.

Syntax
------

[css]

```css
/* <color> values */
-webkit-text-fill-color: red;
-webkit-text-fill-color: #000000;
-webkit-text-fill-color: rgb(100 200 0);

/* Global values */
-webkit-text-fill-color: inherit;
-webkit-text-fill-color: initial;
-webkit-text-fill-color: revert;
-webkit-text-fill-color: revert-layer;
-webkit-text-fill-color: unset;
```

### Values

[`<color>`](#color)

:   The foreground fill color of the element\'s text content.

Formal definition
-----------------

  ---------------------------------- --------------------------------------
  [Initial value](initial_value.md)     `currentcolor`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   computed color
  Animation type                     a [color](color_value.md#interpolation)
  ---------------------------------- --------------------------------------

Formal syntax
-------------

```
-webkit-text-fill-color = 
  <color>  
```

Examples
--------

### Changing the fill color

#### CSS

[css]

```css
p {
  margin: 0;
  font-size: 3em;
  -webkit-text-fill-color: green;
}
```

#### HTML

[html]

```html
<p>This text is green.</p>
```

#### Results

Specifications
--------------

  --------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------

  [Compatibility Standard\
  [\#
  the-webkit-text-fill-color]](https://compat.spec.whatwg.org/#the-webkit-text-fill-color)

  --------------------------------------------------------------------------------------------------

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

`-webkit-text-fill-color`

1

12

49

No

15

3

37

18

49

15

2

1.0

See also
--------

- [Surfin\' Safari blog post announcing this
    feature](https://webkit.org/blog/85/introducing-text-stroke/)
- [CSS-Tricks article explaining this
    feature](https://css-tricks.com/adding-stroke-to-web-text/)
- [`-webkit-text-stroke-color`](-webkit-text-stroke-color.md)
- [`-webkit-text-stroke-width`](-webkit-text-stroke-width.md)
- [`-webkit-text-stroke`](-webkit-text-stroke.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-fill-color>
