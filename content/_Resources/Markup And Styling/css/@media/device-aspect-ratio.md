device-aspect-ratio
===================

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

**Note:** To query for the aspect ratio of the viewport, developers
should use the [`aspect-ratio`](_Resources/Markup%20And%20Styling/css/@media/aspect-ratio.md) media feature instead.

The `device-aspect-ratio`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](@media.md#media_features) can be used to test the
width-to-height aspect ratio of an output device.

Syntax
------

The `device-aspect-ratio` feature is specified as a
[`<ratio>`](ratio.md). It is a range feature, meaning that you can also
use the prefixed `min-device-aspect-ratio` and `max-device-aspect-ratio`
variants to query minimum and maximum values, respectively.

Examples
--------

### Using min-device-aspect-ratio

[css]

```css
article {
  padding: 1rem;
}

@media screen and (min-device-aspect-ratio: 16/9) {
  article {
    padding: 1rem 5vw;
  }
}
```

Specifications
--------------

  -------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------

  [Media Queries Level 4\
  [\#
  device-aspect-ratio]](https://drafts.csswg.org/mediaqueries/#device-aspect-ratio)

  -------------------------------------------------------------------------------------------

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

`device-aspect-ratio`

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

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/device-aspect-ratio>
