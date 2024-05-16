-webkit-text-stroke-color
=========================

The `-webkit-text-stroke-color` CSS property specifies the stroke
[color](color_value.md) of characters of text. If this property is not set,
the value of the [`color`](_Resources/Markup%20And%20Styling/css/color.md) property is used.

Syntax
------

[css]

```css
/* <color> values */
-webkit-text-stroke-color: red;
-webkit-text-stroke-color: #e08ab4;
-webkit-text-stroke-color: rgb(200, 100, 0);

/* Global values */
-webkit-text-stroke-color: inherit;
-webkit-text-stroke-color: initial;
-webkit-text-stroke-color: revert;
-webkit-text-stroke-color: revert-layer;
-webkit-text-stroke-color: unset;
```

### Values

[`<color>`](#color)

:   The color of the stroke.

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
-webkit-text-stroke-color = 
  <color>  
```

Examples
--------

### Varying the stroke color

#### HTML

[html]

```html
<p>Text with stroke</p>
<input type="color" value="#ff0000" />
```

#### CSS

[css]

```css
p {
  margin: 0;
  font-size: 4em;
  -webkit-text-stroke-width: 3px;
  -webkit-text-stroke-color: #ff0000; /* Can be changed in the live sample */
}
```

#### Results

Specifications
--------------

  ------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------

  [Compatibility Standard\
  [\#
  the-webkit-text-stroke-color]](https://compat.spec.whatwg.org/#the-webkit-text-stroke-color)

  ------------------------------------------------------------------------------------------------------

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

`-webkit-text-stroke-color`

1

15

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
- [`-webkit-text-fill-color`](-webkit-text-fill-color.md)
- [`-webkit-text-stroke-width`](-webkit-text-stroke-width.md)
- [`-webkit-text-stroke`](-webkit-text-stroke.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-stroke-color>
