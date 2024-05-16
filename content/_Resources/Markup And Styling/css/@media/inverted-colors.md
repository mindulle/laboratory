inverted-colors
===============

The `inverted-colors`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](@media.md#media_features) is used to test if the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) or
the underlying operating system has inverted all colors.

Inversion of colors can have unpleasant side effects, such as shadows
turning into highlights, which can reduce the readability of the
content. Using this media feature, you can detect if inversion is
happening and style the content accordingly while respecting user
preference.

Syntax
------

[css]

```css
/* Keyword value */
@media (inverted-colors: inverted) {
  /* styles to apply if inversion of colors is detected */
}
```

The `inverted-colors` feature is specified as one of the following
keyword values:

[`none`](#none)

:   Indicates that the colors are displayed normally and no inversion of
    colors has happened. This keyword value evaluates as false.

[`inverted`](#inverted)

:   Indicates that all pixels within the displayed area have been
    inverted. This keyword value evaluates as true.

Examples
--------

### Applying styles if color inversion is detected

This example demonstrates the effects of both `inverted-colors` media
feature keyword values and when the `inverted-colors` media feature is
not supported.

#### HTML

[html]

```html
<p>
  If color inversion is detected, this text will appear blue on white (the
  inverse of yellow on black) along with a line over the text. If no color
  inversion is happening, the text will appear red on light gray without the
  line over the text.
</p>
<p>
  If the text is gray and no overline is present, it means your browser doesn't
  support the
  <code>inverted-colors</code> media feature.
</p>
```

#### CSS

[css]

```css
p {
  color: gray;
}

@media (inverted-colors: inverted) {
  p {
    background: black;
    color: yellow;
    text-decoration: overline;
  }
}

@media (inverted-colors: none) {
  p {
    background: #eee;
    color: red;
  }
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Media Queries Level 5\
  [\#
  inverted]](https://drafts.csswg.org/mediaqueries-5/#inverted)

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

`inverted-colors`

No

No

114

No

No

9.1

No

No

No

No

10

No

See also
--------

- [\@media](@media.md)
- [CSS media queries](css_media_queries.md) module
- [Using media queries](using_media_queries.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/inverted-colors>
