update
======

The `update` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[media feature](@media.md#media_features) can be used to test how
frequently (if at all) the output device is able to modify the
appearance of content once rendered.

[css]

```css
@media (update: < none | slow | fast >) {
  /* styles to apply if the update frequency of the output device is a match */
}
```

Syntax
------

The `update` feature is specified as a single keyword value chosen from
the list below.

[`none`](#none)

:   Once it has been rendered, the layout can no longer be updated.
    Example: documents printed on paper.

[`slow`](#slow)

:   The layout may change dynamically according to the usual rules of
    CSS, but the output device is not able to render or display changes
    quickly enough for them to be perceived as a smooth animation.
    Examples: e-book readers or severely underpowered devices.

[`fast`](#fast)

:   The layout may change dynamically according to the usual rules of
    CSS, and the output device is not unusually constrained in speed, so
    regularly-updating things like [CSS Animations](css_animations.md)
    can be used. Example: computer screens.

Examples
--------

### HTML

[html]

```html
<p>
  If this text animates for you, your browser supports `update` and you are
  using a fast-updating device.
</p>
```

### CSS

[css]

```css
@keyframes jiggle {
  from {
    transform: translateY(0);
  }

  to {
    transform: translateY(25px);
  }
}

@media (update: fast) {
  p {
    animation: 1s jiggle linear alternate infinite;
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
  [\# update]](https://drafts.csswg.org/mediaqueries/#update)

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

`update`

113

113

102

No

99

17

113

113

102

No

17

No

See also
--------

- [Using Media Queries](using_media_queries.md)
- [\@media](@media.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/update>
