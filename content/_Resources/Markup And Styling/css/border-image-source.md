border-image-source
===================

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `border-image-source`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the source image used to create an element\'s [](border-image.md).

Try it
------

The [`border-image-slice`](border-image-slice.md) property is used to
divide the source image into regions, which are then dynamically applied
to the final border image.

Syntax
------

[css]

```css
/* Keyword value */
border-image-source: none;

/* <image> values */
border-image-source: url(image.jpg);
border-image-source: linear-gradient(to top, red, yellow);

/* Global values */
border-image-source: inherit;
border-image-source: initial;
border-image-source: revert;
border-image-source: revert-layer;
border-image-source: unset;
```

### Values

[`none`](#none)

:   No border image is used. The appearance defined by
    [`border-style`](border-style.md) is displayed instead.

[`<image>`](_Resources/Markup%20And%20Styling/css/image.md)

:   Image reference to use for the border.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements, except internal table elements when [`border-collapse`](border-collapse.md) is `collapse`. It also applies to [`::first-letter`](::first-letter).
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   `none` or the image with its URI made absolute
  Animation type                     discrete
  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
border-image-source = 
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

### Basic example

[css]

```css
.box {
  border-image-source: url("image.png");
}
```

Specifications
--------------

  ------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  the-border-image-source]](https://drafts.csswg.org/css-backgrounds/#the-border-image-source)

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

`border-image-source`

15

12

15

11

15

6

4.4

18

15

14

6

1.0

See also
--------

- [`border`](border.md)
- [`outline`](outline.md)
- [`box-shadow`](box-shadow.md)
- [`background-image`](background-image.md)
- [`url()`](url.md) function

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-source>
