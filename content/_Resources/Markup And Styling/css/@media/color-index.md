color-index
===========

The `color-index`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](@media.md#media_features) can be used to test the number of
entries in the output device\'s color lookup table.

Syntax
------

The `color-index` feature is specified as an [`<integer>`](integer.md)
value representing the number of entries in the output device\'s color
lookup table. (This value is zero if the device does not use such a
table.) It is a range feature, meaning that you can also use the
prefixed `min-color-index` and `max-color-index` variants to query
minimum and maximum values, respectively.

Examples
--------

### Basic example

#### HTML

[html]

```html
<p>This is a test.</p>
```

#### CSS

```css

[css]

```css

p {
  color: black;
}

@media (color-index) {
  p {
    color: red;
  }
}

@media (min-color-index: 15000) {
  p {
    color: #1475ef;
  }
}

```

#### Result

### Custom stylesheet

This HTML will apply a special stylesheet for devices that have at least
256 colors.

[html]

```html
<link rel="stylesheet" href="http://foo.bar.com/base.css" />
<link
  rel="stylesheet"
  media="all and (min-color-index: 256)"
  href="http://foo.bar.com/color-stylesheet.css" />
```

Specifications
--------------

  ---------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------

  [Media Queries Level 4\
  [\#
  color-index]](https://drafts.csswg.org/mediaqueries/#color-index)

  ---------------------------------------------------------------------------

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

`color-index`

29

79

No

No

16

8

4.4

29

No

16

8

2.0

See also
--------

- [Using Media Queries](using_media_queries.md)
- [\@media](@media.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/color-index>
