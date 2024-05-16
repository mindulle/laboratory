width
=====

The `width` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[media feature](@media.md#media_features) can be used to test the width
of the
[viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport)
(or the page box, for [paged media](css_paged_media.md)).

Syntax
------

The `width` feature is specified as a [`<length>`](length.md) value
representing the viewport width. It is a range feature, meaning that you
can also use the prefixed `min-width` and `max-width` variants to query
minimum and maximum values, respectively.

Examples
--------

### HTML

[html]

```html
<div>Watch this element as you resize your viewport's width.</div>
```

### CSS

```css

[css]

```css

/*Exact width*/
@media (width: 360px) {
  div {
    color: red;
  }
}

/*Minimum width*/
@media (min-width: 35rem) {
  div {
    background: yellow;
  }
}

/*Maximum width*/
@media (max-width: 50rem) {
  div {
    border: 2px solid blue;
  }
}

```

### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Media Queries Level 4\
  [\# width]](https://drafts.csswg.org/mediaqueries/#width)

  -----------------------------------------------------------------------

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

`width`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

See also
--------

- [Using media queries](using_media_queries.md)
- [\@media](@media.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/width>
