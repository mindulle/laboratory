clip
====

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

**Warning:** Where possible, authors are encouraged to use the newer
[`clip-path`](clip-path.md) property instead.

The `clip` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property defines a visible portion of an element. The `clip` property
applies only to absolutely positioned elements --- that is, elements
with [`position:absolute`](position.md) or [`position:fixed`](position.md).

Syntax
------

[css]

```css
/* Keyword value */
clip: auto;

/* <shape> values */
clip: rect(1px, 10em, 3rem, 2ch);

/* Global values */
clip: inherit;
clip: initial;
clip: revert;
clip: revert-layer;
clip: unset;
```

### Values

[`<shape>`](shape.md)

:   A rectangular [`<shape>`](shape.md) of the form
    `rect(<top>, <right>, <bottom>, <left>)`. The `<top>` and `<bottom>`
    values are offsets from the *inside top border edge* of the box,
    while `<right>` and `<left>` are offsets from the *inside left
    border edge* of the box --- that is, the extent of the padding box.

    The `<top>`, `<right>`, `<bottom>`, and `<left>` values may be
    either a [`<length>`](length) or `auto`. If any side\'s value is
    `auto`, the element is clipped to that side\'s *inside border edge*.

[`auto`](#auto)

:   The element does not clip (default). This is different from
    `rect(auto, auto, auto, auto)`, which clips to the element\'s inside
    border edges.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         absolutely positioned elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   `auto` if specified as `auto`, otherwise a rectangle with four values, each of which is `auto` if specified as `auto` or the computed length otherwise
  Animation type                     a [rectangle](shape.md#interpolation)
  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
clip = 
  <rect()>  |
  auto      
```

Examples
--------

### Clipping an image

[html]

```html
<p class="dotted-border">
  <img src="macarons.png" alt="Original graphic" />
  <img id="top-left" src="macarons.png" alt="Graphic clipped to upper left" />
  <img id="middle" src="macarons.png" alt="Graphic clipped towards middle" />
  <img
    id="bottom-right"
    src="macarons.png"
    alt="Graphic clipped to bottom right" />
</p>
```

[css]

```css
.dotted-border {
  border: dotted;
  position: relative;
  width: 390px;
  height: 400px;
}

#top-left,
#middle,
#bottom-right {
  position: absolute;
  top: 0;
}

#top-left {
  left: 400px;
  clip: rect(0, 130px, 90px, 0);
}

#middle {
  left: 270px;
  clip: rect(100px, 260px, 190px, 130px);
}

#bottom-right {
  left: 140px;
  clip: rect(200px, 390px, 290px, 260px);
}
```

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [CSS Masking Module Level 1\
  [\#
  clip-property]](https://drafts.fxtf.org/css-masking/#clip-property)

  -----------------------------------------------------------------------------

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

`clip`

1

12

1

4Before Internet Explorer 7, Internet Explorer incorrectly interprets
`clip: auto` as `clip: rect(auto, auto, auto, auto)`.

7

1Safari incorrectly interprets `clip: auto` as
`clip: rect(auto, auto, auto, auto)`.

37

18

4

14

1Safari incorrectly interprets `clip: auto` as
`clip: rect(auto, auto, auto, auto)`.

1.0

See also
--------

- This property is deprecated. Use [`clip-path`](clip-path.md) instead.
- Related CSS properties:
  - [`text-overflow`](text-overflow.md)
  - [`white-space`](white-space.md)
  - [`overflow-x`](overflow-x.md)
  - [`overflow-y`](overflow-y.md)
  - [`overflow`](overflow.md)
  - [`display`](display.md)
  - [`position`](position.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/clip>
