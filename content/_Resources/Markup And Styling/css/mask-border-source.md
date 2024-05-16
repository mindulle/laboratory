mask-border-source
==================

The `mask-border-source`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the source image used to create an element\'s [](mask-border.md).

The [`mask-border-slice`](mask-border-slice.md) property is used to divide
the source image into regions, which are then dynamically applied to the
final mask border.

Syntax
------

[css]

```css
/* Keyword value */
mask-border-source: none;

/* <image> values */
mask-border-source: url(image.jpg);
mask-border-source: linear-gradient(to top, red, yellow);

/* Global values */
mask-border-source: inherit;
mask-border-source: initial;
mask-border-source: revert;
mask-border-source: revert-layer;
mask-border-source: unset;
```

### Values

[`none`](#none)

:   No mask border is used.

[`<image>`](_Resources/Markup%20And%20Styling/css/image.md)

:   Image reference to use for the mask border.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements; In SVG, it applies to container elements excluding the [`<defs>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs) element and all graphics elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified, but with [`url()`](url.md) values made absolute
  Animation type                     discrete
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
mask-border-source = 
  none     |
  <image>  

<image> = 
  <url>       |
  <gradient>  

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  
```

Examples
--------

### Basic usage

This property doesn\'t appear to be supported anywhere yet. When it
eventually starts to be supported, it will serve to define the source of
the border mask.

[css]

```css
mask-border-source: url(image.jpg);
```

Chromium-based browsers support an outdated version of this property ---
`mask-box-image-source` --- with a prefix:

[css]

```css
-webkit-mask-box-image-source: url(image.jpg);
```

**Note:** The [`mask-border`](mask-border.md) page features a working
example (using the out-of-date prefixed border mask properties supported
in Chromium), so you can get an idea of the effect.

Specifications
--------------

  -----------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------

  [CSS Masking Module Level 1\
  [\#
  the-mask-border-source]](https://drafts.fxtf.org/css-masking/#the-mask-border-source)

  -----------------------------------------------------------------------------------------------

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

`mask-border-source`

1

79

No

No

15

3.1

4.4

18

No

14

3

1.0

See also
--------

- [`mask-border`](mask-border.md)
- [`mask-border-mode`](mask-border-mode.md)
- [`mask-border-outset`](mask-border-outset.md)
- [`mask-border-repeat`](mask-border-repeat.md)
- [`mask-border-width`](mask-border-width.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-source>
