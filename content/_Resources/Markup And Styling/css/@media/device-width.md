device-width
============

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

**Note:** To query for the width of the viewport, developers should use
the [`width`](_Resources/Markup%20And%20Styling/css/@media/width.md) media feature instead.

The `device-width`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](@media.md#media_features) can be used to test the width of an
output device\'s rendering surface.

Syntax
------

The `device-width` feature is specified as a [`<length>`](length.md)
value. It is a range feature, meaning that you can also use the prefixed
`min-device-width` and `max-device-width` variants to query minimum and
maximum values, respectively.

Examples
--------

### Applying a special stylesheet for devices that are narrower than 800 pixels

[html]

```html
<link
  rel="stylesheet"
  media="screen and (max-device-width: 799px)"
  href="http://foo.bar.com/narrow-styles.css" />
```

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [Media Queries Level 4\
  [\#
  device-width]](https://drafts.csswg.org/mediaqueries/#device-width)

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

`device-width`

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

- [Using Media Queries](using_media_queries.md)
- [\@media](@media.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/device-width>
