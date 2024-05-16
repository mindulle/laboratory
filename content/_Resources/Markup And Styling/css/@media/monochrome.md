monochrome
==========

The `monochrome` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[media feature](@media.md#media_features) can be used to test the number
of bits per pixel in the monochrome frame buffer of the output device.

Syntax
------

The `monochrome` feature is specified as an [`<integer>`](integer.md)
representing the number of bits per pixel in the monochrome frame
buffer. If the device is not a monochrome device, the value is zero. It
is a range feature, meaning that you can also use the prefixed
`min-monochrome` and `max-monochrome` variants to query minimum and
maximum values, respectively.

Examples
--------

### HTML

[html]

```html
<p class="mono">Your device supports monochrome pixels!</p>
<p class="no-mono">Your device doesn't support monochrome pixels.</p>
```

### CSS

[css]

```css
p {
  display: none;
}

/* Any monochrome device */
@media (monochrome) {
  p.mono {
    display: block;
    color: #333;
  }
}

/* Any non-monochrome device */
@media (monochrome: 0) {
  p.no-mono {
    display: block;
    color: #ee3636;
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
  monochrome]](https://drafts.csswg.org/mediaqueries/#monochrome)

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

`monochrome`

1

79

2

No

10

3

≤37

18

4

10.1

1

1.0

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/monochrome>
