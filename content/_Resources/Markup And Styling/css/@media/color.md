color
=====

The `color` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[media feature](@media.md#media_features) can be used to test the number
of bits per color component (red, green, blue) of the output device.

Syntax
------

The `color` feature is specified as an [`<integer>`](integer.md) value
that represents the number of bits per color component (red, green,
blue) of the output device. If the device is not a color device, the
value is zero. It is a range feature, meaning that you can also use the
prefixed `min-color` and `max-color` variants to query minimum and
maximum values, respectively.

**Note:** If the various color components are represented by different
numbers of bits, the smallest number is used. For example, if a display
uses 5 bits for blue and red and 6 bits for green, then the device is
considered to use 5 bits per color component. If the device uses indexed
colors, the minimum number of bits per color component in the color
table is used.

See [](applying_color.md) to learn more about using CSS to
apply color to HTML.

Examples
--------

### HTML

[html]

```html
<p>
  This text should be black on non-color devices, red on devices with a low
  number of colors, and greenish on devices with a high number of colors.
</p>
```

### CSS

[css]

```css
p {
  color: black;
}

/* Any color device */
@media (color) {
  p {
    color: red;
  }
}

/* Any color device with at least 8 bits per color component */
@media (min-color: 8) {
  p {
    color: #24ba13;
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
  [\# color]](https://drafts.csswg.org/mediaqueries/#color)

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

`color`

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

- [](applying_color.md)
- The CSS [`color`](_Resources/Markup%20And%20Styling/css/color.md) property
- The CSS [`<color>`](color_value.md) data unit

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/color>
