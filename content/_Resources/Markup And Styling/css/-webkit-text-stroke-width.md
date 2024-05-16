-webkit-text-stroke-width
=========================

The `-webkit-text-stroke-width`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies the width of the stroke for text.

Syntax
------

[css]

```css
/* Keyword values */
-webkit-text-stroke-width: thin;
-webkit-text-stroke-width: medium;
-webkit-text-stroke-width: thick;

/* <length> values */
-webkit-text-stroke-width: 2px;
-webkit-text-stroke-width: 0.1em;
-webkit-text-stroke-width: 1mm;
-webkit-text-stroke-width: 5pt;

/* Global values */
-webkit-text-stroke-width: inherit;
-webkit-text-stroke-width: initial;
-webkit-text-stroke-width: revert;
-webkit-text-stroke-width: revert-layer;
-webkit-text-stroke-width: unset;
```

### Values

[`<line-width>`](#line-width)

:   The width of the stroke.

Formal definition
-----------------

  ---------------------------------- -------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   absolute [`<length>`](length.md)
  Animation type                     discrete
  ---------------------------------- -------------------------------

Formal syntax
-------------

```
-webkit-text-stroke-width = 
  <line-width>  

<line-width> = 
  <length [0,∞]>  |
  thin            |
  medium          |
  thick           
```

Examples
--------

### Varying stroke widths

#### CSS

[css]

```css
p {
  margin: 0;
  font-size: 4em;
  -webkit-text-stroke-color: red;
}

#thin {
  -webkit-text-stroke-width: thin;
}

#medium {
  -webkit-text-stroke-width: 3px;
}

#thick {
  -webkit-text-stroke-width: 1.5mm;
}
```

#### HTML

[html]

```html
<p id="thin">Thin stroke</p>
<p id="medium">Medium stroke</p>
<p id="thick">Thick stroke</p>
```

#### Results

Specifications
--------------

  ------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------

  [Compatibility Standard\
  [\#
  the-webkit-text-stroke-width]](https://compat.spec.whatwg.org/#the-webkit-text-stroke-width)

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

`-webkit-text-stroke-width`

1

15

49

No

15

3

38

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
- [`-webkit-text-stroke`](-webkit-text-stroke.md)
- [`-webkit-text-fill-color`](-webkit-text-fill-color.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-stroke-width
