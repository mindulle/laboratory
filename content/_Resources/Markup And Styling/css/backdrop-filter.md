backdrop-filter
===============

The `backdrop-filter`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property lets
you apply graphical effects such as blurring or color shifting to the
area behind an element. Because it applies to everything *behind* the
element, to see the effect the element or its background needs to be
transparent or partially transparent.

Try it
------

Syntax
------

[css]

```css
/* Keyword value */
backdrop-filter: none;

/* URL to SVG filter */
backdrop-filter: url(commonfilters.svg#filter);

/* <filter-function> values */
backdrop-filter: blur(2px);
backdrop-filter: brightness(60%);
backdrop-filter: contrast(40%);
backdrop-filter: drop-shadow(4px 4px 10px blue);
backdrop-filter: grayscale(30%);
backdrop-filter: hue-rotate(120deg);
backdrop-filter: invert(70%);
backdrop-filter: opacity(20%);
backdrop-filter: sepia(90%);
backdrop-filter: saturate(80%);

/* Multiple filters */
backdrop-filter: url(filters.svg#filter) blur(4px) saturate(150%);

/* Global values */
backdrop-filter: inherit;
backdrop-filter: initial;
backdrop-filter: revert;
backdrop-filter: revert-layer;
backdrop-filter: unset;
```

### Values

[`none`](#none)

:   No filter is applied to the backdrop.

[`<filter-function-list>`](#filter-function-list)

:   A space-separated list of [`<filter-function>`](filter-function.md)s or
    an [SVG
    filter](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter)
    that will be applied to the backdrop. CSS `<filter-function>`s
    include [`blur()`](blur.md),
    [`brightness()`](brightness.md),
    [`contrast()`](contrast.md),
    [`drop-shadow()`](drop-shadow.md),
    [`grayscale()`](grayscale.md),
    [`hue-rotate()`](hue-rotate.md),
    [`invert()`](invert.md),
    [`opacity()`](_Resources/Markup%20And%20Styling/css/filter-function/opacity.md),
    [`saturate()`](saturate.md), and
    [`sepia()`](sepia.md).

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements; In SVG, it applies to container elements excluding the [`<defs>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs) element and all graphics elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     a [filter function list](filter.md#interpolation)
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
backdrop-filter = 
  none                 |
  <filter-value-list>  

<filter-value-list> = 
  [ <filter-function> | <url> ]+  

<filter-function> = 
  <blur()>         |
  <brightness()>   |
  <contrast()>     |
  <drop-shadow()>  |
  <grayscale()>    |
  <hue-rotate()>   |
  <invert()>       |
  <opacity()>      |
  <sepia()>        |
  <saturate()>     

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  
```

Examples
--------

### CSS

[css]

```css
.box {
  background-color: rgb(255 255 255 / 0.3);
  backdrop-filter: blur(10px);
}

body {
  background-image: url("anemones.jpg");
}
```

### HTML

[html]

```html
<div class="container">
  <div class="box">
    <p>backdrop-filter: blur(10px)</p>
  </div>
</div>
```

### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [Filter Effects Module Level 2\
  [\#
  BackdropFilterProperty]](https://drafts.fxtf.org/filter-effects-2/#BackdropFilterProperty)

  ----------------------------------------------------------------------------------------------------

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

`backdrop-filter`

76

17

103

No

63

9

76

76

103

54

9

12.0

See also
--------

- [`filter`](filter.md)
- [`<filter-function>`](filter-function.md)
- [`background-blend-mode`](background-blend-mode.md),
    [`mix-blend-mode`](mix-blend-mode.md)
- [CSS filter effects](css_filter_effects.md)
- [CSS compositing and blending](css_compositing_and_blending.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/backdrop-filter>
