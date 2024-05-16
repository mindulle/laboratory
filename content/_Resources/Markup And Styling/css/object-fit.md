object-fit
==========

The `object-fit` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets how the content of a [replaced element](replaced_element.md),
such as an
[`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)
or
[`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video),
should be resized to fit its container.

You can alter the alignment of the replaced element\'s content object
within the element\'s box using the [`object-position`](object-position.md)
property.

Try it
------

Syntax
------

[css]

```css
object-fit: contain;
object-fit: cover;
object-fit: fill;
object-fit: none;
object-fit: scale-down;

/* Global values */
object-fit: inherit;
object-fit: initial;
object-fit: revert;
object-fit: revert-layer;
object-fit: unset;
```

The `object-fit` property is specified as a single keyword chosen from
the list of values below.

### Values

[`contain`](#contain)

:   The replaced content is scaled to maintain its aspect ratio while
    fitting within the element\'s content box. The entire object is made
    to fill the box, while preserving its aspect ratio, so the object
    will be
    [\"letterboxed\"](https://en.wikipedia.org/wiki/Letterboxing_(filming))
    if its aspect ratio does not match the aspect ratio of the box.

[`cover`](#cover)

:   The replaced content is sized to maintain its aspect ratio while
    filling the element\'s entire content box. If the object\'s aspect
    ratio does not match the aspect ratio of its box, then the object
    will be clipped to fit.

[`fill`](#fill)

:   The replaced content is sized to fill the element\'s content box.
    The entire object will completely fill the box. If the object\'s
    aspect ratio does not match the aspect ratio of its box, then the
    object will be stretched to fit.

[`none`](#none)

:   The replaced content is not resized.

[`scale-down`](#scale-down)

:   The content is sized as if `none` or `contain` were specified,
    whichever would result in a smaller concrete object size.

Formal definition
-----------------

  ---------------------------------- -------------------
  [Initial value](initial_value.md)     `fill`
  Applies to                         replaced elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -------------------

Formal syntax
-------------

```
object-fit = 
  fill        |
  contain     |
  cover       |
  none        |
  scale-down  
```

Examples
--------

### Setting object-fit for an image

#### HTML

[html]

```html
<section>
  <h2>object-fit: fill</h2>
  <img class="fill" src="mdn_logo_only_color.png" alt="MDN Logo" />

  <img class="fill narrow" src="mdn_logo_only_color.png" alt="MDN Logo" />

  <h2>object-fit: contain</h2>
  <img class="contain" src="mdn_logo_only_color.png" alt="MDN Logo" />

  <img class="contain narrow" src="mdn_logo_only_color.png" alt="MDN Logo" />

  <h2>object-fit: cover</h2>
  <img class="cover" src="mdn_logo_only_color.png" alt="MDN Logo" />

  <img class="cover narrow" src="mdn_logo_only_color.png" alt="MDN Logo" />

  <h2>object-fit: none</h2>
  <img class="none" src="mdn_logo_only_color.png" alt="MDN Logo" />

  <img class="none narrow" src="mdn_logo_only_color.png" alt="MDN Logo" />

  <h2>object-fit: scale-down</h2>
  <img class="scale-down" src="mdn_logo_only_color.png" alt="MDN Logo" />

  <img class="scale-down narrow" src="mdn_logo_only_color.png" alt="MDN Logo" />
</section>
```

#### CSS

[css]

```css
h2 {
  font-family:
    Courier New,
    monospace;
  font-size: 1em;
  margin: 1em 0 0.3em;
}

img {
  width: 150px;
  height: 100px;
  border: 1px solid #000;
  margin: 10px 0;
}

.narrow {
  width: 100px;
  height: 150px;
}

.fill {
  object-fit: fill;
}

.contain {
  object-fit: contain;
}

.cover {
  object-fit: cover;
}

.none {
  object-fit: none;
}

.scale-down {
  object-fit: scale-down;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------

  [CSS Images Module Level 3\
  [\#
  the-object-fit]](https://drafts.csswg.org/css-images/#the-object-fit)

  -------------------------------------------------------------------------------

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

`object-fit`

32

79

16--79Only supported for `<img>` elements.

36

No

1911.6--15

10

4.4.3

32

36

1912--14

10

2.0

See also
--------

- Other image-related CSS properties:
    [`object-position`](object-position.md),
    [`image-orientation`](image-orientation.md),
    [`image-rendering`](image-rendering.md),
    [`image-resolution`](image-resolution.md).
- [`background-size`](background-size.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit>
