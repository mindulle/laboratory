resolution
==========

The `resolution` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[media feature](@media.md#media_features) can be used to test the pixel
density of the output device.

Syntax
------

The `resolution` feature is specified as a
[`<resolution>`](_Resources/Markup%20And%20Styling/css/resolution.md) value representing the pixel density of
the output device. It is a range feature, meaning that you can also use
the prefixed `min-resolution` and `max-resolution` variants to query
minimum and maximum values, respectively.

Examples
--------

### HTML

[html]

```html
<p>This is a test of your device's pixel density.</p>
```

### CSS

[css]

```css
/* Exact resolution */
@media (resolution: 150dpi) {
  p {
    color: red;
  }
}

/* Minimum resolution */
@media (min-resolution: 72dpi) {
  p {
    text-decoration: underline;
  }
}

/* Maximum resolution */
@media (max-resolution: 300dpi) {
  p {
    background: yellow;
  }
}
```

### Result

Specifications
--------------

  -------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------

  [Media Queries Level 4\
  [\#
  resolution]](https://drafts.csswg.org/mediaqueries/#resolution)

  -------------------------------------------------------------------------

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

`resolution`

29

12

8

3.5Supports
[`<integer>`](https://developer.mozilla.org/docs/Web/CSS/integer) values
only.

9

1610--15

16

4.4

29

8

4Supports
[`<integer>`](https://developer.mozilla.org/docs/Web/CSS/integer) values
only.

1610.1--14

16

2.0

See also
--------

- [`window.devicePixelRatio`](https://developer.mozilla.org/en-US/docs/Web/API/Window/devicePixelRatio)
- The [`image-resolution`](image-resolution.md) property

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/resolution>
